``` mermaid
classDiagram
direction TB
    class Horse {
	    - int position
	    - int index
	    - int trackLength
	    + Horse() // constructor
	    + init(int index, int trackLength)
	    + advance()
	    + printLane()
	    + isWinner() bool
    }

    class Race {
	    - int NUM_HORSES
	    - int TRACK_LENGTH
	    + horses: Horse[5]
	    + Race() //constructor
	    + start()
    }

    Race --> Horse
```

## Race::Race()()
```
const int TRACK_LENGTH
const int NUM_HORSES

Create an array of horses length NUM_HORSES
Initialize all the horses
for each horse
    initialize that horse with its index and the track length
```

## Race::start()
```
seed the random number generator
bool keepGoing
while keepGoing is true:
    go through each horse
        advance that horse
        print that horse's lane
        if that horse won: 
            set keepGoing to false
```

## Horse::Horse()
```
position = 0
index = 0
trackLength = 15
```
## void Horse::init(int index, int trackLenght)
```
Horse::index = index
Horse::trackLength = trackLength
Horse::position = 0
```

## void Horse::advance()
```
roll a random 0-1 int, put in coin
add coin to position -> position
```

## void Horse::printLane()
```
    for pos = 0 to trackLength:
    if Horse::position == pos:
        print Horse::index
    else:
        print '.'
    print a new line at the end
```

## bool Horse::isWinner()
```
bool winning = false
if position >= trackLength:
    winning = true
    print some sort of message
return winning
```


