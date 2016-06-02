# SNL-Compiler
SNL(Small Nested Language) Compiler.  Maven jUnit Tokenizer Lexer Syntax Parser.  
编译原理 词法分析 语法分析  

### 进展
- 2016-05-24 开始构思
- 2016-05-27 查资料
- 2016-05-28 1.开始编码
- 2016-05-28 2.初步完成词法分析，开始写语法分析
- 2016-05-29 开始递归下降
- 2016-05-30 递归下降基本完成
- 2016-05-31 1.完成递归下降
- 2016-05-31 2.语法树的输出(竖版)
- 2016-05-31 3.添加主程序，使用 Commons-Cli 解析命令行参数
- 2016-05-31 4.添加几个发现的错误[如下](#勘误)
- 2016-06-01 开始 LL1  
- 2016-06-02 1.初步完成 LL1  
- 2016-06-02 2.增加自动识别文件编码。修复标识符结点值错误的 Bug.  
- 2016-06-02 3.查错，基本上完成了.  

### 参考书籍
《编译程序的设计与实现》刘磊 金英 张晶 张荷花 单郸；高等教育出版社，ISBN 978-7-04-014620-7.  

#### 勘误
- [编译程序的设计与实现(书稿电子版).pdf](book.pdf) (侵删)
- [《编译程序的设计与实现》随书光盘](TP314-43L643.iso) (侵删)

其中《编译程序的设计与实现》:

1. 第 10 页，产生式 (43) 应为：<code>ProcDecMore -> ProcDec</code>. (而不是 ProcDeclare)  
2. 第 63 页，产生式 (67) Predict 集应为 <code>[</code> (左中括号), <code>.</code> (句点), <code>:=</code> (赋值号).  
3. 第 64 页，产生式 (93) Predict 集应包含 <code>]</code> (右中括号).  
4. 第 55 页，例子中 <code>v2:='a';</code> 只能通过词法分析，而**不能通过语法分析**，因为按照给定的产生式(<code>Exp</code>)不能推出字符型。
5. 第 10 页，产生式 (42), (43) 完全多余。可以去掉，并且把产生式 (41) 右部的 <code>ProcDecMore</code> 改为 <code>ProcDecpart</code>. 
6. 第 10 页，产生式 (48), 预测符集应为 <code>)</code> (右括号)，而不是左括号。(第 62 页)