#include <string>

//Critter.h
class Critter{
    protected:
        std::string name;
    public:

}

int main() {
    Critter c;
    c.greet();

    GlitterCritter gc;
    gc.greet();
// you can cast a subclass as its parent...
Critter third = (Critter)gc;
third.greet();

// you can't go the other way safely..
// GlitterCritter fourth = (GlitterCritter)c;
// fourth.greet()
    return 0;
}

-----
//istream.cpp
//istrea, special functions

#include <iostream>
#include <string>


getline function takes a file 


std::hex turn the number to hex code


std::ios::left means left justify

 
