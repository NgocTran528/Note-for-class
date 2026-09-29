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


--Tuesday 
// stringstream demo

#include <iostream>
#include <sstream>
int main() {
    // "adding" string and numeric values doesn't work...
    // string phrace = "I am " + 28 + " years old";
    // std::cout << phrase << std::endl;
    
    std::cout << "I am " << 28 << " years old" << std::endl;
    std::string text;
    int number;

    // a stringstraeam object treats a string like a stream
    std::stringstream ss;
    ss << "I am " << 28 << " years old" << std::endl;
    
    // use the str() method to get the data out of the stream
    std::cout << ss.str();

    // you can get values back!

    ss >> text;
    std::cout << text << std::endl;

    ss>> text;
    std::cout << text << std::endl;

    // you can also insert data into a numeric type if
    // you know it will fit
    ss >> number;
    std::cout << number << std::endl;

    return 0;
} // end main

// fileIO.cpp
#include <fstream>
#include <iostream>
#include <string>

int main(){
    // opening a file for output
    std::ofstream outfile;
    outFile.open("example.dat"); // .dat
    if (outFile.is_open()){
        outFile << "eggs" << std::endl;
        outFile << "milk" << std:endl;
        outFile << "bread" << std::endl;
        outFile.close();
    } else {
        std::cout << "unable to open file" << std::endl;
    } // end if


    // apending to a file
    std::ofstream appFile;
    appFile.open("example.dat", std::ios::app);
    appFile << "chips" << std::endl;
    appFile.close();


    // reading from a file
    std::ifstream inFile;
    inFile.open("example.dat");
    std::string item;
    while (!inFile.eof()){
        std::getline(inFile, item);
        // if (item != ""){
            std::cout << "We need " << item << ", Dude." << std::endl;    
        } // end if
    } // end while
    inFile.close();
    std::cout << std::endl;
    
    
    // using keepGoing loop
    // maybe cleanest way but a bit verbose
    inFile.open("example.dat");
    bool keepGoing = true;
    while (keepGoing){
        getline(inFile, item);
        if (inFile.eof()) {
            keepGoing = false;
        } // end if
    } // end while
    // alternate input
    inFile.open("example.dat");

    // getline returns false at end of file
    // this line both reads in the current line and acts as a condition
    while (getline(inFile, item)) {
        std::cout << "Now we need " << item << std::endl;
    } // end while
    inFile.close();

    return 0;
} // end main
