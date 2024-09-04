# to-dolist
Basit bir vue.js ve bootsrap kullanan To-Do list projesi 
## Projede kullanılan bileşenler
------------
### App.vue: 
Vue.js uygulamanızın ana bileşenidir. Bu bileşen, uygulamanın genel yapısını tanımlar ve diğer alt bileşenleri içerir. Örneğin, To-Do Listesi gibi ana bileşenleri burada birleştirirsiniz. Uygulamanın kök bileşeni olarak, genellikle bir başlık ve ana içerik alanını barındırır.
### TodoList.vue:
uygulamanın ana işlevselliğini yöneten bileşendir. Bu bileşen, yapılacak işlerin (to-do) listesini görüntüler ve kullanıcıların yeni işler eklemesine, mevcut işleri tamamlamasına veya silmesine olanak tanır. Ayrıca, listeyi filtreleyerek sadece tamamlanmış, aktif veya tüm işleri gösterebilir.
### TodoItem.vue:
tek bir to-do öğesini temsil eden bileşendir. Her bir yapılacak iş için bir TodoItem bileşeni oluşturulur. Bu bileşen, bir görevin tamamlanıp tamamlanmadığını kontrol eder ve kullanıcıya işaretleme veya silme gibi eylemler sunar. Ayrıca, görev tamamlandığında üstü çizili olarak gösterir.
## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```
