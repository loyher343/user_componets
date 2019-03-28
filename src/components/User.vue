<template>
    <div class="component">
        <h1>The User Component</h1>
        <p>I'm an awesome User!</p>
        <button @click="changeName">Chang my name</button>
        <hr>
        <div class="row">
            <div class="col-xs-12 col-sm-6">

                <!-- prop being pass throug -->
                <app-user-detail 
                    :nameProp="name" 
                    @nameWasReset="name = $event"
                    :resetFn="resetName"
                    :userAge='age'></app-user-detail> 

            </div>
            <div class="col-xs-12 col-sm-6">
                <app-user-edit 
                :userAge='editAge'
                @ageWasEdited="$event"></app-user-edit>
            </div>
        </div>
    </div>
</template>

<script>
    import UserDetail from './UserDetail.vue';
    import UserEdit from './UserEdit.vue';

    export default {
        data: function() {
            return {
                name: 'Loy',
                age: 40
            };
        },
        methods: {
            changeName(){
                this.name = 'Marcos';
            },
            resetName(){
                this.name = 'Loys'
            }
        },
        components: {
            appUserDetail: UserDetail,
            appUserEdit: UserEdit
        }
    }
</script>

<style scoped>
    div {
        background-color: lightblue;
    }
</style>
