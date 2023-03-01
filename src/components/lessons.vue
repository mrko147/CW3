<template>
     <section>
    <div v-for="lesson in lessons" :key="lesson.id" class="lesson border border-primary rounded">
            <div class="lesson-content">
                <h4>Subject: {{ lessons.subject }}</h4>
                <h4>Loacation: {{ lessons.location }}</h4>
                <h4>Price: <i class="fas fa-pound-sign"></i> {{ lessons.price }}</h4>
                <h4>space: {{ lessons.spaces }}</h4>
                <button v-if="isLessonFull(lesson)" type="button" @click="addLessonToCart(lesson)" disabled>Add to cart</button>
                <button v-else type="button" @click="addLessonToCart(lesson)">Add to cart</button>
            </div>
            <div> 
                <img class="lesson-img" :src="images/lessons.subject" :alt="lessons.subject" >
            </div>
        </div>
        </section>
        
    </template>



<script>

export default {
    props: {
    lessons: {
      type: Array,
      required: true,
    },
  },
}

</script>


