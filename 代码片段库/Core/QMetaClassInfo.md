类型： #Snippet
技术栈： #Cpp #Qt
功能域： #Core #ObjectMode
复杂度层级： #Low

---

Header：\<QMetaClassInfo\>
Doc：[QMetaClassInfo Class](https://doc.qt.io/qt-6/qmetaclassinfo.html)
Public Functions：
```c++
const char *name() const
const char *value() const
```

---

How to set Class Info：
```c++
class MyClass
{
    Q_OBJECT
    Q_CLASSINFO("name", "value")
    Q_CLASSINFO("url", "something you want to write")

public:
    ...
};
```

---

How to Get Class Info：
```c++
 const QMetaObject *metaObj = &MyClass::staticMetaObject;

for (int i = 0; i < metaObj->classInfoCount(); i++) {
	QMetaClassInfo classInfo = metaObj->classInfo(i);
	qInfo() << "Key:" << classInfo.name();
	qInfo() << "Value:" << classInfo.value();
}
```
（Link：[QMetaObject](QMetaObject)）