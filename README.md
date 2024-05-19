# Test-booking-code
1st new code of booking app in golang
<br>
Author: Zeeshali
<br>
package main

import (
	"fmt"
	"strings"
)

func main() {

	var conferancetickets int = 50
	var remainingtickets uint = 50
	Bookings := []string{}

	fmt.Printf("Thankyou for Go confernce we have total %v tickets\n", conferancetickets)
	for {
		var firstname string
		var Lastname string
		var booktickets uint
		var email string
		println("Enter your First Name: ")
		fmt.Scan(&firstname)
		println("Enter your Last Name: ")
		fmt.Scan(&Lastname)
		println("Enter your Tickets: ")
		fmt.Scan(&booktickets)
		println("Enter your Email: ")
		fmt.Scan(&email)

		remainingtickets = remainingtickets - booktickets
		Bookings = append(Bookings, firstname+" "+Lastname, ",")

		// fmt.Printf("The whole slice %v\n", Bookings)
		// fmt.Printf("The first value %v\n", Bookings[0])
		// fmt.Printf("The type of slice %T\n", Bookings)
		// fmt.Printf("The lenth of slice %v\n", len(Bookings))

		fmt.Printf("Thank you %v %v for booking %v tickes. You will receive an confirmation email at %v\n", firstname, Lastname, booktickets, email)
		fmt.Printf("%v tickets are remaining for go confernce\n", remainingtickets)

		Firstnames := []string{}
		for _, boooking := range Bookings {
			var names = strings.Fields(boooking)
			Firstnames = append(Firstnames, names[0])
		}

		fmt.Printf("These are all our bookings: %v\n", Firstnames)

		if remainingtickets == 0 {
			fmt.Printf("confernce is booked out. Come next year.\n")
			break
		}

	}
}
