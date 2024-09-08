def caesar_cipher(message, shift, mode='encrypt'):
    result = ""


    if mode == 'decrypt':
        shift = -shift


    for char in message:
        if char.isalpha():
            shift_base = 65 if char.isupper() else 97
            result += chr((ord(char) - shift_base + shift) % 26 + shift_base)
        else:
            result += char

    return result

def main():
    print("Caesar Cipher Program")
    mode = input("Do you want to 'encrypt' or 'decrypt' the message? ").strip().lower()
    message = input("Enter your message: ").strip()
    shift = int(input("Enter the shift value: ").strip())

    if mode in ['encrypt', 'decrypt']:
        result = caesar_cipher(message, shift, mode)
        print(f"The resulting message is: {result}")
    else:
        print("Invalid mode selected. Please choose either 'encrypt' or 'decrypt'.")

if __name__ == "__main__":
    main()
