<template>
    <li :class="['card', [ marked && 'card--marked' ]]">
        <img :src="avatar" :alt="name" class="card__pic">
        <div class="card__info profile">
            <h3 class="profile__name">{{ name }}</h3>
            <p class="profile__about">{{ title }}</p>
            <p class="profile__address">{{ address }}, {{ city }}</p>
            <p class="profile__email">{{ email }}</p>
            <button class="profile__btn" @click="markCard">{{ text }}</button>
        </div>
    </li>
</template>

<script>
export default {
    props: {
        address: {
            type: String,
            default: ''
        },
        avatar: {
            type: String,
            default: ''
        },
        city: {
            type: String,
            default: ''
        },
        email: {
            type: String,
            default: ''
        },
        name: {
            type: String,
            default: ''
        },
        title: {
            type: String,
            default: ''
        }
    },
    data() {
        return {
            text: 'Mark as suitable',
            marked: false
        }
    },
    methods: {
        markCard: function () {
            if (!this.marked) {
                this.text = 'Mark as suitable'
            } else {
                this.text = 'Skip selection'
            }
            this.marked = !this.marked;
        }
    }
}
</script>

<style scoped>
.card {
    background: #FAFAFA;
    box-shadow: 0px 0px 2px rgba(0, 0, 0, 0.12), 0px 2px 2px rgba(0, 0, 0, 0.24);
    border-radius: 3px;
    margin-bottom: 20px;
    display: flex;
    align-items: stretch;
}

.card__marked {
    border: 1px solid #4765FF;
}

.card__pic {
    background-color: #777;
    width: 136px;
    object-fit: cover;
}
</style>