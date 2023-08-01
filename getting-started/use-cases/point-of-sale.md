# Point Of Sale

The most common approach to working with a POS integration with iVvy is for confirmed bookings to be pulled into the POS system using the [`Get Booking List`](../../venues/getoraddbookingdata/get-booking-list.md) action so that they are visible on the POS on the day of the event.. The getBooking action will include the total amount of the booking, and outstanding amounts for the event. This allows additional flexibility at the POS level to take any remaining balances for the event and pass back the details to the iVvy booking.

Once the event has taken place, \(usually at the time of closing the event\) food and beverage items entered through the POS system will be pushed back into iVvy as “Additional Items” using the [`Add Items To Booking`](../../venues/getoraddbookingdata/add-items-to-booking.md) action. When adding additional items back into iVvy from the POS system, a Cost centre needs to be assigned. To determine a list of cost centres in the iVvy venue account, the [`Get Cost Centre List`](../../account/get-cost-center-list.md) action can be used to access and map the cost centres with the POS system.

Then any payments taken are sent into iVvy using the [`Add Payment to Booking`](../../venues/getoraddbookingdata/add-payment-to-booking.md) action. This action will generate a transaction invoice for the amount of the payment and store the payment information against it. This will reduce the outstanding amount of the iVvy booking, giving the user visibility on total amounts outstanding, if any.

The user will then produce the final invoice in iVvy which will contain the summary of billable items from both systems as they were passed into the booking at the time of closing the event in the POS system. Any remaining amounts \(if applicable\) will be paid against the final invoice.

![](../../.gitbook/assets/pos-system.png)

