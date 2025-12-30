# churchhouse-portal
Booking &amp; Pre-Order Portal for Church House Banbury...  import { useState } from "react";
import { Card, CardContent } from "@/components/ui/card";
import { Input } from "@/components/ui/input";
import { Textarea } from "@/components/ui/textarea";
import { Button } from "@/components/ui/button";

export default function BookingForm() {
  const [formData, setFormData] = useState({
    name: "",
    email: "",
    phone: "",
    date: "",
    time: "",
    guests: "",
    requests: "",
  });

  const handleChange = (e) => {
    setFormData({ ...formData, [e.target.name]: e.target.value });
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    console.log("Booking submitted:", formData);
    // Replace with email API, database call, or WhatsApp trigger
  };

  return (
    <div className="max-w-xl mx-auto p-4">
      <Card className="shadow-lg rounded-2xl">
        <CardContent className="p-6 space-y-4">
          <h2 className="text-2xl font-semibold text-center">Book a Table</h2>
          <form onSubmit={handleSubmit} className="space-y-4">
            <Input name="name" placeholder="Full Name" onChange={handleChange} required />
            <Input type="email" name="email" placeholder="Email Address" onChange={handleChange} required />
            <Input name="phone" placeholder="Phone Number" onChange={handleChange} required />
            <Input type="date" name="date" onChange={handleChange} required />
            <Input type="time" name="time" onChange={handleChange} required />
            <Input type="number" name="guests" placeholder="Number of Guests" onChange={handleChange} required />
            <Textarea name="requests" placeholder="Special Requests (optional)" onChange={handleChange} />
            <Button type="submit" className="w-full">Submit Booking</Button>
          </form>
        </CardContent>
      </Card>
    </div>
  );
}




