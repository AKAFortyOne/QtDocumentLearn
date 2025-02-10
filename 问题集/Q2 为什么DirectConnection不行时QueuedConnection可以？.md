```c++
#include <QtCore/QCoreApplication>
#include <QDebug>
#include <QTextStream>
#include "Radio.h"
#include "Channel.h"

int main(int argc, char *argv[])
{
	QCoreApplication a(argc, argv);
	
	...
	//radio.connect(&radio, &Radio::quit, &a, &QCoreApplication::quit, Qt::DirectConnection);      //不行，无法退出
	radio.connect(&radio, &Radio::quit, &a, &QCoreApplication::quit, Qt::QueuedConnection);        //可以退出
	do
	{
		...
		else if (line == "QUIT")
		{
			emit radio.quit();
			break;
		}
		...
	} while (true);

	return a.exec();    //事件循环
}
```

DirectConnection立刻调用slot函数，然后执行后续代码。当为进入事件循环（a.exec()）时，调用quit无效
QueuedConnection会使得slot函数在事件循环中被调用。此时在事件循环中调用qApp-->quit()，此时可以退出，有效。

以下为Perplexity原话：
> 1. **线程上下文**
> **DirectConnection**：信号发出后，槽函数会立即在发出信号的线程中执行。如果信号和槽不在同一线程中，使用 `DirectConnection` 将导致槽函数无法被调用，因为它会尝试在错误的线程中执行。
> **QueuedConnection**：信号发出后，槽函数被插入到接收者线程的事件队列中。这样，无论信号和槽是否在同一线程中，槽函数都会在接收者的线程中执行，从而避免了线程不匹配的问题
> 2. **事件循环**
> 在使用 `DirectConnection` 时，如果槽函数执行的是耗时操作，会阻塞事件循环，这可能导致程序无响应。如果槽函数在UI线程中执行且耗时较长，用户界面将冻结。
> 使用 `QueuedConnection` 可以让信号发出后立即返回控制权给调用者，随后事件循环会处理插入的槽函数，这样可以避免UI冻结现象
> 3. **执行顺序**
> **DirectConnection** 会在发出信号后立即调用槽函数，然后继续执行后续代码。这意味着如果槽函数需要较长时间来处理，后续代码将被阻塞。
> **QueuedConnection** 则会立即执行后续代码，而槽函数将在稍后的事件循环中被调用，这样可以保持主线程的流畅性
> 4. **适用场景**
> 当信号和槽在同一线程中且槽函数执行时间较短时，使用 `DirectConnection` 是合适的。
> 当涉及多线程或需要避免阻塞主线程时，应优先选择 `QueuedConnection`，以确保程序的响应性和稳定性

（和线程有关吗？）