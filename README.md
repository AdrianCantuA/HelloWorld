
# README
# Adrian Cantu Antunez
A01284748
Ingeniero en Tecnologías Computacionales

# Rodrigo Reyes
A01284917
ITC

//Adrian Cantu Antunez A01284748
#ifndef Fecha_hpp
#define Fecha_hpp

# include <stdio.h>
# include <string>
// Declaración de variables y métodos
class Fecha{
private:
  int dia;
  int mes;

public:
//Metodos constructores
Fecha();
Fecha(int _dia, int _mes);

void setDia(int _dia);
void setMes(int _mes);


int getDia();
int getMes();

std::string str();
};
#endif /*Fecha_hpp*/
