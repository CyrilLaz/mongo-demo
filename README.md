```js
// запрос(ы) для вставки данных минимум о двух книгах в коллекцию books,
const books = [
  {
    title: "1984",
    description:
      "Роман-антиутопия Джорджа Оруэлла о тоталитарном режиме, в котором подавляется индивидуальность, а свободное мышление запрещено.",
    authors: "Джордж Оруэлл",
  },
  {
    title: "О дивный новый мир",
    description:
      "Роман Олдоса Хаксли, действие которого происходит в будущем обществе, где генетическая инженерия и социальное программирование контролируют каждый аспект жизни.",
    authors: "Олдос Хаксли",
  },
];
try {
  db.collection("books").insertMany(books);
} catch (e) {
  console.log(e);
}

// запрос для поиска полей документов коллекции books по полю title,

try {
  const book = db.collection("books").find({ title: "1984" });
} catch (e) {
  console.log(e);
}

// запрос для редактирования полей: description и authors коллекции books по _id записи.

await db.collection("books").updateOne(
  { _id: "66124b2b41d694bb4bdb83b0" },
  {
    $set: {
      description:
        "Depicts a dystopian future where a strict totalitarian government controls every aspect of citizens' lives. The main character, Winston Smith, works at the Ministry of Truth, where he encounters propaganda and manipulation. While trying to resist the system, Winston gets involved in a dangerous rebellion and realizes the importance of truth and freedom.",
      authors: "George Orwell",
    },
  }
);
```
