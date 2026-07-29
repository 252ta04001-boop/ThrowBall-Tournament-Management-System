# ==========================================================
#        THROW BALL TOURNAMENT MANAGEMENT SYSTEM
#               Developed using Python
# ==========================================================

print("=" * 60)
print("        WELCOME TO THROW BALL TOURNAMENT")
print("=" * 60)

# ---------------- TEAM DETAILS ----------------

team1 = input("Enter Team 1 Name : ")
team2 = input("Enter Team 2 Name : ")

print("\nEnter Player Details")

players1 = []
players2 = []

print(f"\nPlayers of {team1}")
for i in range(1, 7):
    player = input(f"Player {i}: ")
    players1.append(player)

print(f"\nPlayers of {team2}")
for i in range(1, 7):
    player = input(f"Player {i}: ")
    players2.append(player)

score1 = 0
score2 = 0

sets1 = 0
sets2 = 0

total_points1 = 0
total_points2 = 0

match_history = []

# ---------------- MATCH START ----------------

print("\nMatch Starts...")
print("First team to score 15 points wins the set.")
print("Best of 3 Sets")

for set_no in range(1, 4):

    print("\n" + "=" * 40)
    print("SET", set_no)
    print("=" * 40)

    score1 = 0
    score2 = 0

    while True:

        print("\nMenu")
        print("1. Point for", team1)
        print("2. Point for", team2)
        print("3. Show Live Score")
        print("4. End Current Set")

        choice = input("Enter Choice : ")

        if choice == "1":
            score1 += 1
            total_points1 += 1

        elif choice == "2":
            score2 += 1
            total_points2 += 1

        elif choice == "3":
            print("-----------------------")
            print(team1, ":", score1)
            print(team2, ":", score2)
            print("-----------------------")

        elif choice == "4":
            break

        else:
            print("Invalid Choice")
            continue

        if score1 >= 15:
            print("\n", team1, "wins Set", set_no)
            sets1 += 1
            break

        elif score2 >= 15:
            print("\n", team2, "wins Set", set_no)
            sets2 += 1
            break

    match_history.append((set_no, score1, score2))

    if sets1 == 2 or sets2 == 2:
        break

# ---------------- MATCH SUMMARY ----------------

print("\n")
print("=" * 60)
print("MATCH SUMMARY")
print("=" * 60)

print("Teams")
print(team1, "VS", team2)

print("\nPlayers of", team1)
for player in players1:
    print("-", player)

print("\nPlayers of", team2)
for player in players2:
    print("-", player)

print("\nSet Results")

for result in match_history:
    print("Set", result[0], ":", team1, result[1], "-", result[2], team2)

print("\nTotal Sets Won")
print(team1, ":", sets1)
print(team2, ":", sets2)

print("\nTotal Points")
print(team1, ":", total_points1)
print(team2, ":", total_points2)

if sets1 > sets2:
    winner = team1
else:
    winner = team2

print("\n🏆 TOURNAMENT WINNER :", winner)

# ---------------- PERFORMANCE ----------------

print("\nPerformance Analysis")

if total_points1 > total_points2:
    print(team1, "scored the highest points in the match.")
elif total_points2 > total_points1:
    print(team2, "scored the highest points in the match.")
else:
    print("Both teams scored equal points.")

print("\nFair Play Message")
print("Respect your teammates.")
print("Respect your opponents.")
print("Play with sportsmanship.")

print("\nThank you for using Throw Ball Tournament Management System.")
print("=" * 60)
