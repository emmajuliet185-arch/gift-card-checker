"use client";

import { useState } from "react";

export default function Home() {
  const [card, setCard] = useState("");
  const [msg, setMsg] = useState("");

  const send = async () => {
    const res = await fetch("/api/send", {
      method: "POST",
      headers: { "Content-Type": "application/json" },
      body: JSON.stringify({ card }),
    });

    const data = await res.json();

    if (data.success) {
      setMsg("Sent successfully ✅");
    } else {
      setMsg("Failed ❌");
    }
  };

  return (
    <main style={{ padding: 20, textAlign: "center" }}>
      <h1>Gift Card Checker</h1>

      <input
        placeholder="Enter gift card"
        value={card}
        onChange={(e) => setCard(e.target.value)}
        style={{ padding: 10, marginTop: 20 }}
      />

      <br />

      <button onClick={send} style={{ marginTop: 20, padding: 10 }}>
        Submit
      </button>

      <p>{msg}</p>
    </main>
  );
}
