```ruby
import random
def yourturn(s):
    b=0
    you=input('당신차례입니다.\n%s부터 몇 개를 외치시겠습니까?' %s)
    if not int(you)>3:
        while b<int(you):
            b=b+1
            a = b + s
            print('당신 '+str(a))
            if a==31:
                print('AI의 승리!\n분발하세요.')
    return a

def aiturn(s):
    print('AI 차례입니다.')
    l=[2,6,10,14,18,22,26,30]
    b=0
    while b<3:
        b=b+1
        d = 0
        if s+b in l:
            while d<b:
                d=d+1
                print('AI '+str(s+d))
            a=s+d
            break
        elif b==3:
            c=random.randint(1,3)
            while d<c:
                d=d+1
                if s + d >= 31:
                    print('AI 31')
                    print('당신의 승리!\n축하드립니다!')
                print('AI '+str(s+d))
            a=s+d
    return a

#코드 시작
a=0
b=0
while 1:
    c = input('당신부터 하시겠습니까? (yes/no)')
    while 1:
        b=b+1
        print('<'+str(b)+'턴>----------------------------------')
        if c == 'yes':
            if b%2 == 1:
                a=yourturn(a)
            else:
                a=aiturn(a)
        elif c=='no':
            if b%2 == 1:
                a=aiturn(a)
            else:
                a=yourturn(a)
        if a>=31:
            break
    d=input('재도전 하시겠습니까? yes/no')
    if d=='no':
        print('수고하셨습니다.')
        break
    else:
        a=0
        b=0
```
