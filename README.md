# Morse-Code-Translator
this is a morse code translator, you can decode morse, or encode text to it, your choice! Talk in a secret way? All of it is Here. Quote of the post: 'im not late, just really early for tomorrow'
# Morse code dictionary for decoding
Morse_Code_Dictionary = {
    ".-": "A", "-...": "B", "-.-.": "C", "-..": "D", ".": "E",
    "..-.": "F", "--.": "G", "....": "H", "..": "I", ".---": "J",
    "-.-": "K", ".-..": "L", "--": "M", "-.": "N", "---": "O",
    ".--.": "P", "--.-": "Q", ".-.": "R", "...": "S", "-": "T",
    "..-": "U", "...-": "V", ".--": "W", "-..-": "X", "-.--": "Y",
    "--..": "Z", "-----": "0", ".----": "1", "..---": "2",
    "...--": "3", "....-": "4", ".....": "5", "-....": "6",
    "--...": "7", "---..": "8", "----.": "9", "/": " "
}

# Reverse dictionary for encoding
Text_To_Morse = {value: key for key, value in Morse_Code_Dictionary.items()}

# Encode text to Morse code
def encode_to_morse(text):
    return ' '.join(Text_To_Morse.get(char.upper(), "?") if char != " " else "/" for char in text)

# Decode Morse code to text
def decode_from_morse(code):
    return ''.join(Morse_Code_Dictionary.get(symbol, "?") for symbol in code.strip().split())

# Single interaction
def morse_translator():
    print("🔠 Morse Code Translator 🔢")
    print("1. Encode text to Morse")
    print("2. Decode Morse to text")
    choice = input("Choose an option (1 or 2): ").strip()

    if choice == '1':
        text = input("Enter text to encode: ")
        print("Morse output:")
        print(encode_to_morse(text))

    elif choice == '2':
        morse_input = input("Enter Morse code (space-separated, '/' between words): ")
        print("Decoded message:")
        print(decode_from_morse(morse_input))

    else:
        print("Invalid choice. Please enter 1 or 2.")

# Run the translator once
if __name__ == "__main__":
    morse_translator()
