#include <iostream>

// Función para calcular la potencia
int calcularPotencia(int base, int exponente) {
    if (exponente == 0) {
        return 1;
    }
    else if (exponente < 0) {
        return 0; // Manejar casos donde el exponente sea cero o negativo
    }
    else {
        return base * calcularPotencia(base, exponente - 1);
    }
}

// Función para determinar si un número es primo
bool esPrimo(int numero) {
    if (numero <= 1) {
        return false;
    }
    for (int i = 2; i * i <= numero; i++) {
        if (numero % i == 0) {
            return false;
        }
    }
    return true;
}

// Función para determinar si un año es bisiesto
bool esBisiesto(int anio) {
    if (anio % 4 == 0) {
        if (anio % 100 == 0) {
            if (anio % 400 == 0) {
                return true;
            }
            else {
                return false;
            }
        }
        else {
            return true;
        }
    }
    else {
        return false;
    }
}

int main() {
    int opcion;
    int numero1, numero2;
    int base, exponente;
    int anio;

    do {
        std::cout << "Seleccione una opción:\n";
        std::cout << "1. Realizar operaciones aritméticas básicas\n";
        std::cout << "2. Comparar dos números\n";
        std::cout << "3. Calcular la potencia de un número\n";
        std::cout << "4. Determinar si un número es primo\n";
        std::cout << "5. Determinar si un año es bisiesto\n";
        std::cout << "6. Salir\n";
        std::cin >> opcion;

        switch (opcion) {
        case 1:
            std::cout << "Ingrese dos números enteros: ";
            std::cin >> numero1 >> numero2;
            std::cout << "Suma: " << numero1 + numero2 << "\n";
            std::cout << "Resta: " << numero1 - numero2 << "\n";
            std::cout << "Multiplicación: " << numero1 * numero2 << "\n";
            std::cout << "División: " << static_cast<double>(numero1) / numero2 << "\n";
            std::cout << "Comparación:\n";
            std::cout << "Iguales: " << (numero1 == numero2) << "\n";
            std::cout << "Mayor: " << (numero1 > numero2) << "\n";
            std::cout << "Menor: " << (numero1 < numero2) << "\n";
            break;
        case 2:
            std::cout << "Ingrese dos números enteros: ";
            std::cin >> numero1 >> numero2;
            std::cout << "Comparación:\n";
            std::cout << "Iguales: " << (numero1 == numero2) << "\n";
            std::cout << "Mayor: " << (numero1 > numero2) << "\n";
            std::cout << "Menor: " << (numero1 < numero2) << "\n";
            break;
        case 3:
            std::cout << "Ingrese la base y el exponente: ";
            std::cin >> base >> exponente;
            std::cout << "Resultado: " << calcularPotencia(base, exponente) << "\n";
            break;
        case 4:
            std::cout << "Ingrese un número: ";
            std::cin >> numero1;
            if (esPrimo(numero1)) {
                std::cout << "El número es primo\n";
            }
            else {
                // End of the main function
