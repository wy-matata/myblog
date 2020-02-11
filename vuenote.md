#  VUE note
##  原生JS，JQuery和MVVM对比

* 原生JS: 语法冗长，复杂，操作页面麻烦，效率低
* JQuery: 提供简单的API，简化了操作dom的方式，但是没有对业务逻辑分层，需要维护数据与dom之间的同步。
* MVVM: 在 MVVM 框架中，View(视图) 和 Model(数据) 是不可以直接通讯的，在它们之间存在着 ViewModel 这个中间介充当着观察者的角色。当用户操作 View(视图)，ViewModel 感知到变化，然后通知 Model 发生相应改变；反之当 Model(数据) 发生改变，ViewModel 也能感知到变化，使 View 作出相应更新。这个一来一回的过程就是我们所熟知的双向绑定 

DOM （Document Object Model）是指文档对象模型，通过它，可以访问HTML文档的所有元素。


