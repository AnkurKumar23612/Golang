# Golang

                                          installattion golang



sudo apt-get update

sudo apt-get -y upgrade

wget https://dl.google.com/go/go1.13.3.linux-amd64.tar.gz

sudo tar -xvf go1.13.3.linux-amd64.tar.gz

sudo mv go /usr/local

export GOROOT=/usr/local/go

export GOPATH=$HOME/Projects/Proj1

export PATH=$GOPATH/bin:$GOROOT/bin:$PATH

go version
						
					installation Visual studio




sudo apt update

sudo apt install software-properties-common apt-transport-https wget

wget -q https://packages.microsoft.com/keys/microsoft.asc -O- | sudo apt-key add -

sudo add-apt-repository "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main

sudo apt update

sudo apt install code

code
				          First step



												
go to 

cd /Documents/Golang/helloworld/

check ls

to run
go run main.go

to build
 go build main.go

to run build file
./main

to format all the code inproject
go fmt

To compile and insatll package
go install  and Go get

to run any test
go test

to remove
rm fileNmae

some of the basi cdata types]
bool,string,int,float64

					  basic code



package main

import "fmt"

func main() {

	card := newCard()

	fmt.Println(card)

}

func newCard() string {

	return "Ankur"
}



					   slice




package main

import "fmt"

func main() {

	cards := []string{"Ankur", newCard()}
	cards = append(cards, "choudhary")

	//fmt.Println(cards)

	for i, card := range cards {
		fmt.Println(i, card)
	}

}

func newCard() string {

	return "Kumar"
}



					
					custome type declaration
1
package main

// Create a new type of 'deck'
// which is a slice of strings
type deck []string

2
package main

import "fmt"

func main() {

	cards := deck{"Ankur", newCard()}
	cards = append(cards, "choudhary")

	//fmt.Println(cards)

	for i, card := range cards {
		fmt.Println(i, card)
	}

}

func newCard() string {

	return "Kumar"
}




				           receiver

1
package main

func main() {

	cards := deck{"Ankur", newCard()}
	cards = append(cards, "choudhary")

	//fmt.Println(cards)

	cards.print()

}

func newCard() string {

	return "Kumar"
}

2
package main

import "fmt"

// Create a new type of 'deck'
// which is a slice of strings
type deck []string

func (d deck) print() {
	for i, card := range d {
		fmt.Println(i, card)
	}
}


						

					Creating a new deck
1
package main

func main() {

	cards := newDeck()

	cards.print()

}

2
package main

import "fmt"

// Create a new type of 'deck'
// which is a slice of strings
type deck []string

func newDeck() deck {
	cards := deck{}

	cardSuits := []string{"Spades", "Diamonds", "Hearts", "Clubs"}
	cardValues := []string{"Ace", "Two", "Three", "Four"}

	for _, suit := range cardSuits {
		for _, value := range cardValues {
			cards = append(cards, value+" of "+suit)
		}
	}

	return cards
}

func (d deck) print() {
	for i, card := range d {
		fmt.Println(i, card)
	}
}



			
					Multiple return values
1
package main

import "fmt"

func main() {

	cards := newDeck()

	//cards.print()
	hand, remainingCards := deal(cards, 5)

	hand.print()
	fmt.Println("Ankur")
	remainingCards.print()

}

2
package main

import "fmt"

// Create a new type of 'deck'
// which is a slice of strings
type deck []string

func newDeck() deck {
	cards := deck{}

	cardSuits := []string{"Spades", "Diamonds", "Hearts", "Clubs"}
	cardValues := []string{"Ace", "Two", "Three", "Four"}

	for _, suit := range cardSuits {
		for _, value := range cardValues {
			cards = append(cards, value+" of "+suit)
		}
	}

	return cards
}

func (d deck) print() {
	for i, card := range d {
		fmt.Println(i, card)
	}
}

func deal(d deck, handSize int) (deck, deck) {
	return d[:handSize], d[handSize:]
}



			converting ,joining and saving to harddrive




