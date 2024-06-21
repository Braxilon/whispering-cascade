#include <iostream>
#include <string>
#include <thread>
#include <chrono>

// Function to create a whispering-cascade effect
void whisperingCascade(const std::string& text, int baseDelay) {
    for (size_t i = 0; i < text.length(); ++i) {
        std::cout << text[i] << std::flush;
        std::this_thread::sleep_for(std::chrono::milliseconds(baseDelay + i * 50));
    }
    std::cout << std::endl;
}

int main() {
    std::string message;
    int baseDelay;

    // Get user input
    std::cout << "Enter a message to cascade: ";
    std::getline(std::cin, message);
    std::cout << "Enter base delay in milliseconds: ";
    std::cin >> baseDelay;

    // Apply the whispering-cascade effect
    whisperingCascade(message, baseDelay);

    return 0;
}
