类型： #Snippet
技术栈： #Cpp #Qt
功能域： #Core #ObjectMode
复杂度层级： #Low

---
### 🏛 原典藏经阁
Header：\<QMetaMethod\>
Doc：[QMetaMethod Class](https://doc.qt.io/qt-6/qmetamethod.html)
Public Types：
```c++
enum Access{Private, Protected, Public}
enum MethodType{Method, Signal, Slot, Constructor}
```
Public Functions：
```c++
bool isValid() const  //当前方法是否可用(存在)

int methodIndex() const  //返回当前方法的index
QByteArray methodSignature() const  //返回完整的方法签名
QMetaMethod::MethodType methodType() const  //返回当前方法的类型(enum MethodType)

QByteArray name() const  //当前方法的名字

QMetaType parameterMetaType(int index) const  //指定index处的参数类型信息
int parameterCount() const  //当前方法参数的数量
QList<QByteArray> parameterTypes() const  //该方法参数类型名字的List
QByteArray parameterTypeName(int index) const //指定index处的参数类型名字
int parameterType(int index) const  //指定index处的参数类型id
QList<QByteArray> parameterNames() const  //参数名字的List

QMetaType returnMetaType() const  //返回值的类型信息
const char *typeName() const  //返回值的类型名字
int returnType() const  //返回值的类型id

QMetaMethod::Access acess() const //当前方法的访问性(enum Acess)
bool isConst() const  //当前方法是否为const类型(不是返回值，是该方法)

int revision() const  //返回方法的修订号
const char *tag() const //获取当前方法的标签

bool invoke(QObject *obj, [Qt::ConnectionType type], [ReturnArg], Args)
```
Static Public Members：
```c++
QMetaMethod fromSignal(PointerToMemberFunction signal)
```
Macros：
```c++
Q_METAMETHOD_INVOKE_MAX_ARGS  //支持最大invoke动态调用method的数量
```

> [!TIP]
> Method之间支持`==`和`!=`运算

---
### 🗡 兵械图谱室
**invoke**：
```c++

```

**isConst**：
```C++
Q_INVOKABLE void a(int b) const;  //true
Q_INVOKABLE const char c(double d, char nametest);  //false
```

**revision**：
```C++
Q_REVISION()
```

**tag**：
Define Tag：
```c++
#ifndef Q_MOC_RUN
#define MY_CUSTOM_TAG
#endif

...
public:
	MY_CUSTOM_TAG ... void foo();
...
```

---
### 🧿 观星者回廊
> [!WARNING]
只有函数前加Q_INVOKABLE才能被QMetaMethod检查到
只有QMetaObject里的constructor才能匹配QMetaMethod里MetaType的Construct
一般情况下QMetaMethod只匹配Signal和Slot，特殊如第一条加动态调用前缀，才能检测到method

QByteArray直接输出qInfo，"内容"

---
### 🕯 传灯者密室
