const express = require('express');
const app = express();
const port = process.env.PORT || 3000;

app.use(express.json());

app.post('/add', (req, res) => {
    const { num1, num2 } = req.body;
    if (num1 == null || num2 == null) {
        return res.status(400).json({ error: "Please provide num1 and num2" });
    }
    const result = Number(num1) + Number(num2);
    res.json({ result });
});

app.listen(port, () => {
    console.log(Server running on port ${port});
});
