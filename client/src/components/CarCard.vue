<template>
  <div>
    <v-card class="mx-auto" max-width="344">
      <v-img height="250" :src="c.image"></v-img>
      <v-card-title>{{ c.title }}</v-card-title>
      <v-card-text>
        Owner: <span class="font-weight-black">{{ c.owner.firstName }} {{ c.owner.lastName }}</span> <br />
        <br />
        Year: <span class="font-weight-black">{{ c.yearOfMake }}</span> <br />
        Miles: <span class="font-weight-black">{{ c.miles }}</span> <br /><br />
        Price: <span class="font-weight-black">{{ c.price }}</span> <br /><br />
        <span>{{ c.description }}</span> <br />
        <br />
        <v-btn color="error" :disabled="c.title.includes('RESERVED')" class="red darken-2" @click="buyCar()">
          BUY CAR
        </v-btn>
      </v-card-text>
    </v-card>
  </div>
</template>

<script>
export default {
  props: {
    c: {
      type: Object,
    },
  },
  methods: {
    buyCar() {
      this.$emit('buyCar', this.c);
    },
  },
};
</script>

<style lang="scss" scoped></style>
