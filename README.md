# HW-11-Node
Домашняя работа 11


Задание


Готовый API для выполнения домашнего задания:


“import express from 'express';


// Создаем приложение Express

const app = express();


// Используем middleware для обработки JSON в теле запроса

app.use(express.json());


// Простой массив для хранения данных (вместо базы данных)

let products = [

  { id: 1, name: 'Product One', price: 29.99 },

  { id: 2, name: 'Product Two', price: 49.99 },

];


// Маршрут для получения всех продуктов (GET /products)

app.get('/products', (req, res) => {

  res.json(products);

});


// Маршрут для получения конкретного продукта по ID (GET /products/:id)

app.get('/products/:id', (req, res) => {

  const product = products.find(p => p.id === parseInt(req.params.id));

  if (!product) return res.status(404).json({ message: 'Product not found' });

  res.json(product);

});


// Маршрут для создания нового продукта (POST /products)

app.post('/products', (req, res) => {

  const newProduct = {

    id: products.length + 1,

    name: req.body.name,

    price: req.body.price,

  };

  products.push(newProduct);

  res.status(201).json(newProduct);

});


// Запуск сервера на порту 3000

app.listen(3000, () => {

  console.log('Server is running on http://localhost:3000');

});”




Задание: Тестирование API


Запустите API


Скачайте или скопируйте готовый код API и сохраните его в файле, например, `index.js`.

Откройте терминал и перейдите в директорию, где находится этот файл.

Запустите сервер, убедитесь, что сервер запущен и слушает на порту 3000.


Протестируйте маршруты с помощью Postman


Откройте Postman и создайте новый запрос для каждого из маршрутов API:

GET /products: Этот запрос вернет список всех продуктов.

GET /products/:id: Этот запрос вернет конкретный продукт по его ID (например, `/products/1`).

POST /products: Этот запрос добавляет новый продукт. В теле запроса необходимо передать JSON с полями `name` и `price`.


Объедините запросы в коллекцию


Создайте новую коллекцию в Postman:

На панели слева выберите "Collections".

Нажмите на "New Collection" и дайте коллекции название (например, "Products API").

Добавьте все запросы в коллекцию:

Откройте каждый созданный запрос.

Нажмите на значок "Save" и выберите вашу коллекцию для сохранения.


Проверьте коллекцию и убедитесь в корректности работы запросов


Откройте каждый запрос в вашей коллекции и отправьте его.

Убедитесь, что запросы возвращают ожидаемые результаты.

Проверьте правильность получения, создания и отображения данных.

