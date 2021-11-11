<template>
    <div class="blogs row ms-1 mt-2" >
    <div class="col-12"></div>
    <div
      class="
        col-12
        card
        d-flex
        flex-column
        justify-content-center
        align-items-middle
      "
    >
      <div class="p-2 rounded text-center">
        <h2>{{ blog.title }}</h2>
        <h5>{{ blog.creator.name}}</h5>
        <h6>{{blog.body}}</h6>


      </div>
    </div>
    </div>
</template>


<script>
import { computed } from '@vue/reactivity'
import { AppState } from '../AppState'
import { blogsService } from '../services/blogsService'
import { logger } from '../utils/Logger'


export default {
    props: { blog: { type: Object, required: true}},
    setup(props){
        return {
            blogsTitle: computed(()=> `${props.blog.title}`),
            blogsBody: computed(()=> `${props.blog.body}`),
            blogsName: computed(()=> `${props.blog.creator.name}`)
        }
    }}
</script>


<style lang="scss" scoped>

</style>