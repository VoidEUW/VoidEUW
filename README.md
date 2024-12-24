```c
#include <stdio.h>
#include <stdlib.h>

#define DEVELOPER 1
#define NAME "Void"
#define AGE 19
#define COUNTRY "Germany"
#define INSITUTION "Technische Universität Chemnitz"
#define DEGREE "Bachelor of Science"
#define MAJOR "Angewandte Informatik"

#if DEVELOPER

typedef struct Developer {
    char* name;
    int age;
    char* country;
    char* institution;
    char* degree;
    char* major;
    char* programming_languages;
    char* languages;
} Developer;

int main();
void about_me(Developer* developer);
void about_my_profession(Developer* developer);
void about_my_languages(Developer* developer);

int main() {
    Developer* developer = (Developer*) malloc(sizeof(Developer));
    {
        developer->name = NAME;
        developer->age = AGE;
        developer->country = COUNTRY;
        developer->institution = INSITUTION;
        developer->degree = DEGREE;
        developer->major = MAJOR;

        developer->languages = "German, English, French, Chinese";
        developer->programming_languages = "C, C++, Python, Java, JavaScript";
    }

    about_me(developer);
    about_my_profession(developer);
    about_my_languages(developer);

    free(developer);
    return 0;
}

void about_me(Developer* developer) {
    printf("Hey, I'm %s, a %d year old developer from %s.\n", 
        developer->name, 
        developer->age, 
        developer->country
    );
}

void about_my_profession(Developer* developer) {
    printf("I'm currently studying %s at %s.\n", developer->major, developer->institution);
    printf("I'm pursuing a %s degree and I am passionate about software development.\n", developer->degree);
}

void about_my_languages(Developer* developer) {
    printf("I'm fluent in the following languages: %s.\n", developer->languages);
    printf("As for programming languages, I have experience with %s.\n", developer->programming_languages);
}

#endif
```
