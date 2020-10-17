<template>
  <div class="footer">
    <div class="container">
      <div class="row">
        <div class="col-sm d-flex flex-column">
          <a href="#">Компьютеры</a>
          <a href="#">Комплектующие</a>
          <a href="#">Периферия</a>
          <a href="#">Электроника</a>
          <a href="#">Телефоны</a>
        </div>
        <div class="col-sm d-flex flex-column">
          <a href="#">Реклама на сайте</a>
          <a href="#">Пополнение баланса</a>
          <a href="#">Добавить компанию</a>
        </div>
        <div class="col-sm d-flex flex-column" >
          <a href="#">Написать в редакцию сайта</a>
          <a href="#">Правила размещения</a>
        </div>
      </div>
      <div class="row d-flex justify-content-center">
        <p>© 2000-2020 ТОО «Multimedia Club»</p>
      </div>

    </div>
  </div>
</template>

<script>
export default {
  name: 'VmFooter',
}
</script>

<style lang="scss" scoped>
.footer {
  background: #00202E;
    color: #DDDDDD;

}
a{
    color: #DDDDDD;

  text-decoration: underline;
}
</style>
