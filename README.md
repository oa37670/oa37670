def guess_number():
    print("فكر في رقم بين 1 و 999999 وسأحاول تخمينه!")
    print("أجب بـ (نعم / لا / صحيح) حسب السؤال.")

    low = 1
    high = 999999
    attempts = 0

    while low <= high:
        guess = (low + high) // 2
        attempts += 1

        print(f"هل الرقم أكبر من {guess}؟")
        response = input("(نعم / لا / صحيح): ").strip().lower()

        if response == "نعم":
            low = guess + 1
        elif response == "لا":
            high = guess - 1
        elif response == "صحيح":
            print(f"تم التخمين! الرقم هو {guess}، بعد {attempts} محاولة.")
            return
        else:
            print("الرجاء إدخال (نعم / لا / صحيح).")

    print("لم أتمكن من تخمين الرقم. هل كنت صادقًا؟")

guess_number()
