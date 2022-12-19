# python中的字典和列表

## 字典:

### 一.字典(dict)的概念:

Python字典是另一种可变容器模型,可存储任意类型对象。如字符串、数字、元组等其他容器模型
因为字典是无序的所以不支持索引和切片。

### 二.字典(dict)的定义:

> 1.一般格式:
> 格式: 字典名={元素1,元素2,...}
> *元素以键值对存在==key(键值):value(实值)*
>
> 2.空字典:
>
> ```
> 格式: 字典名={} 或者 字典名=dict()
> ```
>
> 3.举例:
>
> ```python
> dict = {"nane": "张三", "age": 20, "sex": "男"}
> dict1={}
> dict2={}
> print(dict)
> print(dict1)
> print(dict2)
> 运行结果:
> ```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200719165457495.png#pic_center)

#### 注意:

- key不可以重复,否则只会保留第一个;
- value值可以重复;
- key可以是任意的数据类型,但不能出现可变的数据类型,保证key唯一;
- key一般形式为字符串。

### 三.字典(dict)的一些基本操作:

#### 1.增:

```
格式: 字典名[new key]=new value
# 定义一个字典
dict = {"nane": "张三", "age": 20, "sex": "男"}
# 增加元素
dict["score"] = 100
print(dict)
运行结果:
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200719165856806.png#pic_center)

#### 2.删:

```
格式:del 字典名[key]
# 定义一个字典
dict = {"name": "张三", "age": 20, "sex": "男"}
#删除元素
del dict["name"]
print(dict)
运行结果:
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200719212742659.png#pic_center)



#### 3.查:

```
格式: value=字典名[key]
# 定义一个字典
dict = {"name": "张三", "age": 20, "sex": "男"}
#查找元素
value=dict["sex"]
print(value)
运行结果:
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200719213112337.png#pic_center)

#### 4.改:

```
格式: 字典名[key]=new value
# 定义一个字典
dict = {"name": "张三", "age": 20, "sex": "男"}
#修改元素
dict["name"]="李四"
print(dict)
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200719213415590.png#pic_center)



#### 注意:

```
也可以使用clear()去进行清空字典
#清空字典
dict.clear()
print(dict)
```

### 四.字典(dict)的常见操作:

| **名称**    |           **解释**            |
| ----------- | :---------------------------: |
| len()       |     测量字典中键值对个数      |
| keys()      |      返回字典中所有的key      |
| values()    |      返回包含value的列表      |
| items()     | 返回包含(键值,实值)元组的列表 |
| in \ not in |     判断key是否存在字典中     |
| 举例说明:   |                               |

```
# 定义一个字典
dict = {"name": "张三", "age": 20, "sex": "男"}
#常见操作
#len():测量字典中的键值对
print(len(dict))
#keys():返回所有的key
print(dict.keys())
#values():返回包含value的列表
print(dict.values())
#items():返回包含(键值,实值)元组的列表
print(dict.items())
#in  not in
if 20 in dict.values():
    print("我是年龄")
if "李四" not in dict.values():
    print("李四不存在")
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/2020071921493095.png#pic_center)

### 五.字典三种取值方式:

#### 1.value=字典名[key]:

```
这种是比较简单的方式,通过key值进行取值:
#字典的定义
my_dict={"name":"小红","age":20,"sex":"女"}

#1.value=字典名[key]
print(my_dict["age"])
```

#### 2.setdefault:

- **格式:`字典名.setdefault(k,value)`**
- 如果key值存在,那么返回对应字典的value,不会用到自己设置的value;
- 如果key值不存在.返回None,并且把新设置的key和value保存在字典中;
- 如果key值不存在,但设置了value,则返回设置的value;

```
#字典的定义
my_dict={"name":"小红","age":20,"sex":"女"}

