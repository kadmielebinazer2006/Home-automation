



# Home-automation-
#include <iostream>
#include <string>
#include <vector>

// Mock classes for hardware components
class LightBulb {
public:
    void turnOn() {
        std::cout << "Light Bulb is ON" << std::endl;
    }

    void turnOff() {
        std::cout << "Light Bulb is OFF" << std::endl;
    }
};

class TemperatureSensor {
public:
    float getTemperature() {
        // Mock temperature reading
        return 22.5; // Example temperature in Celsius
    }
};

// Home Automation System
class HomeAutomation {
private:
    LightBulb lightBulb;
    TemperatureSensor tempSensor;

public:
    void controlLight(const std::string& command) {
        if (command == "on") {
            lightBulb.turnOn();
        } else if (command == "off") {
            lightBulb.turnOff();
        } else {
            std::cout << "Invalid command for light." << std::endl;
        }
    }

    void checkTemperature() {
        float temp = tempSensor.getTemperature();
        std::cout << "Current temperature: " << temp << " °C" << std::endl;
    }
};

int main() {
    HomeAutomation home;

    std::string command;
    std::cout << "Enter command for light (on/off): ";
    std::cin >> command;
    home.controlLight(command);

    std::cout << "Checking temperature..." << std::endl;
    home.checkTemperature();

    return 0;
}
