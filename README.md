- 👋 Hi, I’m @Mustafakatranci
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
Mustafakatranci/Mustafakatranci is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
import random

# Oyuncu sınıfı tanımı
class Player:
    def __init__(self, name):
        self.name = name
        self.skill = random.randint(1, 10)

    def shoot(self):
        return random.randint(1, self.skill)

# Oyun sınıfı tanımı
class FootballGame:
    def __init__(self, team1, team2):
        self.team1 = team1
        self.team2 = team2
        self.score1 = 0
        self.score2 = 0

    def play_game(self):
        print("Maç başlıyor!")
        for i in range(5):  # 5 tur oynanacak
            print(f"Tur {i+1}:")
            goal1 = self.team1.shoot()
            goal2 = self.team2.shoot()
            print(f"{self.team1.name} vuruş gücü: {goal1}")
            print(f"{self.team2.name} vuruş gücü: {goal2}")
            if goal1 > goal2:
                print(f"{self.team1.name} gol attı!")
                self.score1 += 1
            elif goal1 < goal2:
                print(f"{self.team2.name} gol attı!")
                self.score2 += 1
            else:
                print("Gol yok!")
            print("Skor: {} {} - {} {}".format(self.team1.name, self.score1, self.score2, self.team2.name))
            print()
        print("Maç sona erdi!")
        if self.score1 > self.score2:
            print(f"{self.team1.name} kazandı!")
        elif self.score1 < self.score2:
            print(f"{self.team2.name} kazandı!")
        else:
            print("Berabere!")

# Oyuncuların oluşturulması
player1 = Player("Takım 1")
player2 = Player("Takım 2")

# Oyunun oluşturulması ve başlatılması
game = FootballGame(player1, player2)
game.play_game()
