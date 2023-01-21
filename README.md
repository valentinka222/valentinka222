#словари языки
def make_language_list(n):
    pupil_languages = []
    for language in range(n):
        language_name = input()
        pupil_languages.append(language_name)
    return pupil_languages


number_pupils = int(input())
all_languages = []
for pupil in range(number_pupils):
    number_language = int(input())
    pupil_language = make_language_list(number_language)
    all_languages.append(set(pupil_language))
all_know_languages = set.union(*all_languages)
everybody_know_languages = set.intersection(*all_languages)
print(len(everybody_know_languages))
print(*everybody_know_languages, sep='\n')
print(len(all_know_languages))
print(*all_know_languages, sep='\n')





class Book:

    def __init__(self, title, translation, year, writer, country):
        self.title = title
        self.translation = translation
        self.year = year
        self.writer = writer
        self.country = country

    def __repr__(self):
        return self.title + ', ' + self.translation + ', ' + str(self.year) + ', ' + self.writer + ', ' + self.country

    def common_country(self, book):
        if self.country == book.country:
            print("True")
            return True
        else:
            print('False')
            return False

    def previously_written(self, book):
        if self.year > book.year:
            print(self.year)
            return self.year
        else:
            print(book.year)
            return book.year


books = [
    Book("Harry Potter and the sorcerer's stone", 'Гарри Поттер и философский камень', 1997, 'Joanne Rowling', 'England'),
    Book('A walk to remember', 'Спеши любить', 2009, 'Nicholas Sparks', 'USA'),
    Book('The Heart of a dog', 'Собачье сердце', 1925, 'Mikhail Bulgakov', 'Russia'),
    Book('Eugene Onegin', 'Евгений Онегин', 1823, 'Alexander Pushkin', 'Russia')
    ]

books[2].common_country(books[3])
books[0].previously_written(books[2])
print(sorted(books, key=lambda x: x.year))

