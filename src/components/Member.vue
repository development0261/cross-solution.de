<template>
  <div>
    <q-card class="col-md-12 col-lg-1 col-sm-4 col-xs-11">
      <q-item class="portrait">
        <q-item-section avatar>
          <q-avatar size="10rem">
            <q-img
              :src="image"
              spinner-color="primary"
              spinner-size="82px"
            />
          </q-avatar>
        </q-item-section>
      </q-item>
      <q-item-section>
        <q-item-label>{{ name }}</q-item-label>
        <q-item-label caption>{{ title }}</q-item-label>
      </q-item-section>
      <q-card-section class="slogan">
        {{ slogan }}
      </q-card-section>
      <q-card-actions
        class="slogan"
        align="center"
      >
        <q-btn
          flat
          push
          v-for="button in buttons"
          v-bind:key="button.text"
          v-bind="button.link"
          @click.native="openUrl(button.link)"
        >
          <q-icon :name="button.name" />
        </q-btn>
      </q-card-actions>
    </q-card>

  </div>
</template>

<script>
export default {
  props: {
    name: String,
    title: String,
    image: String,
    slogan: String,
    buttons: Array
  },
  methods: {
    openUrl (url) {
      window.location.href = url
    }
  }
}
</script>

<style lang="sass" scoped>
.btn-icon
  width: 25px

grid-container
  display: grid
  grid-template-columns: repeat(2, 1fr)
  grid-row-gap: 10px
  grid-column-gap: 10px

.q-item .portrait
  box-shadow: 0 0 5px #666
  height: 100%
  padding: 0px
  background-color: $secondary

.q-card
  height: 100%

.q-card .slogan
  background-color: $light-blue-1

.q-card button
  color: $secondary

</style>
