<template>
    <div>
      <p>{{ msg }}</p>
    </div>
    <div>
        <div class="container">
            <button type="button" class="btn btn-primary"><p>{{ msg }}</p></button>
        </div>
    </div>
  </template>
  
  <script>

  import axios from 'axios'
  export default {
    name: 'Ping',
    data() {
      return {
        msg: '',
      };
    },
    methods: {
        getMessage() {
            const path = '/ping';
            axios.get(path)
                .then((res) => {
                    this.msg = res.data;
                })
                .catch((error) => {
                    console.error(error);
                });
        },
    },
    created() {
        this.getMessage();
    },
  };
  </script>