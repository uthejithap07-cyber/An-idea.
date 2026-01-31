# An-idea.
# PEER-CARE : Peer Led Mental Health Support System
# Prototype for Ideathon

# Threshold values
ANXIETY_THRESHOLD = 7
DEPRESSION_THRESHOLD = 7
SCREEN_TIME_THRESHOLD = 6  # hours per day

def mood_check():
    print("\n--- Mood Check-In ---")
    anxiety = int(input("Rate your anxiety level (0-10): "))
    depression = int(input("Rate your depression level (0-10): "))
    screen_time = float(input("Daily screen time (hours): "))

    analyze_risk(anxiety, depression, screen_time)

def analyze_risk(anxiety, depression, screen_time):
    print("\n--- Analysis Result ---")

    if anxiety >= ANXIETY_THRESHOLD:
        print("⚠ High Anxiety Detected")
        notify_peer("Anxiety")

    if depression >= DEPRESSION_THRESHOLD:
        print("⚠ High Depression Detected")
        notify_peer("Depression")

    if screen_time >= SCREEN_TIME_THRESHOLD:
        print("⚠ Digital Addiction Risk Detected")
        suggest_digital_detox()

    if anxiety < 7 and depression < 7 and screen_time < 6:
        print("✅ You are doing well. Keep maintaining healthy habits!")

def notify_peer(issue):
    print(f"📩 Peer Support Alert Sent for {issue}")
    print("👥 Assigned peer will check in with the user")

def suggest_digital_detox():
    print("📵 Suggested Actions:")
    print("- Take a 30-minute screen break")
    print("- Go for a walk or do breathing exercises")
    print("- Join peer digital detox challenge")

def main():
    print("=================================")
    print("  PEER-CARE Mental Health System  ")
    print("=================================")

    while True:
        print("\n1. Mood Check-In")
        print("2. Exit")
        choice = input("Choose an option: ")

        if choice == "1":
            mood_check()
        elif choice == "2":
            print("Thank you for using PEER-CARE ❤️")
            break
        else:
            print("Invalid choice. Try again.")

# Run the program
main()
