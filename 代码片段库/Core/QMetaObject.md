类型： #Snippet
技术栈： #Cpp #Qt
功能域： #Core #ObjectMode
复杂度层级： #Medium

---

Header：\<QMetaObject\>
Doc：[QMetaObject](https://doc.qt.io/qt-6/qmetaobject.html)
Public Types：
```c++
class Connection
{
	swap(QMetaObject::Connection)
}
```
Public Functions：
```c++
QMetaClassInfo classInfo(int index) const  //指定index处的Info
int classInfoCount() const  //Info的条数
int classInfoOffset() const?
int indexOfClassInfo(const char *name) const  //制定name处的index
const char *className() const  //返回类名
const QMetaObject *superClass() const  //返回父类

QMetaMethod constructor(int index) const  //指定index处的构造方法
int constructorCount() const
int indexOfConstructor(const char *constructor) const

QMetaMethod method(int index) const
int methodCount() const
int methodOffset() const
int indexOfMethod(const char* method) const

QMetaEnum enumerator(int index) const
int enumeratorCount() const
int enumeratorOffset() const
int indexOfEnumerator(const char *name) const

QMetaProperty property(int index) const
int propertyCount() const
int propertyOffset() const
int indexOfProperty(const char *name) const
QMetaProperty userProperty() const

int indexOfSignal(const char *signal) const
int indexOfSlot(const char *slot) const

QObject *newInstance(Args &&... arguments) const
QMetaType metaType() const
bool inderits(const QMetaObject *metaObject) const
```
Static Public Members：
```c++

```
（Link：[[QMetaClassInfo]]，[[QMetaMethod]]，[[QMetaProperty]]，[[QMetaEnum]]，[[QMetaType]]）


---

```c++

```



```c++

```

---

> [!QUESTION]
哪些是实例化以后才能用的，哪些是不实例化也能用的？

必须实例化的有：

不实例化也行的：

