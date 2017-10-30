# data语义学
问题，以下这些类sizeof大小？
class X{};
class Y: public virtual X{};
class Z: public virtual X{};
class A: public Y, public Z{};
编译器为空类安插进去一个char，使得空class的对象得以在内存中配置独一无二的地址。
Y Z大小受到3个因素影响
1. 语言本身所造成的额外负担，例如支持virtual base class
2.  编译器对于特殊情况所提供的优化处理
3. alignment限制，即字节对齐

一个virtual base class subobject只会在derived class中存在一份实体，不管它在class继承体系中出现了多少次。
class object必须有足够的大小以容纳它所有的nonstatic data members，同事编译器会自动加上额外的date members，用以支持语言特性，同时还需要满足边界对齐。
## data member的绑定
extern float x；
class member float x；
防御性编程
data member 放在class 开头
inline function是放在class声明之外

## data member的存取
static 成员存在和nonstatic成员
static成员属于class，别名后存放在data段
nonstatic成员隐含通过this关联


