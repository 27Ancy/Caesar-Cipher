# Caesar-Cipher
This project implements a simple Caesar cipher for encryption and decryption of text. The Caesar cipher is a basic encryption technique where each letter in the plaintext is shifted by a fixed number of positions in the alphabet.

alphabets = ['a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i', 'j', 'k', 'l', 'm', 'n', 'o', 'p', 'q', 'r', 's', 't', 'u', 'v', 'w', 'x', 'y', 'z']
direction = input("Do you want to encrypt or decrypt:\n").lower()
text = input("Type your text: \n").lower()
shift = int(input("Type the number of positions you want to shift: \n"))

# Function to encrypt text
def encrypt(original_text, shift_amount):
    encrypted_text = ""
    for char in original_text:
        if char in alphabets:
            # Find the new position after the shift
            original_position = alphabets.index(char)
            new_position = (original_position + shift_amount) % 26
            encrypted_text += alphabets[new_position]
        else:
            # Non-alphabetic characters remain unchanged
            encrypted_text += char
    print(f"Encrypted text: {encrypted_text}")

# Function to decrypt text
def decrypt(original_text, shift_amount):
    decrypted_text = ""
    for char in original_text:
        if char in alphabets:
            # Find the new position after reversing the shift
            original_position = alphabets.index(char)
            new_position = (original_position - shift_amount) % 26
            decrypted_text += alphabets[new_position]
        else:
            # Non-alphabetic characters remain unchanged
            decrypted_text += char
    print(f"Decrypted text: {decrypted_text}")

# Main logic to choose between encrypt and decrypt
if direction == "encrypt":
    encrypt(text, shift)
elif direction == "decrypt":
    decrypt(text, shift)
else:
    print("Invalid option. Please choose 'encrypt' or 'decrypt'.")

