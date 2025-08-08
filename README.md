# longevity_Diet_Shedule_repo

import React from "react"; import { useState } from "react";

const schedule = [ { day: "Monday", fasting: "18:6", supplements: ["Berberine", "Lion's Mane", "Gotu Kola", "Fish Oil"], foods: ["Blueberries", "Tofu", "85% Dark Chocolate"], teas: ["Tulsi Green Tea", "Dragonwell Green Tea"] }, { day: "Tuesday", fasting: "OMAD", supplements: ["Psilocybin Microdose", "Ginkgo Biloba", "Coconut Oil"], foods: ["Beetroot", "Pomegranate", "Greek Yogurt"], teas: ["Bo Li Chun Green Tea", "Rooibos"] }, { day: "Wednesday", fasting: "16:8", supplements: ["Berberine", "Gotu Kola", "Fish Oil"], foods: ["Nuts", "Seeds", "Tofu"], teas: ["Gunpowder Green Tea", "Tulsi"] }, { day: "Thursday", fasting: "18:6", supplements: ["Lion's Mane", "Ginkgo Biloba", "Coconut Oil"], foods: ["Blueberries", "Greek Yogurt"], teas: ["Ceylon Green Tea", "Rooibos"] }, { day: "Friday", fasting: "20:4", supplements: ["Psilocybin Microdose", "Berberine", "Fish Oil"], foods: ["Pomegranate", "85% Dark Chocolate"], teas: ["Tulsi Green Tea", "Bo Li Chun"] }, { day: "Saturday", fasting: "Alternate Day Fast", supplements: ["Gotu Kola", "Lion's Mane", "Ginkgo Biloba"], foods: ["Nuts", "Seeds"], teas: ["Gunpowder Green Tea", "Dragonwell"] }, { day: "Sunday", fasting: "Feast Day", supplements: ["Berberine", "Coconut Oil", "Fish Oil"], foods: ["Greek Yogurt", "Beetroot", "Tofu"], teas: ["Ceylon Green Tea", "Rooibos"] } ];

export default function App() { const [selectedDay, setSelectedDay] = useState(schedule[0]);

return ( <div className="min-h-screen p-6 bg-white text-black"> <h1 className="text-3xl font-bold mb-6">Longevity Planner</h1>

<div className="flex space-x-2 mb-4 overflow-x-auto">
    {schedule.map((day) => (
      <button
        key={day.day}
        onClick={() => setSelectedDay(day)}
        className="px-4 py-2 rounded bg-blue-100 hover:bg-blue-300"
      >
        {day.day}
      </button>
    ))}
  </div>

  <div className="bg-gray-100 p-4 rounded">
    <h2 className="text-xl font-semibold">{selectedDay.day}</h2>
    <p className="mb-2">Fasting Regimen: {selectedDay.fasting}</p>

    <h3 className="font-semibold">Supplements:</h3>
    <ul className="list-disc list-inside mb-2">
      {selectedDay.supplements.map((item, idx) => (
        <li key={idx}>{item}</li>
      ))}
    </ul>

    <h3 className="font-semibold">Foods:</h3>
    <ul className="list-disc list-inside mb-2">
      {selectedDay.foods.map((item, idx) => (
        <li key={idx}>{item}</li>
      ))}
    </ul>

    <h3 className="font-semibold">Teas:</h3>
    <ul className="list-disc list-inside">
      {selectedDay.teas.map((item, idx) => (
        <li key={idx}>{item}</li>
      ))}
    </ul>
  </div>
</div>

); }


