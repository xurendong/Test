大标题
==========

小标题
----------

# 一级标题

## 二级标题

### 三级标题

#### 四级标题

- 个人编程，写一个命令行程序
    - 注册Github账号，建立项目仓库
        - 添加ReadMe.md并编辑，描述项目的简要介绍、功能、用例、下载、文档等
        - 建立doc目录存放文档
        - 建立scripts目录存放各种脚本
        - 建立config目录存放可公开配置信息
        - 建立src目录存放源码
        - 建立test目录存放测试脚本极其数据
        - 建立PSP表格，预估下述几个过程的耗时估计
    - 分析程序的需求，并提交文档到github
        - 基本需求
        - 扩展需求
        - 高级需求
    - 功能设计，并提交文档到github

[xinz](http://www.cnblogs.com/xinz)

SE_FZU目录：
[1](http://www.cnblogs.com/math/p/4820808.html)
[2](http://www.cnblogs.com/math/p/4827832.html)
[3](http://www.cnblogs.com/math/p/4833301.html)
[4](http://www.cnblogs.com/math/p/4852995.html)
[5](http://www.cnblogs.com/math/p/4870584.html)
[6](http://www.cnblogs.com/math/p/4890133.html)
[7](http://www.cnblogs.com/math/p/4916062.html)
[8](http://www.cnblogs.com/math/p/4919227.html)
[9](http://www.cnblogs.com/math/p/4935697.html)
[**10**](http://www.cnblogs.com/math/p/4976461.html)
[11](http://www.cnblogs.com/math/p/5066939.html)
[12](http://www.cnblogs.com/math/p/5100034.html)
[13](http://www.cnblogs.com/math/p/5104644.html)

>功利主义是一种在西方影响巨大的伦理学说，其原则是“最大多数人的最大幸福”，以行为的实际功效或利益为判断行为正当与否的标准。本书系统地阐述了这一学说，分绪论、何谓功利主义、论功利主义最后制裁力、功利主义可以得到什么样的证明、论公道与功利主义之关系。

-- 引用自《[功利主义](https://book.douban.com/subject/3072490/)》

[专业主义](https://book.douban.com/subject/1790456/)
- 描述：这本书着重阐释了真正的专家必须具备的四种能力：**先见能力**、**构思能力**、**讨论的能力**、**适应矛盾**的能力，以丰富的案例和深刻的洞见警示人们*重新思考专业*的内涵与效用，培养并吸纳专业人才。
- 状态：~~已读完。~~
- 备注： <span style="color:red">分析、设计、实现、改进</span>.

``` cpp
/*
** Create or reuse a zero-terminated string, first checking in the
** cache (using the string address as a key). The cache can contain
** only zero-terminated strings, so it is safe to use 'strcmp' to
** check hits.
*/
TString *luaS_new (lua_State *L, const char *str) {
  unsigned int i = point2uint(str) % STRCACHE_N;  /* hash */
  int j;
  TString **p = G(L)->strcache[i];
  for (j = 0; j < STRCACHE_M; j++) {
    if (strcmp(str, getstr(p[j])) == 0)  /* hit? */
      return p[j];  /* that is it */
  }
  /* normal route */
  for (j = STRCACHE_M - 1; j > 0; j--)
    p[j] = p[j - 1];  /* move out last element */
  /* new element is first in the list */
  p[0] = luaS_newlstr(L, str, strlen(str));
  return p[0];
}
```

行内公式$\sqrt{3x-1}+(1+x)^2$，
行公式:
$$
\sqrt{3x-1}+(1+x)^2
$$

![](https://img5.doubanio.com/mpic/s4525326.jpg)

#### MarkDown有什么好处？
MarkDown的好处是纯文本排版，文本本身就有很强的结构化效果，即使只是在Notepad里写MarkDown，不用任何渲染，你也能看出层次结构来。比如，在QQ、微信里，你发个MarkDown的文本，别人准能看的出其中的结构层次来，这就是文本结构本身的效果。当然，如果你需要高级一点的渲染效果，随便找个支持MarkDown渲染的站点渲染下，再导出成HTML或者PDF都是很好的。博客类，像博客园都已经支持MarkDown渲染了。而临时渲染工具，像这个站点：[stackeditor](http://stackedit.io/editor)就可以直接贴上你在本地Notepad里编辑好的文本，右侧就可以看到渲染效果，你可以选择导出成纯文本、HTML、或者PDF。这个站点导出PDF是要注册帐号的，但也有办法绕过去，比如你导出带样式的HTML，然后用Chrome浏览器打开，右键打印，保存PDF，就能做到一样的效果。
