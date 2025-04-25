import pyotp
import time

# إنشاء مفتاح سري (يتم حفظه في قاعدة البيانات عادة)
secret = pyotp.random_base32()
print(f"المفتاح السري (احفظه): {secret}")

# إنشاء كائن TOTP
totp = pyotp.TOTP(secret)

# طباعة رمز التحقق الحالي
print("رمز التحقق الحالي:", totp.now())

# التحقق من رمز (يحاكي ما يفعله السيرفر)
user_input = input("أدخل رمز التحقق: ")
if totp.verify(user_input):
    print("الرمز صحيح!")
else:
    print("رمز خاطئ.")
