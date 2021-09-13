<template>
  <div>
    <v-card
        :loading="loading"
        class="mx-auto my-12"
        max-width="374"
    >
        <template slot="progress">
        <v-progress-linear
            color="deep-purple"
            height="10"
            indeterminate
        ></v-progress-linear>
        </template>

        <v-img
        height="250"
        :src="user.image"
        ></v-img>

        <v-card-title>{{user.name}}</v-card-title>

        <v-card-text>
            <v-row
                align="center"
                class="mx-0"
            >
        
                <div class="grey--text">
                    <v-row align="center" class="mx-0"> 
                        <b>Id:</b> {{user.id}}   <div class="ms-5"><b>Created At:</b> {{user.createdAt}} </div> 
                
                    </v-row>
                </div>
            </v-row>

            <br>
            <div class="my-3 text-subtitle-1">
                <b>Phone:</b> {{user.phone}}
            </div>


            <v-divider class="mx-4"></v-divider>
            <br>

            <div><b>Address:</b> {{user.address}} | <b>Number:</b> {{user.number}} </div>
            <div><b>Zip Code:</b> {{user["zip-code"]}} </div>
            <div><b>Lat:</b> {{user.lat}} | <b>Long:</b> {{user.long}}</div>
        </v-card-text>
    
    </v-card>
  
  </div>
</template>

<script>
    export default {
        props:['user'],
        data: () => ({
        loading: false,
        selection: 1,
        }),

        methods: {
            reserve () {
                this.loading = true

                setTimeout(() => (this.loading = false), 2000)
            },
        },
    }
</script>
