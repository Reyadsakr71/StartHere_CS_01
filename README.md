# StartHere_CS_01
How to implement a CAESAR CiPHER with Python

def encrypt(plaintext, shift):
    encrypted_message = ""
    for char in plaintext:
        # Encrypt uppercase letters
        if char.isupper():
            encrypted_message += chr((ord(char) + shift - 65) % 26 + 65)
        # Encrypt lowercase letters
        elif char.islower():
            encrypted_message += chr((ord(char) + shift - 97) % 26 + 97)
        # Leave non-alphabetic characters unchanged
        else:
            encrypted_message += char
    return encrypted_message


def decrypt(encrypted_message, shift):
    decrypted_message = ""
    for char in encrypted_message:
        # Decrypt uppercase letters
        if char.isupper():
            decrypted_message += chr((ord(char) - shift - 65) % 26 + 65)
        # Decrypt lowercase letters
        elif char.islower():
            decrypted_message += chr((ord(char) - shift - 97) % 26 + 97)
        # Leave non-alphabetic characters unchanged
        else:
            decrypted_message += char
    return decrypted_message


# Main function to get input from the user and perform encryption/decryption
def main():
    message = input("Enter the message to encrypt: ")
    shift = int(input("Enter the shift value for encryption: "))
    # Encrypt the message
    encrypted = encrypt(message, shift)
    print(f"Encrypted message: {encrypted}")
    # Decrypt the message
    decrypted = decrypt(encrypted, shift)
    print(f"Decrypted message: {decrypted}")


# Run the main function
if __name__ == "__main__":
    main()

