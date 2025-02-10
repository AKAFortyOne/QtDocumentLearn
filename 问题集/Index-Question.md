1. <font color="#ff0000">信号与槽连接失败</font>：信号与槽未触发或参数不匹配。
2. <font color="#ffff00">跨平台界面适配问题</font>：不同操作系统下界面显示不一致。
3. <font color="#00b0f0">多线程中更新UI崩溃</font>：在非主线程直接操作UI导致崩溃。
4. <font color="#00b0f0">内存泄漏</font>：未正确释放Qt对象。
5. <font color="#ff0000">中文乱码</font>：中文字符显示为乱码。
6. <font color="#ff0000">样式表（QSS）不生效</font>：样式表未正确应用。
7. <font color="#00b0f0">窗口闪烁或卡顿</font>：频繁重绘导致性能问题。
8. <font color="#ff0000">事件处理冲突</font>：事件被错误拦截（如按键事件）
9. <font color="#ffff00">文件路径处理问题</font>：跨平台路径分隔符不一致（`\` vs `/`）
10. <font color="#ffff00">数据库连接失败</font>：无法连接SQLite/MySQL等数据库
11. <font color="#ffff00">国际化（i18n）失效</font>：翻译文件（.qm）未加载或未生效。
12. <font color="#ff0000">QML与C++交互问题</font>：QML无法调用C++对象方法。
13. <font color="#ff0000">程序打包后缺少依赖库</font>：发布程序时缺少DLL或插件。
14. <font color="#ff0000">触摸屏事件不响应</font>：触摸事件未被正确处理。
15. <font color="#ffff00">高DPI屏幕显示模糊</font>：界面在高分辨率下模糊。
16. <font color="#00b0f0">自定义控件绘制性能差</font>：复杂自定义控件导致卡顿。
17. <font color="#00b0f0">网络请求阻塞UI</font>：同步HTTP请求导致界面冻结。
18. <font color="#ff0000">拖放操作（Drag & Drop）失效</font>：拖放功能未按预期工作。
19. <font color="#00b0f0">程序启动慢</font>：初始化耗时过长影响体验。
20. <font color="#ff0000">QTimer不准时</font>
21. <font color="#ff0000">源文件（qrc）加载失败</font>


### Q1：public function和static public members的区别是？
前者必须实例化(`var.func()`)才能用，后者不用实例化(`CLASS::func()`)也能用。
后者对于public函数实例化了也能用，对于private函数实例化就用不了了。
`metaObject`和`staticMetaObject`同理
