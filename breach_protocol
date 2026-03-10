import random

def breach_protocol():
    # 1. Game Setup
    # Player starts at [0,0], Goal is at [4,4]
    player = [0, 0]
    goal = [4, 4]
    cpu_cycles = 15
    
    # Generate random walls that aren't on the start or goal
    walls = []
    while len(walls) < 6:
        w = [random.randint(0, 4), random.randint(0, 4)]
        if w != player and w != goal and w not in walls:
            walls.append(w)

    print("--- 💻 NETRUNNER: BREACH PROTOCOL 💻 ---")
    print("Goal: Reach the CORE [C] before CPU cycles hit 0.")
    print("Avoid the WALLS [#].")

    # 2. Game Loop
    while cpu_cycles > 0:
        # Render the Grid
        print(f"\nCPU CYCLES: {cpu_cycles}")
        for y in range(5):
            row = ""
            for x in range(5):
                if [x, y] == player:
                    row += " [P] "
                elif [x, y] == goal:
                    row += " [C] "
                elif [x, y] in walls:
                    row += " [#] "
                else:
                    row += "  .  "
            print(row)

        if player == goal:
            print("\n🔓 ACCESS GRANTED! System breached successfully.")
            return

        # 3. Input & Movement
        move = input("\nDirection (W/A/S/D): ").lower().strip()
        new_pos = list(player)

        if move == 'w': new_pos[1] -= 1
        elif move == 's': new_pos[1] += 1
        elif move == 'a': new_pos[0] -= 1
        elif move == 'd': new_pos[0] += 1
        else: continue

        # 4. Collision & Boundary Logic
        if 0 <= new_pos[0] <= 4 and 0 <= new_pos[1] <= 4:
            if new_pos in walls:
                print("💥 CONNECTION BLOCKED: Physical wall detected.")
            else:
                player = new_pos
                cpu_cycles -= 1
        else:
            print("🚫 OUT OF BOUNDS: Stay within the grid.")

    print(f"\n💀 CONNECTION LOST: CPU depleted. The core was at {goal}.")

breach_protocol()
