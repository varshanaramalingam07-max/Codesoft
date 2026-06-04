# Simple Movie Recommendation System

movies = {
    "Action": ["Avengers", "Batman", "John Wick"],
    "Comedy": ["Home Alone", "Mr. Bean", "The Mask"],
    "Sci-Fi": ["Interstellar", "Inception", "The Martian"],
    "Horror": ["Conjuring", "Insidious", "Annabelle"]
}

print("=== Movie Recommendation System ===")
print("\nAvailable Categories:")

for category in movies:
    print("-", category)

user_choice = input("\nEnter your favorite category: ")

if user_choice in movies:
    print("\nRecommended Movies:")
    for movie in movies[user_choice]:
        print("-", movie)
else:
    print("\nCategory not found!")
