# PRODIGY_CS_01
def caesar_cipher(text, shift, mode):
result = ""
for char in text:
if char.isalpha():
shift_base = 65 if char.isupper() else 97
shift_direction = shift if mode == 'encrypt' else -shift
new_char = chr((ord(char) - shift_base + shift_direction) % 26 + shift_base)
result += new_char
else:
result += char
return result
def main():
print("Caesar Cipher Program")
action = input("Would you like to (E)ncrypt or (D)ecrypt a message? ").lower()
if action in ['e', 'd']:
message = input("Enter your message: ")
shift = int(input("Enter shift value (1-25): "))
mode = 'encrypt' if action == 'e' else 'decrypt
result = caesar_cipher(message, shift, mode)
print(f"The {mode}ed message is: {result}")
else:
print("Invalid choice. Please enter 'E' to encrypt or 'D' to decrypt.")
if __name__ == "__main__":
main()	
