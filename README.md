# FirstProject.py
POUNDS_TO_KILOGRAMS = 0.45
KILOGRAMS_TO_POUNDS = 1 / POUNDS_TO_KILOGRAMS

def main():
    try:
        weight = float(input("Enter your weight: "))
        unit = input("Enter the unit (L)bs or (K)g: ").strip().upper()

        if unit == 'L':
            converted_weight, result_unit = convert_to_kilograms(weight), 'kg'
        elif unit == 'K':
            converted_weight, result_unit = convert_to_pounds(weight), 'lbs'
        else:
            print("Invalid unit. Please enter 'L' for pounds or 'K' for kilograms")
            return

        print(f"Your weight is: {converted_weight} {result_unit}")

    except ValueError:
        print("Invalid input. Please enter a valid weight value.")
    except Exception as e:
        print(f"An error occurred: {e}")

def convert_to_kilograms(pounds):
    return round(pounds * POUNDS_TO_KILOGRAMS, 2)

def convert_to_pounds(kilograms):
    return round(kilograms * KILOGRAMS_TO_POUNDS, 2)

if __name__ == "__main__":
    main()
