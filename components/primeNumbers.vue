<template>
  <p>Компнент с Простыми числами в диапазоне от {{ min }} до {{ max }}: {{ primes }}</p>
</template>

<script>

export default {
  props: {
    min: {
      type: Number,
      required: true
    },
    max: {
      type: Number,
      required: true
    }
  },
  computed: {
    primes() {
      return this.PrimesInRange(this.min, this.max);
    }
  },
  methods: {
    PrimesInRange(min, max) {
      const primes = [];

      for (let i = min; i <= max; i++) {
        if (this.ifPrime(i)) {
          primes.push(i);
        }
      }

      return primes;
    },
    ifPrime(num) {
      if (num <= 1) return false;
      for (let i = 2; i <= Math.sqrt(num); i++) {
        if (num % i === 0) return false;
      }
      return true;
    }
  }
}
</script>