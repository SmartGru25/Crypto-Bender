<template>
<Default>
    <div class="pb-20 text-left">
        <header>
            <div class="flex items-center text-2xl font-bold text-gray-400 md:block dark:text-gray-300">
              <h1 class="inline-block"> Notifications </h1>
          
              <button 
                class="p-2 ml-5 text-sm font-bold bg-white border rounded-md shadow-sm dark:bg-gray-700 dark:border-gray-600 dark:hover:bg-gray-600 dark:hover:text-white hover:shadow-md focus:outline-none"
                @click="$emit('update', false)"
              >
              <i class="fa fa-check"></i>
              Mark all as read
              </button>
            </div>
        </header>

        <div class="mt-5 space-y-2">
            <div v-for="notification in notifications" class="flex justify-between px-5 py-2 bg-white rounded-md shadow-md">
                <div>
                    <h4>
                        <span class="font-bold">Task reminder:</span> {{ notification.message }}
                    </h4>
                    <small></small>
                </div>
                <div>
                    <button @click="markAsRead(notification)" class="px-5 py-1 text-white bg-gray-700 rounded-md hover:bg-opacity-75 focus:outline-none">Mark as read</button>
                </div>
            </div>
        </div>
    </div>
</Default>
</template>

<script setup>
    import Default from "../layouts/default.vue";
    import { inject } from "vue";

    const notifications = inject('notifications', []);
    const markAsRead = (notification) => {
        // set update
    }
</script>