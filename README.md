PROJECT : BUS TICKET RESERVATION SYSTEM
TITLE : GoBus
TARGET AUDIENCE : Travel Agencies
TYPE : B2B
TIMELINE : 2 weeks
BUDGET : 0
TOTAL MEMBERS : 1
FEATURES :
	Registration
	Admin Login
	Adding and Updating Bus details
	View Bus availability
	Remove outdated Bus
	Selecting a bus based on route and schedule
	Choose available seats
	Generate booking confirmation
	Payment options
	Bill generation
	Viewing past bookings
	Canceling a reservation
	Refund processing
	View overall booking statistics
DATA MODEL:
	Registration-Class
		userId String
		name String
		emailid String
		phoneno String/long
		DOB String
		password String
		confirmPassword String
	Admin-Class
		adminId String
		userName String
		password String
	Bus-Class
		busId String
		busNumber String
		operatorName String
		route String
		departureTime Date/Time
		arrivalTime Date/Time
		totalSeats int
		availableSeats int
		status String("Active"/"Cancvelled"/"Expired")
	Seat-Class
		seatId String
		seatNumber String
		isBooked Boolean
		busId String
	Booking-Class
		bookingId String
		userId String
		busId String
		selectedSeats List<Seat>
		bookingDate Date
		totalAmount Double
		bookingStatus String("Confirmed"/"Cancelled"/"Refunded")
	Payment-Class
		paymentId String
		bookingId String
		paymentMethod String("Card"/"UPI"/"NetBanking")
		paymentDate Date
		paymentStatus String("Success"/"Failed")
	Bill-Class
		billId String
		bookingId String
		userId String
		amount Double
		dateGenerated Date
	BookingHistory-Class
		userId String
		bookings List<Booking>
	Cancellation-Class
		cancellationId String
		bookingId String
		cancelDate Date
		refundAmount Double
	Statistics-Class
		totalBookings int
		totalRevenue Double
		mostBookedRoute String
		cancelledBookings int
		occupancyRate Double
	SearchFilter-Class
		filterByRoute String
		filterByDate Date
		filterByBusNumber String
