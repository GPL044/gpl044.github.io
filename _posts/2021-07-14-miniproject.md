---
layout: single
title: "미니 프로젝트"
---

[요구사항]
도박 예방을 위한 도박 체험 프로그램
도박장의 여러 게임들을 체험 할 수 있게 한다.

[설계]
도박장

룰렛,인디언포커,야바위
세 게임 중 선택
룰렛은 같은 숫자 3 개 나오면 당첨
인디언포커는 1~10까지 숫자 카드 2개씩. 카드더미에서 상대와 나 1장씩 뽑고 상대의 패만 보고 배팅
야바위는 1 2 3 중 하나 입력. 해당 숫자가 당첨일 시 당첨




~~~python
SeedMoney=0
SeedMoney=int(input("돈: "))
while SeedMoney>0:
  GameType=int(input("1=룰렛, 2=인디언포커, 3=야바위: "))
  
  if GameType==1:
    GameMoney=int(input("돈 입력: "))
    SeedMoney-=GameMoney
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
    Blindmansbluff=[1, 1, 2, 2, 3, 3, 4, 4, 5, 5,6,6,7,7,8,8,9,9,10,10]
    Ien=int(len(Blindmansbluff))
    while Ien>0:
      import random
      PlayerCard=random.choice(Blindmansbluff)
      Blindmansbluff.remove(PlayerCard)
      ComputerCard=random.choice(Blindmansbluff)
      Blindmansbluff.remove(ComputerCard)
      print("상대의 패:{}".format(ComputerCard))
      Chip=int(input("배팅할 배팅머니를 입력: "))
      SeedMoney-=Chip
      Gamble=0
      Gamble+=Chip*2
      if PlayerCard>ComputerCard:
        print("U WIN!")
        print("Ur Card:{}, Com's Card:{}".format(PlayerCard, ComputerCard))
        SeedMoney+=Gamble
        Gamble-=Gamble
        print("잔액{}원".format(SeedMoney))
      elif PlayerCard==ComputerCard:
        print("DRAW!")
        print("Ur Card:{}, Com's Card:{}".format(PlayerCard, ComputerCard))
        print("다음 게임 승리 시 이번 게임의 배팅머니를 가져갑니다.")
      else:
        print("U Lose")
        print("Ur Card:{}, Com's Card:{}".format(PlayerCard, ComputerCard))
        print("잔액{}원".format(SeedMoney))
    else:
      break
      
  elif GameType==3:
    GameMoney=int(input("돈 입력: "))
    SeedMoney-=GameMoney
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
else:
  print("탕진하셨습니다.")
~~~
