#  Exercício MongoDB - Loja Virtual

##  Banco de Dados e Coleção

```javascript
use loja_virtual
db.createCollection("produtos")

db.produtos.insertOne({
  nome: "Smartphone Galaxy A15",
  categoria: "Eletronicos",
  preco: 1299.90,
  marca: "Samsung",
  armazenamento: "128GB",
  cor: "Azul",
  estoque: 100
})

db.produtos.insertMany([
  {
    nome: "Notebook Ultra X",
    categoria: "Eletronicos",
    preco: 3899.90,
    marca: "Lenovo",
    memoria_ram: "16GB",
    processador: "Intel i7",
    estoque: 100
  },
  {
    nome: "Camiseta Basica",
    categoria: "Roupas",
    preco: 59.90,
    tamanho: "M",
    cor: "Preta",
    material: "Algodao",
    estoque: 100
  }
])

db.produtos.find()

db.produtos.find({ preco: { $gt: 100 } })

db.produtos.find({ categoria: "Eletronicos" })

db.produtos.find(
  {},
  { nome: 1, preco: 1, _id: 0 }
)

db.produtos.updateOne(
  { nome: "Smartphone Galaxy A15" },
  { $set: { preco: 1199.90 } }
)

db.produtos.updateMany(
  {},
  { $set: { estoque: 50 } }
)

db.produtos.updateMany(
  { categoria: "Roupas" },
  { $set: { promocao: true } }
)

db.produtos.deleteOne({ nome: "Camiseta Basica" })

db.produtos.deleteMany({ categoria: "Livros" })