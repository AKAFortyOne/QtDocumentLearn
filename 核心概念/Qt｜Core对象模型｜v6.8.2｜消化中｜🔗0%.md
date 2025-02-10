类型： #Concept
技术栈： #Cpp #Qt 
功能域： #Core #对象模型
认知阶段： #已掌握 （#待理解/#已掌握/#需复习）

---
### 原始摘录
- a very powerful mechanism for seamless object communication called [signals and slots]
- queryable and designable [object properties]
- powerful [events and event filters]
- contextual [string translation for internationalization]
- sophisticated interval driven [timers] that make it possible to elegantly integrate many tasks in an event-driven GUI
- hierarchical and queryable [object trees] that organize object ownership in a natural way
- guarded pointers ([QPointer]) that are automatically set to 0 when the referenced object is destroyed, unlike normal C++ pointers which become dangling pointers when their objects are destroyed
- a [dynamic cast] that works across library boundaries.
- support for [custom type] creation.

These classes form the basis of the Qt Object Model.

| QMetaClassInfo            | Additional information about a class                               |
| ------------------------- | ------------------------------------------------------------------ |
| **QMetaContainer**？       | **Common functionality for sequential and associative containers** |
| **QMetaEnum**？            | **Meta-data about an enumerator**                                  |
| **QMetaMethod**           | **Meta-data about a member function**                              |
| **QMetaObject**           | **Contains meta-information about Qt objects**                     |
| **QMetaProperty**         | **Meta-data about a property**                                     |
| **QMetaSequence**         | **Allows type erased access to sequential containers**             |
| **QMetaType**             | **Manages named types in the meta-object system**                  |
| **QObject**               | **The base class of all Qt objects**                               |
| **QObjectCleanupHandler** | **Watches the lifetime of multiple QObjects**                      |
| **QPointer**              | **Template class that provides guarded pointers to QObject**       |
| **QSignalBlocker**        | **Exception-safe wrapper around QObject::blockSignals()**          |
| **QSignalMapper**         | **Bundles signals from identifiable senders**                      |
| **QVariant**              | **Acts like a union for the most common Qt data types**            |

---
### 认知转译
Qt对象模型提供了如下功能：
- 信号与槽
- 对象属性
	[[QMetaObject]]
- 事件及事件筛选
- 文本翻译及国际化
- 计时器
- 对象树
- 安全指针（QPointer）
- 动态转换
- 自定义类型

---
### 隐喻映射

---
> [!QUESTION]
