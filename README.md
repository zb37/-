# -
小学四则运算题升级
import random
from fractions import Fraction
def zs():

    fz= ['＋', '－', '×', '÷']#随机选择运算法则

    f= random.randint(0, 3)

    n1 = random.randint(0,99)

    n2 = random.randint(0,99)

    result = 0

    if f== 0:#加法

       result  = n1 + n2

    elif f == 1:#减法，要先比较大小，防止输出负数

        n1, n2 = max(n1, n2), min(n1, n2)

        result  = n1 - n2

    elif f== 2:#乘法

        result  = n1 * n2

    elif f == 3:#除法
        n2 = random.randint(1,99)

        result  = n1 / n2

    print(n1, fz[f], n2, '= ', end='')

    return result
def xs():

    fz= ['＋', '－', '×', '÷']

    f= random.randint(0, 3)

    x1 = random.randint(0,20)#生成2个真分数，约分通分较复杂所以数值设的较小
    if x1==0:
        x2 = random.randint(1,20)
    else:
        x2 = random.randint(x1,20)
    x3 = random.randint(0,20)
    if x3==0:
        x4 = random.randint(1,20)
    else:
        x4 = random.randint(x3,20)
    n1 = Fraction(x1,x2)
    n2 = Fraction(x3,x4)
    result = 0

    if f== 0:#加法

       result  = n1 + n2

    elif f == 1:#减法，要先比较大小，防止输出负数

        n1, n2 = max(n1, n2), min(n1, n2)

        result  = n1 - n2

    elif f== 2:#乘法

        result  = n1 * n2

    elif f == 3:#除法

        result  = n1 / n2

    print(n1, fz[f], n2, '= ', end='')

    return result
def chuti():
    x= random.randint(1,2)
    if x==1:
        result=str(zs())
    elif x==2:
        result=str(xs())
    return result

#制作题库

def test():
    print('输入所需要的题目数量')

    n=int(input())

    result =[]

    m=0

    while m<=(n-1):

        print(m+1,end='、')
        result .append(chuti())
        print(' ')
        m=m+1

    m=0

    print('对应的答案：')

    while m<=(n-1):

        print(m+1,'、',result [m])

        m=m+1



print('选择想要的模式')

print('1、进行单道四则运算')

print('2、制作题库')

n=int(input())

#当输入1时，进行单道四则运算

if n==1:

    while True:
        x= random.randint(1,2)#随机选择整数或者分数的题型
        if x==1:
            result=str(zs())
            y=input()
            if y==result:
                print('答对了')
            else:
                print('答错了，正确答案是：',result)
        elif x==2:
            result=str(xs())
            y=input()
            if y==result:
                print('答对了')
            else:
                print('答错了，正确答案是：',result)
#当输入2时，进行制作题库

if n==2:

     test()
