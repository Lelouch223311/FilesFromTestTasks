<script>
/*! Прошу заметить,я писал максимально быстро на сколько мог,комментарии не оставлял*/

import primeNumbers from '../components/primeNumbers.vue'

export default {
    data() {
        return {
            // min: 11,
            // max: 20
        }
    },
    components: {
        primeNumbers
    },
    methods: {
        getComputerSuffixA(n) {

            let word;
            n = prompt(`Введите число/цифру`, '10')
            if ((n === 1) || (n > 20 && n % 10 === 1)) word = "компьютер";
            else if ((n >= 2 && n <= 4) || (n > 20 && n % 10 >= 2 && n % 10 <= 4)) word = "компьютера";
            else word = "компьютеров";

            return alert(`${n} ${word}`);


        },
        task2(numbers) {
            let NOD = numbers[0];
            for (let i = 1; i < numbers.length; i++) {
                NOD = this.findNOD(NOD, numbers[i]);
            }

            let divisors = [];
            for (let i = 1; i <= NOD; i++) {
                if (NOD % i === 0) {
                    divisors.push(i);
                }
            }

            return divisors;
        },


        findNOD(a, b) {
            while (b !== 0) {
                [a, b] = [b, a % b];
            }
            return a;
        },

        changeNumbers(numbers) {
            // deleted
        },
        checkCodeFirst() {
            alert(
                `
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
`
            )
        },
        consoleTable(n) {
            let nn = prompt(`Введите цифру от 1 до 10`, '6')
            n = nn;
            console.log(`======================\n\ Таблица умножения до ${n}: \n\ ======================`);
            for (let i = 1; i <= n; i++) {
                let tablica = '';
                for (let j = 1; j <= n; j++) {
                    tablica += `${i} × ${j} = ${i * j}\t`;
                }
                console.log(tablica);
                
            }
            alert('Друг,посмотри консоль :)')
        }


    }
}


</script>
<template>
    

    <div>
        <!-- <h2><b>Задачи по Программированию:</b></h2> -->
        <br>
        <div class="first">
            <h3>Задача 1</h3>
            <span> Текст задачи: </span> <b>Разработайте функцию, которая принимает целое число в качестве аргумента и
                возвращает строку, содержащую это число и слово "компьютер" в нужном склонении по падежам в зависимости
                от числа. Например, при вводе числа 25 функция должна возвращать "25 компьютеров", для числа 41-"41
                компьютер", а для числа 1048 - "1048 компьютеров"


            </b>
            <h4>Ответ: <span class="text-red-600"><button @click="getComputerSuffixA">*нажми меня*</button></span></h4>

        </div>
        <br>

        <div class="two">
            <h3>Задача 2</h3>
            <span> Текст задачи: </span> <b>Написать функцию/метод, которая на вход получает массив положительных целых
                чисел произвольной длины. Например [42, 12, 18]. На выходе возвращает массив чисел, которые являются
                общими делителями для всех указанных числе. В примере это будет [2, 3, 6].</b>
            <h4>Ответ: <span class="text-red-600">
                    <p>Массив: [15,3]</p>
                    <p>Что бы сменить цифры,не смог сделать функцию увы. Надо в ручную,путь: ~/pages/programm.vue
                        ctrl+f => two </p>

                    <p>Общие делители: {{ task2([15, 3]) }}</p>
                </span></h4>

        </div>
        <br>
        <div class="three">
            <h3>Задача 3</h3>
            <span> Текст задачи: </span> <b>Написать метод который возвращает массив простых чисел в диапазоне 2 числа -
                максимальный и минимальные заданных чисел. Например вход - от 11 до 20 диапазон считается включая
                граничные значения,навыходе программа должна выдать [11,13,17,19]</b>
            <h4>Ответ: <span class="text-red-600">
                    <!-- <PrimeNumbers :min="10" :max="50" /> -->
                    <PrimeNumbers :min="15" :max="35" />
                </span>
                <button class="p-1 animate-bounce rounded-2xl border-red-600" @click="checkCodeFirst">посмотреть
                    код</button>
            </h4>

        </div>
        <br>
        <div class="four">
            <h3>Задача 4</h3>
            <span> Текст задачи: </span> <b>Написать метод,который в консоль выводит таблицу умножения. На вход метод получает число,до которого выводит таблицу
                умножения. В Консоли должна появиться таблица. Например,если на вход пришло число 5,то получим...</b>
            <h4>Ответ: <span class="text-red-600">
                <button @click="consoleTable(n)">*нажми на меня*</button></span>
            </h4>
            <br>

        </div>
    </div>

</template>


<style scoped>
.first {

    display: flex;
    gap: 5px;
    border: 3px solid lime;
    box-shadow: 1px 1px 19px 15px lime;
    border-radius: 5px;
    animation: borderr infinite linear 1s 2.1s;

}

.two {

    display: flex;
    gap: 5px;
    border: 3px solid green;
    border-radius: 5px;
    box-shadow: 1px 1px 19px 15px black;
}

.three {

    display: flex;
    gap: 5px;
    border: 3px solid lime;
    border-radius: 5px;
    box-shadow: 1px 1px 19px 15px black;
}

.four {

    display: flex;
    gap: 5px;
    border: 3px solid lime;
    border-radius: 5px;
    box-shadow: 1px 1px 19px 15px red;
}


@keyframes borderr {
    0% {
        border: 3px solid blue;
    }

    50% {
        border: 3px solid violet;
    }

    75% {
        border: 3px solid blue;
    }

    100% {
        border: 3px solid blueviolet;
    }
}
</style>