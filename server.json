const express = require("express");
const http = require("http");
const { Server } = require("socket.io");

const app = express();
const server = http.createServer(app);

const io = new Server(server, {
  cors: { origin: "*" }
});

app.get("/", (req, res) => {
  res.send("WebSocket ativo");
});

io.on("connection", (socket) => {
  socket.on("novo_sinal", (sinal) => {
    io.emit("receber_sinal", sinal);
  });
});

const PORT = process.env.PORT || 3000;
server.listen(PORT, () => {
  console.log("Rodando na porta", PORT);
});