#2.setdefault:  格式:字典名.setdefault(k,default)
#如果key存在返回对应的value
print(my_dict.setdefault("name"))
print(my_dict.setdefault("name","111"))
print(my_dict)
#如果key不存在,返回None,并且将设置的加入字典中
print(my_dict.setdefault("name1"))
print(my_dict.setdefault("name1","555"))
print(my_dict)
```

#### 3.get:

- **格式:`字典名.get(k,value)`**

- 如果key值存在,那么返回对应字典的value,不会用到自己设置的value;

- 如果key值不存在.返回None,但是不会把新设置的key和value保存在字典中;

- 如果key值不存在,但设置了value,则返回设置的value;

- ```
  #字典的定义
  my_dict={"name":"小红","age":20,"sex":"女"}
  
  #3.get:   格式:字典名.get(k,default)
  #如果key存在返回对应的value
  print(my_dict.get("name"))
  print(my_dict.get("name","李四"))
  #如果key不存在,返回None,设置的不加入字典中
  print(my_dict.get("name2"))
  print(my_dict.get("name2","王五"))
  print(my_dict)
  ```

  ![在这里插入图片描述](https://img-blog.csdnimg.cn/20200719220559934.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQ1MDk2Mjcz,size_16,color_FFFFFF,t_70#pic_center)

### 六.字典的[遍历](https://so.csdn.net/so/search?q=遍历&spm=1001.2101.3001.7020):

#### 1.key:

```
#1.key
for i in my_dict.keys():
    print(i)
```

#### 2.value:

```
#2.value
for i in 
my_dict.values():
    print(i)
```

#### 3.item:

```
#3.所有项(元素)  item
for i in my_dict.items():
    print(i)
```

#### 4.依次打印key和value:

```
#4.依次打印key和value,通过索引
for key,value in my_dict.items():
    print(key,value)
```

#### 5.元素值和对应的下标索引(enumerate()):

```
#5.元素值和对应的下标索引  enumerate(列表名)
for i in enumerate(my_dict):
    print(i)
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200719222843518.png#pic_center)

## 列表:

### 第一部分：列表（list）：

**列表（list）用来存储不同的数据类型，使用 [ ]**

```python
service = ['http','ssh','ftp']
```

**列表的特性：

#### 1.1：索引：**

```python
print(service[1])    ##输出第二个元素，ssh
print(service[-1])   ##输出最后一个元素，ftp
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190702083130670.png)

#### **1.2：切片：**

```python
print(service[1:])   ##打印第一个元素之后的内容
print(service[:-1])  ##打印最后一个元素之前的内容
print(service[::-1])  ##倒序输出
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190702083333487.png)

```
4、列表分片；
例如以下程序及其实现：
对于列表分片的含义需要明白，列表分片就是指将列表里面的一些列元素（不仅仅是某一个元素）进行获取或者得到，获取的规则如下所示：
Temp=m[A:B] %表示将m列表里从索引号位置为A开始的元素到B-1处元素之间的列表获取赋给temp.
```

![img](https://img2018.cnblogs.com/blog/1499410/201810/1499410-20181018020001893-1524878261.png)

#### **1.3：重复：**

```
print(service * 3)   ##输出三遍
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190702083528540.png)

#### **1.4：连接：**

```
service1 = ['nfs','samba']
print(service + service1)
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190702083637542.png)

#### **1.5：成员操作赋:**

```
print('nfs' in service)   ##判断是否存在
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190702083929891.png)

#### **1.6：迭代:[for循环遍历]**

```
for i in service:
	print(i)       ##遍历输出每个元素
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190702084228880.png)

#### **1.7列表里嵌套列表:**

```
service2 = [['abc','def','www'],[1,2,3],['mike','tony','sun']]

对其索引：print(service2[2][1])   ##第三个元素中的第二个元素
对其切片：print(service2[:][1])   ##第二个元素
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190702084706592.png)

#### 对以上内容进行一个练习：

```
题目：输入一年中的某一天，判断这一天是这一年的第几天：
User_input = input('输入：年-月-日')
Year = int(User_input.split('-')[0])   ##得到年份
Month = int(User_input.split('-')[1])  ##得到月份
Day = int(User_input.split('-')[2])    ##得到天

li = [31,28,31,30,31,30,31,31,30,31,30,31]   ##所有平年各个月份的天数
num = 0    ##记录天数
if ((Year % 4 == 0) and (Year % 100 != 0) or (Year % 400 == 0)):    ##当闰年时：
    li[1] = 29   ##将二月的天数改为29
for i in range(12):  ##遍历月份
	if Month > i + 1:   ##i从0开始，假如是5月的某一天，i循环到3停止，经过0-1-2-3四次循环，取4个月份即取1-2-3-4月的所有天
		num += li[i]   ##将1-4月总天数求和
	else:            ##退出if判断后，当下一次循环时，i=4，i+1不满足if的条件，进入else，将最后5月的第几天加入总天数中
		num += Day
		break
