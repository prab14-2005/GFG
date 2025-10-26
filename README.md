# GFG
"""
Diwali Diya Counting Pattern 
"""

import time

def print_pattern_left_aligned(n):
    """Left-aligned increasing pattern."""
    print("\n🪔 Left-Aligned Pattern 🪔")
    print("─" * 40)
    for i in range(1, n + 1):
        print("★ " * i)

def print_pattern_right_aligned(n):
    """Right-aligned increasing pattern."""
    print("\n🪔 Right-Aligned Pattern 🪔")
    print("─" * 40)
    for i in range(1, n + 1):
        spaces = "  " * (n - i)
        diyas = "★ " * i
        print(spaces + diyas)

def print_pattern_hollow_pyramid(n):
    """Hollow pyramid pattern."""
    print("\n🪔 Hollow Pyramid Pattern 🪔")
    print("─" * 40)
    for i in range(1, n + 1):
        spaces = " " * (n - i) * 2
        if i == 1:
            print(spaces + "★")
        elif i == n:
            print("★ " * i)
        else:
            middle_spaces = "  " * (i - 2)
            print(spaces + "★ " + middle_spaces + " ★")

def print_pattern_wave(n):
    """Wave/zigzag pattern."""
    print("\n🪔 Wave Pattern 🪔")
    print("─" * 40)
    for i in range(1, n + 1):
        if i % 2 == 1:
            # Odd rows: left-aligned
            print("★ " * i)
        else:
            # Even rows: right-aligned
            spaces = "  " * (n - i)
            print(spaces + "★ " * i)

def print_pattern_hourglass(n):
    """Hourglass/double triangle pattern."""
    print("\n🪔 Hourglass Pattern 🪔")
    print("─" * 40)
    # Upper triangle (decreasing)
    for i in range(n, 0, -1):
        spaces = "  " * (n - i)
        diyas = "★ " * i
        print(spaces + diyas)
    # Lower triangle (increasing)
    for i in range(2, n + 1):
        spaces = "  " * (n - i)
        diyas = "★ " * i
        print(spaces + diyas)

def print_pattern_christmas_tree(n):
    """Christmas tree style with trunk."""
    print("\n🪔 Christmas Tree Pattern 🪔")
    print("─" * 40)
    # Tree top
    for i in range(1, n + 1):
        spaces = " " * (n - i) * 2
        diyas = "★ " * i
        print(spaces + diyas)
    # Tree trunk
    trunk_spaces = " " * (n - 1) * 2
    for _ in range(2):
        print(trunk_spaces + "║")

def print_pattern_alternate_symbols(n):
    """Pattern with alternating symbols."""
    print("\n🪔 Alternate Symbol Pattern 🪔")
    print("─" * 40)
    symbols = ['★', '✦', '✧', '⭐', '🪔']
    for i in range(1, n + 1):
        symbol = symbols[(i - 1) % len(symbols)]
        print(f"{symbol} " * i)

def print_pattern_rainbow(n):
    """Rainbow colored pyramid."""
    print("\n🪔 Rainbow Pattern 🪔")
    print("─" * 40)
    colors = [
        '\033[91m',  # Red
        '\033[93m',  # Yellow
        '\033[92m',  # Green
        '\033[96m',  # Cyan
        '\033[94m',  # Blue
        '\033[95m',  # Magenta
    ]
    reset = '\033[0m'
    
    for i in range(1, n + 1):
        spaces = " " * (n - i) * 2
        color = colors[(i - 1) % len(colors)]
        diyas = f"{color}★{reset} " * i
        print(spaces + diyas)

def print_pattern_bordered_box(n):
    """Pattern inside a decorative box."""
    print("\n🪔 Bordered Box Pattern 🪔")
    width = n * 3 + 4
    
    # Top border
    print("╔" + "═" * width + "╗")
    
    # Pattern rows
    for i in range(1, n + 1):
        diyas = "★ " * i
        padding = " " * (width - len(diyas) - 1)
        print(f"║ {diyas}{padding}║")
    
    # Bottom border
    print("╚" + "═" * width + "╝")

def print_pattern_with_animation(n):
    """Animated pattern (prints row by row with delay)."""
    print("\n🪔 Animated Pattern 🪔")
    print("─" * 40)
    print("(Watch it grow...)\n")
    
    for i in range(1, n + 1):
        spaces = " " * (n - i) * 2
        diyas = "★ " * i
        print(spaces + diyas)
        time.sleep(0.3)  # 300ms delay

def main():
    """Main function with enhanced menu."""
    print("\n" + "═" * 70)
    print("✨ DIWALI DIYA PATTERN GENERATOR ✨".center(70))
    print("═" * 70)
    
    # Input validation
    while True:
        try:
            n = int(input("\n🪔 Enter number of rows (3-15): "))
            if 3 <= n <= 15:
                break
            else:
                print("⚠️  Please enter a number between 3 and 15!")
        except ValueError:
            print("⚠️  Invalid input! Please enter a valid number.")
    
    # Enhanced menu
    print("\n" + "╔" + "═" * 68 + "╗")
    print("║" + " CHOOSE YOUR PATTERN STYLE ".center(68) + "║")
    print("╠" + "═" * 68 + "╣")
    print("║  1. Left-Aligned Pattern          6. Christmas Tree Pattern    ║")
    print("║  2. Right-Aligned Pattern         7. Alternate Symbol Pattern  ║")
    print("║  3. Hollow Pyramid Pattern        8. Rainbow Pattern           ║")
    print("║  4. Wave/Zigzag Pattern           9. Bordered Box Pattern      ║")
    print("║  5. Hourglass Pattern            10. Animated Pattern          ║")
    print("║                                  11. ALL PATTERNS              ║")
    print("╚" + "═" * 68 + "╝")
    
    while True:
        try:
            choice = int(input("\n🎯 Enter your choice (1-11): "))
            if 1 <= choice <= 11:
                break
            else:
                print("⚠️  Please choose between 1-11!")
        except ValueError:
            print("⚠️  Invalid choice!")
    
    print("\n" + "═" * 70)
    
    # Execute pattern based on choice
    patterns = {
        1: print_pattern_left_aligned,
        2: print_pattern_right_aligned,
        3: print_pattern_hollow_pyramid,
        4: print_pattern_wave,
        5: print_pattern_hourglass,
        6: print_pattern_christmas_tree,
        7: print_pattern_alternate_symbols,
        8: print_pattern_rainbow,
        9: print_pattern_bordered_box,
        10: print_pattern_with_animation,
    }
    
    if choice == 11:
        # Show all patterns
        for func in patterns.values():
            func(n)
            print()
    else:
        patterns[choice](n)
    
    print("\n" + "═" * 70)
    print("✨ Happy Diwali! ✨".center(70))
    print("═" * 70)

if __name__ == "__main__":
    main()
