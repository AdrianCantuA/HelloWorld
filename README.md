
# README
# Adrian Cantu Antunez
A01284748
Ingeniero en Tecnologías Computacionales

# Rodrigo Reyes
A01284917
ITC

#include "Serie.hpp"
#include <iostream>
//Declaracion de variables
Serie::Serie(){
id = "";
titulo = "";
duracion = 0;
genero = "";
calificacionPromedio = 0;
cantEpisodios = 0;
}
//Se guardan las variables en el objeto
Serie::Serie (std::string _id, std::string _titulo, int _duracion, std::string _genero, double _calificacionPromedio, int _cantEpisodios){
id = _id;
titulo = _titulo;
duracion = _duracion;
genero = _genero;
calificacionPromedio = _calificacionPromedio;
cantEpisodios = _cantEpisodios;
}

//Serie::~Serie() {
 // std::cout << "Se destruyo un objeto Serie\n";
//}
//Metodos set
void Serie::setId(std::string _id){
  id = _id;
}
void Serie::setTitulo (std::string _titulo){
  titulo = _titulo;
}
void Serie::setDuracion(int _duracion){
  duracion = _duracion;
}
void Serie::setGenero (std::string _genero){
  genero = _genero;
}
void Serie::setCalificacion (double _calificacionPromedio){
  calificacionPromedio = _calificacionPromedio;
}
void Serie::setCantidadEpisodios(int _cantEpisodios){
  cantEpisodios = _cantEpisodios;
}
void Serie::setEpisodio(int &_numEpisodio, Episodio _episodio){
if (_numEpisodio>cantEpisodios && _numEpisodio<1){
    _numEpisodio=-1;
}
else {
  episodios[_numEpisodio].setTitulo(_episodio.getTitulo());
  episodios[_numEpisodio].setTemporada(_episodio.getTemporada());
  episodios[_numEpisodio].setCalificacion(_episodio.getCalificacion());
}
}

//Metodos get
std::string Serie::getId(){
  return id;
}
std::string Serie::getTitulo (){
  return titulo;
}
int Serie::getDuracion(){
  return duracion;
}
std::string Serie::getGenero (){
  return genero;
}
double Serie::getCalificacion (){
  return calificacionPromedio;
}
int Serie::getCantidadEpisodios(){
  return cantEpisodios;
}
Episodio Serie::getEpisodio(int &_numEpisodio){
  if (_numEpisodio>cantEpisodios && _numEpisodio<1){
    _numEpisodio=-1;
    return Episodio();
  }
  return episodios[_numEpisodio];
}


//Metodos miscelaneos
void Serie::calcularCalificacionPromedio(){
  double promedio=0;
  if (cantEpisodios==0){
    calificacionPromedio=0;
  }
  else {
    for (int a=0;a<cantEpisodios;a++){
    promedio = promedio + episodios[a].getCalificacion();
    }
  calificacionPromedio = promedio / cantEpisodios;
  }
}
void Serie::addEpisodio(Episodio _episodio){
  if (cantEpisodios<5){
    episodios[cantEpisodios]=_episodio;
    episodios[cantEpisodios].str();
    cantEpisodios=cantEpisodios+1;
    std::cout <<"\n"+_episodio.str();
  }
  else{
    std::cout <<"\nNo se pudo añadir el Episodio:" + _episodio.str();
  }
  }
void Serie::delEpisodio(){
  if (cantEpisodios!=0){
  std::cout <<"\nSe elimino el episodio:" + episodios[cantEpisodios-1].str();
  episodios[cantEpisodios].~Episodio();
  cantEpisodios=cantEpisodios-1;
  }
  else {
    std::cout <<"No hay episodios :/";
  }
}


std::string Serie::str(){
  std::string todo;
  todo= id + ',' + titulo + ',' + std::to_string(duracion) + ',' + genero + ',' +std::to_string(calificacionPromedio) + ',' + std::to_string(cantEpisodios)+ "\n";
  //para imprimir el arreglo de objetos solo tuve que usar un for que llame al metodo str por cada objeto en el arreglo. 
  for (int a=0;a<cantEpisodios;a++){
    todo = todo + "E"+std::to_string(a)+episodios[a].str() + "\n" ;
  }
  return todo;
}