print('这一天是%d年的第%d天' %(Year,num))
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190702085509368.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2RkZHh4eQ==,size_16,color_FFFFFF,t_70)

### **列表的增删改查：**

#### **1.增加：**

```
往列表里增加元素:
1.print(service + ['firewalld'])   ##用连接的方式
2.service.append('firewalld')   print(service)    ##append:追加一个元素到列表中
3.extend:拉伸 追加多个元素到列表中  service.extend(['mysql','firewalld'])
4.service.insert(1,'samba')  ###在指定索引位置插入元素  ##在第二个元素的位置插入samba作为第二个元素
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190702090216248.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2RkZHh4eQ==,size_16,color_FFFFFF,t_70)

```
1、 向列表里面加元素：
向python列表里面添加元素主要有三种方法：
（1）append（）
append()对于列表的操作主要实现的是在特定的列表最后添加一个元素，并且只能一次添加一个元素，并且只能在列表最后；
  m.append(元素A)

（2）extend（）
extend（）对于列表的操作主要实现的是对于特定列表的扩展和增长，可以一次添加多个元素，不过也只能添加在列表的最后；
  m.extend([元素A，元素B，……])

（3）insert（）
insert（）对于列表的操作主要是在列表的特定位置添加想要添加的特定元素，比较常用，这里的特定位置是指元素所在列表中的位置索引号，需要注意的是这里的索引号都是从0开始的，不是从1开始的，这个大家需要特别注意。
  m.insert(A,元素B)：表示在列表m里面的第A+1处加入元素B
```

![img](https://img2018.cnblogs.com/blog/1499410/201810/1499410-20181018015812837-2059913571.png)

#### **2.删除：**

```
1.service.pop()   ##弹出最后一个元素
a = service.pop(0)  ##弹出第1个元素  ###可以将其赋值

2.service.remove('ssh') ##指定删除对象的名字  ##直接删除，不能将其赋值   ##不能指定序号，只能指定要删除对象的

3. del service  ##删除列表
del service   ##直接删除整个列表
print(service)
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190702090528650.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2RkZHh4eQ==,size_16,color_FFFFFF,t_70)

```
2、删减列表中的一些元素；
与之前python列表的添加元素相对，删减列表里面的一些元素也有三种方法：
（1）m.remove()
m.remove的作用是移除掉列表m里面的特定元素；
  m.remove(元素A)
  
（2）del m[n]
它的作用是删除掉列表里面的索引号位置为n 的元素，这里需要注意的是del是一种操作语句。
  del m[n]
  
（3）m.pop（）
它的作用是将列表m的最后一个元素返回，并且在此基础上进行删除掉
  Temp=m.pop()   %这里temp就会直接等于吗列表里最后一个元素。
  Print(m)       %这里再次输出m的时候已经是删掉最后一个元素的m列表
```

![img](https://img2018.cnblogs.com/blog/1499410/201810/1499410-20181018015858805-1021128885.png)

#### **3.赋值：**

```
1.service[0] = 'mysql'   ##通过索引 重新赋值
2.service[:2] = ['samba','iscsi']  ##通过切片给前两个元素重新赋值
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190702090751283.png)

#### **4.查看：**

```
service.count('ssh')
查看指定元素的索引值 
service.index('iscsi')    ###最小索引值
service.index('ssh',1,3)   ###从1-3中查找【第二个元素和第三个元素之间】【不取上限】
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190702090955189.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2RkZHh4eQ==,size_16,color_FFFFFF,t_70)

```
3、获取列表里面的特定元素
Temp=m[n]   %获取m列表第n+位置处的元素
```

