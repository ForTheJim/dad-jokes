<template>
<div>
    <h1>About Dad Jokes</h1>
    <p>This is an app that displays terrible, awful Dad Jokes</p>
</div>
</template>

<script>
export default {
    head() {
        return {
            title: 'About The App',
            meta: [
                {
                    hid: 'description',
                    name: 'description',
                    content: 'Best Place for Terrible, Awful Dad Jokes'
                }
            ]
        }
    }
}
</script>