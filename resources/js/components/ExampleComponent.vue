<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8">
                <h6>Example Component</h6>
                {{ user }}
                 
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                user: null
            }
        },
        mounted() {
            axios.get('/api/user')
                .then(response => {
                    this.user = response.data
                    console.log(response.data)
                })
                .catch(error => console.log(error.data))
        }
    }
</script>
