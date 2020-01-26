<template>
  <section class="contact">
    <h1 class="contact__title">contact</h1>
    <form method="POST" name="contact" class="contact__form" netlify>
      <p class="contact__form__item">
        <label for="name">お名前</label>
        <input type="text" id="name" name="name" />
      </p>
      <p class="contact__form__item">
        <label for="email">Eメール</label>
        <input type="email" id="email" name="email" />
      </p>
      <p class="contact__form__item">
        <label for="content">内容</label>
        <textarea name="content" id="content" cols="30" rows="10"></textarea>
      </p>
      <p class="contact__form__item">
        <button type="submit">送信</button>
      </p>
    </form>
  </section>
</template>

<style lang="scss" scoped>
@import '@/assets/scss/variable.scss';
.contact{
  padding: $header-height $side-space;
  background-color: $main-color;
  height: 100vh;
  color: $light-color;
  &__title {
    text-align: center;
    padding: 0 $side-space;
    @include title;
  }
  &__form {
    width: 100%;
    margin: 0 auto;
    &__item {
      display: flex;
      flex-direction: column;
      margin-bottom: $header-height/2;
    }
    &__item:last-child {
      display: block;
      text-align: center;
    }
  }
}
</style>

