
# README
# Adrian Cantu Antunez
A01284748
Ingeniero en Tecnologías Computacionales

# Rodrigo Reyes
A01284917
ITC
 
 
| Juan          | Adrian        |
| ------------- | ------------- |
| 10            | 20            |
| 14            | 12            |
 
'''c++

# include <iostream>
# include "Reloj.hpp"

 int n,c;


 int main(int argc, const char * argv[]) {

    Reloj reloj;
    while (n!=7){
      std::cout << "\n¿Que desea hacer? \n1. Definir hora \n2. Definir minutos \n3. Ver la hora \n4. Ver minutos \n5. Muestra \n6. Incrementa minutos \n7. Salir\n";
      std::cin>> n;
      switch (n){
        case 1:
        std::cout << "\n¿Que hora quiere poner?\n";
        std::cin>> c;
        reloj .setHora(c);
        break;
        case 2:
        std::cout << "\n¿Que minutos quiere poner?\n";
        std::cin>> c;
        reloj .setMinutos(c);
        break;
        case 3: 
        std::cout << "\nLa hora es " + std::to_string(reloj .getHora());
        break;
        case 4: 
        std::cout << "\nLos minutos son " + std::to_string(reloj .getMinutos());
        break;
        case 5:
        reloj .Muestra();
        break;
        case 6:
        reloj .IncrementaMinutos();
        reloj .Muestra();
        break;
    }
    }
    return 0;
  }
