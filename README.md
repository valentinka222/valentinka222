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
