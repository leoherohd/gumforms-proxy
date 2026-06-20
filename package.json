const express = require("express");

const app = express();

app.use(express.json());

app.all("*", (req, res) => {
  res.json({
    service: "gumforms-proxy-v1",
    method: req.method,
    host: req.hostname,
    path: req.path,
    query: req.query,
    headers: req.headers,
  });
});

app.get("/health", (req, res) => {
  res.json({ status: "ok" });
});

const port = process.env.PORT || 3000;
app.listen(port, () => {
  console.log(`Server running on port ${port}`);
});