![img](https://img2018.cnblogs.com/blog/1499410/201810/1499410-20181018015927038-1067420619.png)

#### **5.排序**

```
sort 排序
对字符串排序不区分大小写

names = ['alice','Bob','coco','Harry']
names.sort()
names      ###按照ASCLL排序   ###先排序首字母为大写的，再排序首字母是小写的
names.sort(key=str.lower)   ###对字符串排序不区分大小写，相当于将所有元素转换为小写，再排序
names.sort(key=str.upper)   ###相当于将所有元素转换为大写，再排序

乱序
li = list(range(10))   ##生成0-9，将其转换为列表形式
print(li)
import random
random.shuffle(li)   ##随机打乱
print(li)    
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190702091349600.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2RkZHh4eQ==,size_16,color_FFFFFF,t_70)

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190702091535992.png)

#### **练习：**

**修改用户登陆系统：用户名和用户密码存放在两个列表里。用admin超级用户登陆后，可以进行添加，删除，查看用户的操作。**

```
1.后台管理员admin 密码admin
2.管理员才能看到会员信息
3.会员信息包含
添加会员信息
删除会员信息
查看会员信息
退出

inuser = input('UserName: ')
inpasswd = input('Password: ')
users = ['root', 'westos']
passwds = ['123', '456']

if inuser == 'admin' and inpasswd == 'admin':
    while True:
        print("""
            菜单
        1.添加会员信息
        2.删除会员信息
        3.查看会员信息
        4.退出
        """)
        choice = input('请输入选择： ')
        if choice == '1':
            Add_Name = input('要添加的会员名: ')
            Add_Passwd = input('设置会员的密码为： ')
            users = users + [Add_Name]
            passwds = passwds + [Add_Passwd]
            print('添加成功！')

        elif choice == '2':
            Remove_Name = input('请输入要删除的会员名： ')
            if Remove_Name in users:
                Remove_Passwd = input('请输入该会员的密码： ')
                SuoYinZhi = int(users.index(Remove_Name))
                if Remove_Passwd == passwds[SuoYinZhi]:
                    users.remove(Remove_Name)
                    passwds.pop(SuoYinZhi)
                    print('成功删除！')
                else:
                    print('用户密码错误,无法验证身份,删除失败')
            else:
                print('用户错误！请输入正确的用户名')


        elif choice == '3':
            print('查看会员信息'.center(50,'*'))
            print('\t用户名\t密码')
            usercount = len(users)
            for i in range(usercount):
                print('\t%s\t%s' %(users[i],passwds[i]))


        elif choice == '4':
            exit()
        else:
            print('请输入正确选择！')

```

### 其他:

```
5、常用的列表操作符
1）+:它主要实现的是多个列表之间的拼接
常见的列表操作符
2）*：主要实现的是列表的复制和添加
3）比较>,<:主要进行数据型列表的元素比较
4）and等：；逻辑运算符，可以进行列表之间的逻辑判断
```

![img](https://img2018.cnblogs.com/blog/1499410/201810/1499410-20181018020135205-1746958657.png)

```
6、 其他常见列表操作函数：
1）m.count(A)：输出元素A在列表m里面出现的次数
2）m.index(A)：输出元素A在列表m里面的索引位置号
m.index(A,a,b)：对于列表m里面包含多个元素A时，输出在列表m索引号a-b之间的特定索引号
3）m.reverse()：将列表m进行前后的翻转，前变后，后变前
4）m.sort()：将列表m里面地数据进行从小到大的排列
5）m.sort(reverse=True)：将列表m里面地数据进行从大到小的排列

其实对于列表m里面的元素进行从大到小的排列还可以用以下方法：
 N=m.sort()
 N.reverse()
```

![img](https://img2018.cnblogs.com/blog/1499410/201810/1499410-20181018020311165-965083442.png)

```
7、 Python列表的拷贝
对于python里面如果想要进行列表的复制，具体的操作语句如下：
1） 深拷贝：
M=[A,b,a,c]
N=M[:]

2） 浅拷贝：
N=M
有人说可以直接将M赋值给N也是一样的，虽然表面看起来两者的实现效果是一样的，但是如果你要继续对N进行操作的时候就会出现问题，因为对于正确的第一种拷贝复制，它的作用是将列表M复制下来给N，如果后面对M进行操作，它对于N是完全没有影响的，而我们如果采用赋值的方式，那么在后面对M操作以后就会影响到N，N的值也会随之改变。

  综上所述，第一种python列表的拷贝方法才是真正意义上的深拷贝，而赋值操作只是一种暂时的等量代换，它属于一种浅拷贝。
```

![img](https://img2018.cnblogs.com/blog/1499410/201810/1499410-20181018020403595-1612811637.png)
