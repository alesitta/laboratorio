#include <iostream>
#include <stdexcept>

using namespace std;

// Función recursiva para calcular el factorial
int factorial(int n) {
    if (n < 0) {
        throw invalid_argument("Error: Factorial de un numero negativo no esta definido.");
    }
    if (n == 0 || n == 1) {
        return 1;
    }
    return n * factorial(n - 1);
}

// Función recursiva para calcular el n-ésimo número de Fibonacci
int fibonacci(int n) {
    if (n < 0) {
        throw invalid_argument("Error: No existe Fibonacci de un numero negativo.");
    }
    if (n == 0) return 0;
    if (n == 1) return 1;
    return fibonacci(n - 1) + fibonacci(n - 2);
}

int main() {
    try {
        int opcion, numero;
        cout << "Selecciona una opcion:\n1. Calcular Factorial\n2. Calcular Fibonacci\nOpcion: ";
        cin >> opcion;

        cout << "Introduce un numero: ";
        cin >> numero;

        if (opcion == 1) {
            int resultado = factorial(numero);
            cout << "El factorial de " << numero << " es: " << resultado << endl;
        }
        else if (opcion == 2) {
            int resultado = fibonacci(numero);
            cout << "El numero Fibonacci en la posicion " << numero << " es: " << resultado << endl;
        }
        else {
            cout << "Opcion no valida." << endl;
        }
    }
    catch (const exception& e) {
        cerr << "Excepcion capturada: " << e.what() << endl;
    }
    catch (...) {
        cerr << "Se ha producido un error desconocido." << endl;
    }

    return 0;
}
