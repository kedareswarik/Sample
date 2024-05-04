import random
import string

def generate_code(length=8, exclude_chars='', existing_codes=set()):
    characters = ''.join(set(string.ascii_letters + string.digits) - set(exclude_chars))
    code = ''.join(random.choice(characters) for _ in range(length))
    
    # Ensure the generated code is unique
    while code in existing_codes:
        code = ''.join(random.choice(characters) for _ in range(length))
    
    return code

# Example usage:
existing_codes = {'ABC123', 'DEF456', 'GHI789'}
code = generate_code(length=10, exclude_chars='AEIOU', existing_codes=existing_codes)
print("Generated Code:", code)
