<template>
    <div class="bg-gray-300 rounded-md p-5">
        <h1 class="text-2xl">What am I up to?</h1>
        <p>Here you can see what my status is on Discord.</p>
        <br />
        <div v-if="lanyard !== null" class="bg-gray-50 opacity-15 p-5 rounded-md flex md:flex-row flex-col">
            <img :src="`https://cdn.discordapp.com/avatars/${ lanyard.discord_user.id }/${ lanyard.discord_user.avatar }`|| `https://cdn.discordapp.com/avatars/728318691716104222/102f9b47cc033813bf0361b87998cae3`" class="rounded-md max-h-23" />
            <div class="flex flex-col my-auto ml-2">
                <div>
                    <p class="text-2xl" v-tippy="{ placement: 'top', arrow: true, followCursor: true, animation: 'fade' }" :content="lanyard.discord_user.id">{{ lanyard.discord_user.username }}<span class="text-gray-700 dark:text-gray-500">#{{ lanyard.discord_user.discriminator }}</span></p>
                </div>
                <div v-if="lanyard.activities.length >= 1">
                    <p class="text-xl text-gray-700 dark:text-gray-500">{{ lanyard.activities[0].name }} <span class="text-black">|</span> <span class="text-black">{{ lanyard.activities[0].details }}</span></p>
                </div>
                <div>
                    <p class="text-md">Currently <span class="text-gray-700 dark:text-gray-500">{{ lanyard.discord_status }}</span></p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  props: {
    lanyard: Array
  }
};
</script>