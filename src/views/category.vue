<template>
  <div>
        <h1>Category</h1>
        <ul>
            <li v-for="category in categories"> {{ category }} </li>
        </ul>
  </div>
</template>

<script>

export default {
    components: {
        asd: () => import('@/views/users')
    },
    data()  {
        return {
              categories: ['animals','birds','trees']
        }
    }  
}
</script>