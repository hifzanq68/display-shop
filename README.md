# display-shop
import React, { useState } from "react";
import { Input } from "@/components/ui/input";
import { Card, CardContent } from "@/components/ui/card";
import Image from "next/image";

const displayData = [
  {
    brand: "Samsung",
    model: "TFT",
    price: 600,
  },
  {
    brand: "Samsung",
    model: "OLED",
    price: 1600,
  },
  {
    brand: "Samsung",
    model: "A04s",
    price: 850,
  },
  {
    brand: "Samsung",
    model: "M11",
    price: 1150,
  },
  {
    brand: "Vivo",
    model: "Vivo Y16",
    price: 700,
  },
  {
    brand: "Vivo",
    model: "Vivo Y02",
    price: 800,
  },
  {
    brand: "Vivo",
    model: "Vivo V27",
    price: 1400,
  },
  {
    brand: "Vivo",
    model: "Vivo V29",
    price: 1500,
  },
  {
    brand: "Realme",
    model: "Realme C11",
    price: 600,
  },
  {
    brand: "Realme",
    model: "Realme Narzo",
    price: 800,
  },
  {
    brand: "Realme",
    model: "Realme C25",
    price: 1300,
  },
  {
    brand: "Realme",
    model: "Realme C35",
    price: 1500,
  },
  {
    brand: "Redmi",
    model: "Redmi 9A",
    price: 600,
  },
  {
    brand: "Redmi",
    model: "Redmi Note 10",
    price: 1300,
  },
  {
    brand: "Redmi",
    model: "Redmi Note 12",
    price: 1800,
  },
  {
    brand: "Redmi",
    model: "Redmi 13C",
    price: 1500,
  },
  {
    brand: "Oppo",
    model: "Oppo A3s",
    price: 800,
  },
  {
    brand: "Oppo",
    model: "Oppo A57",
    price: 1300,
  },
  {
    brand: "Oppo",
    model: "Oppo A58",
    price: 1600,
  },
  {
    brand: "Oppo",
    model: "Oppo A78",
    price: 1700,
  },
  {
    brand: "Infinix",
    model: "Infinix Smart 7",
    price: 700,
  },
  {
    brand: "Infinix",
    model: "Infinix Hot 20",
    price: 900,
  },
  {
    brand: "Infinix",
    model: "Infinix Zero",
    price: 1200,
  },
  {
    brand: "Infinix",
    model: "Infinix Note 30",
    price: 1600,
  },
];

export default function DisplayList() {
  const [search, setSearch] = useState("");

  const filteredDisplays = displayData.filter(
    (item) =>
      item.brand.toLowerCase().includes(search.toLowerCase()) ||
      item.model.toLowerCase().includes(search.toLowerCase()) ||
      item.price.toString().includes(search)
  );

  return (
    <div className="p-4 max-w-6xl mx-auto">
      <h1 className="text-3xl font-bold mb-4 text-center">Mobile Display List</h1>
      <Input
        type="text"
        placeholder="Search by brand, model, or price"
        className="mb-6"
        value={search}
        onChange={(e) => setSearch(e.target.value)}
      />
      <div className="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4">
        {filteredDisplays.map((item, index) => (
          <Card key={index} className="rounded-2xl shadow-md">
            <Image
              src="/A_digital_graphic_design_displays_smartphone_LCD_s.png"
              alt="Display Image"
              width={300}
              height={200}
              className="rounded-t-2xl"
            />
            <CardContent className="p-4">
              <p className="text-lg font-semibold">{item.brand}</p>
              <p className="text-sm text-gray-500">{item.model}</p>
              <p className="text-base font-medium mt-2">Price: ₹{item.price}</p>
            </CardContent>
          </Card>
        ))}
      </div>
    </div>
  );
}
