#1
#include <iostream>
#include <string>

int main() {
    std::string input;
    std::cout << "Введите строку: ";
    std::getline(std::cin, input);

    int letterCount = 0, digitCount = 0;

    for (char ch : input) {
        if (std::isalpha(ch)) letterCount++;
        else if (std::isdigit(ch)) digitCount++;
    }

    if (letterCount + digitCount == 0) {
        std::cout << "Ошибка: строка должна содержать хотя бы одну букву или цифру." << std::endl;
        return 1; // Завершение с ошибкой
    }

    std::cout << "Исходная строка: " << input << std::endl;
    if (letterCount > digitCount) {
        std::cout << "В строке больше букв, чем цифр." << std::endl;
    } else {
        std::cout << "В строке меньше букв, чем цифр." << std::endl;
    }

    return 0;
}

#2
#include <iostream>
#include <string>
#include <set>

int main() {
    std::string input;
    std::cout << "Введите слово: ";
    std::getline(std::cin, input);

    std::set<char> uniqueLetters;

    for (char ch : input) {
        if (std::isalpha(ch)) uniqueLetters.insert(tolower(ch)); // Приводим к нижнему регистру
    }

    if (uniqueLetters.empty()) {
        std::cout << "Ошибка: слово должно содержать хотя бы одну букву." << std::endl;
        return 1; // Завершение с ошибкой
    }

    std::cout << "Исходная строка: " << input << std::endl;
    std::cout << "Количество различных букв: " << uniqueLetters.size() << std::endl;

    return 0;
}
