<script setup lang="ts">
import { computed } from "vue";

interface Foo {
  category: 'foo'
}

interface Baz {
  category: 'baz'
}

type unionType = Foo | Baz

//Use Math random so typescript can't infer the type
const foo: unionType = Math.random() > 0.5 ? { category: 'foo' } : { category: 'baz' }

const computedStuff = computed(() => {
  switch (foo.category) {
    case 'foo':
      return 'foo'
    case 'baz':
      return 'baz'
  }
})

</script>

<template>
  {{ computedStuff }}
</template>
