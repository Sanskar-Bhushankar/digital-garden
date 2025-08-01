---
{"dg-publish":true,"permalink":"/Notes/WEB/React/Project 1- Seat Booking/","created":"2025-02-11T16:26:39.080+05:30"}
---



# seat booking 

``` js
import { useState } from 'react'
import reactLogo from './assets/react.svg'
import viteLogo from '/vite.svg'
import './App.css'

function App() {
  const [seats, setSeats] = useState(Array(20).fill(false));
  const [bookedSeats, setBookedSeats] = useState(0);

  // Handle seat click
  const handleSeatClick = (index) => {
    if (!seats[index]) {
      const updatedSeats = [...seats];
      updatedSeats[index] = true; // Book the seat
      setSeats(updatedSeats);
      setBookedSeats(bookedSeats + 1); // Increment the booked seat count
    }
  };

  // Render the 20 seats in 5 rows
  const renderSeats = () => {
    return seats.map((isBooked, index) => (
      <div
        key={index}
        onClick={() => handleSeatClick(index)}
        style={{
          width: "60px",
          height: "60px",
          margin: "5px",
          display: "inline-block",
          backgroundColor: isBooked ? "red" : "green",
          color: "white",
          textAlign: "center",
          lineHeight: "60px",
          cursor: "pointer",
        }}
      >
        {isBooked ? "Booked" : "Available"}
      </div>
    ));
      }

  return (
    <>
       <div>
      <h2>Seat Booking</h2>
      <div style={{ display: "flex", flexWrap: "wrap", width: "320px" }}>
        {renderSeats()}
      </div>
      <p>Total Seats Booked: {bookedSeats}</p>
    </div>
    </>
  )
}

export default App

```

explanation for some part of code

  `const [seats, setSeats] = useState(Array(20).fill(false));`

- **Line 4**: We initialize a state variable `seats` with an array of 20 elements, all set to `false`. This array will represent the 20 seats, where `false` means the seat is not booked, and `true` means it is booked. `setSeats` is the function that will update this state.


`if (!seats[index]) {`

The condition `if (!seats[index])` works as follows:

1. **`seats[index]`**: The `seats` array holds the booking status for each seat. Each element in the array is either `true` (if the seat is booked) or `false` (if the seat is available).
    
2. **`!seats[index]`**: The `!` (logical NOT) operator inverts the value of `seats[index]`. So:
    
    - If `seats[index]` is `false` (seat is available), `!seats[index]` will be `true`.
    - If `seats[index]` is `true` (seat is already booked), `!seats[index]` will be `false`.
3. **Effect**: The `if (!seats[index])` statement checks if the seat at the given index is **available** (i.e., `seats[index]` is `false`). If it's available, we proceed with booking the seat.


    `const updatedSeats = [...seats];`

- **Line 9**: We create a shallow copy of the `seats` array (using the spread operator `...`). This is necessary because React requires us to treat the state as immutable, meaning we can't directly modify the state. So, we create a new array to modify.

## output
![](/img/user/Notes/WEB/React/attachments/Pasted image 20250105033633.png)


# connecting to sql in backend using mysql2

``` js
import mysql from "mysql2/promise"

const connectdb= async()=>{
    try{
        const connection= await mysql.createConnection({
            host:'localhost',
            user:'root',
            password:'student',
            database:'trial'
        })
        console.log("connection created")
        //await connection.end()

        await connection.execute(`
            create table if not exists classroom(
                id int primary key,
                subject varchar(50) not null,
                passingmarks int not null
            );
        `)
    }catch(err){
            console.log("erro connecting",err.message)
    }

}

connectdb()

```