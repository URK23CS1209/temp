
def celsius_to_fahrenheit(celsius):
    return (celsius * 9/5) + 32

def celsius_to_kelvin(celsius):
    return celsius + 273.15

def fahrenheit_to_celsius(fahrenheit):
    return (fahrenheit - 32) * 5/9

def fahrenheit_to_kelvin(fahrenheit):
    return (fahrenheit - 32) * 5/9 + 273.15

def kelvin_to_celsius(kelvin):
    return kelvin - 273.15

def kelvin_to_fahrenheit(kelvin):
    return (kelvin - 273.15) * 9/5 + 32

def convert_temperature(value, unit):
    if unit.lower() in ['celsius', 'c']:
        celsius = value
        fahrenheit = celsius_to_fahrenheit(celsius)
        kelvin = celsius_to_kelvin(celsius)
    elif unit.lower() in ['fahrenheit', 'f']:
        fahrenheit = value
        celsius = fahrenheit_to_celsius(fahrenheit)
        kelvin = fahrenheit_to_kelvin(fahrenheit)
    elif unit.lower() in ['kelvin', 'k']:
        kelvin = value
        celsius = kelvin_to_celsius(kelvin)
        fahrenheit = kelvin_to_fahrenheit(kelvin)
    else:
        raise ValueError("Unknown temperature unit. Please use 'Celsius', 'Fahrenheit', or 'Kelvin'.")
    
    return celsius, fahrenheit, kelvin

def main():
    try:
        value = float(input("Enter the temperature value: "))
        unit = input("Enter the unit of measurement (Celsius, Fahrenheit, Kelvin): ").strip()
        
        celsius, fahrenheit, kelvin = convert_temperature(value, unit)
        
        print(f"\nTemperature Conversions for {value} {unit.capitalize()}:")
        print(f"Celsius: {celsius:.2f} °C")
        print(f"Fahrenheit: {fahrenheit:.2f} °F")
        print(f"Kelvin: {kelvin:.2f} K")
    except ValueError as e:
        print(f"Error: {e}")

if __name__ == "__main__":
    main()
