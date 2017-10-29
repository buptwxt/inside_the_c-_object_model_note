# data语义学
问题，以下这些类sizeof大小？
class X{};
class Y: public virtual X{};
class Z: public virtual X{};
class A: public Y, public Z{};
编译器为空类安插进去一个char，使得空class的对象得以在内存中配置独一无二的地址。
Y Z大小受到3个因素影响
1. 语言本身所造成的额外负担，例如支持virtual base class
2.     


