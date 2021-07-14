---
layout: single
title: "미니 프로젝트"
---

[설계]
도박

룰렛,로또,야바위
세 게임 중 선택
룰렛은 같은 숫자 3 개 나오면 당첨
로또는 숫자 6개 입력해서 6개 동일하면 1등, 5개 동일하면 2등 ….
야바위는 1 2 3 중 하나 입력. 해당 숫자가 당첨일 시 당첨




~~~python
SeedMoney=1000000

while SeedMoney>0:
  GameType=int(input("1=룰렛, 2=로또, 3=야바위: "))
  GameMoney=int(input("돈 입력: "))
  SeedMoney-=GameMoney
  if GameType==1:
    import random
    Game1Number1=[1,2,3,4,5,6]
    Game1Number2=[1,2,3,4,5,6]
    Game1Number3=[1,2,3,4,5,6]
    random.choice(Game1Number1)
    random.choice(Game1Number2)
    random.choice(Game1Number3)
    uno=random.choice(Game1Number1)
    dos=random.choice(Game1Number2)
    tres=random.choice(Game1Number3)
    if uno==dos==tres:
      GameMoney*=7
      print("{},{},{}".format(uno, dos, tres))
      print("당첨! {}원!".format(GameMoney))
      SeedMoney+=GameMoney
      print("잔액 {}원".format(SeedMoney))
    else:
      GameMoney*=0
      print("{}{}{}".format(uno, dos, tres))
      print("꽝~ 당첨금{}원~".format(GameMoney))
      SeedMoney+=GameMoney
      print("잔액 {}원".format(SeedMoney))
  elif GameType==2:
    import random
  
    random.randrange(1,46)
    print("미완")
  elif GameType==3:
    import random
    Game3=random.randrange(1,4)
    Player=int(input("1~3 중 당첨일 것 같은 숫자 입력: "))
    if Game3==Player:
      GameMoney*=2
      print("내가 고른 숫자:{}".format(Player))
      print("당첨 숫자:{}".format(Game3))
      print("당첨! {}원!".format(GameMoney))
      SeedMoney+=GameMoney
      print("잔액 {}원".format(SeedMoney))
    else:
      GameMoney*=0
      print("내가 고른 숫자:{}".format(Player))
      print("당첨 숫자:{}".format(Game3))
      print("꽝~ 당첨금{}원~".format(GameMoney))
      SeedMoney+=GameMoney
      print("잔액 {}원".format(SeedMoney))
  else:
    print("프로그램에 존재하지 않는 종류의 게임입니다. 그만하시겠습니까?")
    SeedMoney+=GameMoney
    Answer=int(input("종료하시려면 1번을, 계속하시려면 2번을 눌러주세요: "))
    if Answer==1:
      print("종료 금액 {}원. 게임이 종료되었습니다.".format(SeedMoney))
      break
    else:
      print("..")
~~~
