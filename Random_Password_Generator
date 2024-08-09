import java.security.SecureRandom;
import java.util.Random;
import java.util.Scanner;

public class PasswordGenerator {

    private static final String LOWERCASE_CHARACTERS = "abcdefghijklmnopqrstuvwxyz";
    private static final String UPPERCASE_CHARACTERS = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
    private static final String NUMBERS = "0123456789";
    private static final String SPECIAL_CHARACTERS = "!@#$%^&*()-_=+[]{}|;:'\",.<>/?";

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter the number of lowercase letters: ");
        int lowercaseCount = scanner.nextInt();

        System.out.print("Enter the number of uppercase letters: ");
        int uppercaseCount = scanner.nextInt();

        System.out.print("Enter the number of numbers: ");
        int numbersCount = scanner.nextInt();

        System.out.print("Enter the number of special characters: ");
        int specialCharactersCount = scanner.nextInt();

        int totalLength = lowercaseCount + uppercaseCount + numbersCount + specialCharactersCount;

        if (totalLength == 0) {
            System.out.println("Password length should be greater than 0.");
        } else {
            String generatedPassword = generateRandomPassword(lowercaseCount, uppercaseCount, numbersCount, specialCharactersCount);
            System.out.println("Generated Password: " + generatedPassword);
        }

        scanner.close();
    }

    public static String generateRandomPassword(int lowercaseCount, int uppercaseCount, int numbersCount, int specialCharactersCount) {
        StringBuilder password = new StringBuilder();
        Random random = new SecureRandom();

        password.append(generateRandomCharacters(LOWERCASE_CHARACTERS, lowercaseCount, random));
        password.append(generateRandomCharacters(UPPERCASE_CHARACTERS, uppercaseCount, random));
        password.append(generateRandomCharacters(NUMBERS, numbersCount, random));
        password.append(generateRandomCharacters(SPECIAL_CHARACTERS, specialCharactersCount, random));

        // Shuffle the characters in the password
        char[] passwordArray = password.toString().toCharArray();
        for (int i = passwordArray.length - 1; i > 0; i--) {
            int index = random.nextInt(i + 1);
            char temp = passwordArray[index];
            passwordArray[index] = passwordArray[i];
            passwordArray[i] = temp;
        }

        return new String(passwordArray);
    }

    private static String generateRandomCharacters(String characters, int count, Random random) {
        StringBuilder result = new StringBuilder();
        for (int i = 0; i < count; i++) {
            int randomIndex = random.nextInt(characters.length());
            char randomChar = characters.charAt(randomIndex);
            result.append(randomChar);
        }
        return result.toString();
    }
}
