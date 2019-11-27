# NeShellOperator Shell之运算符

## 一、运算符
```bash
a=20
b=10
```
### 1.1 算术运算符
运算符 | 说明  | 举例  
--    | --   | --  
+     | 加法  | `expr $a + $b`结果为30  
-     | 减法  | `expr $a - $b`结果为10  
*     | 乘法  | `expr $a \* $b`结果为200  
/     | 除法  | `expr $a / $b`结果为2  
%     | 取余  | `expr $a % $b`结果为0  
=     | 赋值  | a=$b 把变量b的值赋给a  
==    | 相等  | 用于比较两个数字，相同返回true [ $a == $b ]返回false  
!=    | 不相等 | 用于比较两个数字，不相同则返回true [ $a != $b ]返回true  
**注意：**  
条件表达式要放在方括号之间，并且要有空格，例如：[$a==$b]是错误的，必须写成[ $a == $b ]

### 1.2 关系运算符
运算符 | 说明                                         | 举例
--    | -------------------------------------------  | --
-eq   | 检测两个数是否相等，相等返回true                 | [ $a -eq $b ]返回false
-ne   | 检测两个数是否不相等，不相等返回true              | [ $a -ne $b ]返回true
-gt   | 检测左边的数是否大于右边的，如果是，则返回true     | [ $a -gt $b ]返回true
-lt   | 检测左边的数是否小于右边的，如果是，则返回true     | [ $a -lt $b ]返回false
-ge   | 检测左边的数是否大于等于右边的，如果是，则返回true  | [ $a -ge $b ]返回true
-le   | 检测左边的数是否小于等于右边的，如果是，则返回true  | [ $a -le $b ]返回false

### 1.3 布尔运算符
运算符 | 说明                                | 举例
--    | ----------------------------------- | --
!    | 非运算，表达式为true,否则返回true       | [ !false ] 返回true
-o   | 或运算，有一个表达式为true，则返回true   | [ $a -le 20 -o $b -gt 100 ]返回true
-a   | 与运算，两个表达式都为true,才返回true    | [ $a -le 20 -o $b -gt 100 ]返回false

### 1.4 逻辑运算符
运算符 | 说明      | 举例
--    | -------   | --
&&    | 逻辑的 AND | [[ $a -lt 100 && $b -gt 100 ]] 返回false  
||    | 逻辑的OR   | [[ $a -lt 100 || $b -gt 100 ]] 返回true  

### 1.5 字符串运算符
运算符 | 说明                                 | 举例
--    | ----------------------------------- | --
=     | 检测两个字符串是否相等，相等返回true     | [ $a = $b ]返回false
!=    | 检测两个字符串是否不相等，不相等返回true  | [ $a != $b ]返回true
-z    | 检测字符串长度是否为0，为0返回true       | [ -z $a ]返回false
-n    | 检测字符串长度是否不为0，不为0返回true    | [ -n "$a" ]返回true
$     | 检测字符串是否为空，不为空返回true        | [ $a ]返回true

### 1.2 文件测试运算符
运算符   | 说明                                                           | 举例
--      | -------------------------------------------------------------  | --
-b file | 检测文件是否是块设备文件，如果是，则返回true                         | [ -b $file ]返回false
-c file | 检测文件是否是字符设备文件，如果是，则返回true                       | [ -c $file ]返回false
-d file | 检测文件是否是目录，如果是，则返回true                              | [ -d $file ]返回false
-f file | 检测文件是否是普通文件（既不是目录，也不是设备文件），如果是，则返回true | [ -f $file ]返回true
-g file | 检测文件是否设置了 SGID 位，如果是，则返回true                      | [ -g $file ]返回false
-k file | 检测文件是否设置了粘着位（Sticky Bit），如果是，则返回true           | [ -k $file ]返回false
-p file | 检测文件是否是有名管道，如果是，则返回true                          | [ -p $file ]返回false
-u file | 检测文件是否设置 SUID 位，如果是，则返回true                       | [ -u $file ]返回false
-r file | 检测文件是否可读，如果是，则返回true                               | [ -r $file ]返回true
-w file | 检测文件是否可写，如果是，则返回true                               | [ -w $file ]返回true
-x file | 检测文件是否可执行，如果是，则返回true                             | [ -x $file ]返回true
-s file | 检测文件是否是否为空（文件大小是否大于0），不为空则返回true           | [ -s $file ]返回true
-e file | 检测文件（包含目录）是否存在，如果是，则返回true                    | [ -e $file ]返回true


![image](https://github.com/tianyalu/NeMakefile/blob/master/show/make_file_fun_param.png)  

