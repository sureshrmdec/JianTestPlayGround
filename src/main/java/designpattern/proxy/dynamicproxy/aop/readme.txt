上述便是我们针对connection做动态代理的方式，但是我们从中得不到任何好处，除了能比静态代理稍微少写点代码以外。因为这个动态代理还是只能
代理Connection这一个接口，如果我们写出这种动态代理的方式的话，说明我们应该使用静态代理处理这个问题，因为它代表我们其实只希望代理一个类
就好。从重构的角度来说，其实更简单点，那就是在你发现你使用静态代理的时候，需要写一大堆重复代码的时候，就请改用动态代理试试吧。

通常情况下，动态代理的使用是为了解决这样一种问题，就是我们需要代理一系列类的某一些方法，最典型的应用就是我们前段时间讨论过的springAOP，我
们需要创造出一批代理类，切入到一系列类当中的某一些方法中。下面给出一个经常使用的动态代理方式。

====================

上述我做了一些注释，其实已经说明一些问题，这个代理类的作用是可以代理任何类，因为它被传入的对象是Object，而不再是具体的类，比如刚才的
Connection，这些产生的代理类在调用toString方法时会被插入before方法和after方法.

SJ: 11/25/2016
上次SAP面试时问如何自己实现AOP时，应该直接回答动态代理！真是2啊。
