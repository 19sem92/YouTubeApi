<template>
    <div>
        Hi there!
        <SearchBar @termChange="onTermChange"/>
        <VideoList/>
    </div>
</template>

<script>
    import axios from 'axios';
    import SearchBar from './components/SearchBar';
    import VideoList from './components/VideoList';
    const API_KEY = 'AIzaSyBdsUPqT6cwQ-E2h7lWtPDy-m8vmjdHMTU';

    export default {
        name: 'App',
        components: {
            SearchBar,
            VideoList
        },
        methods: {
            onTermChange(searchWord){

                axios.get('https://www.googleapis.com/youtube/v3/search', {
                    params:{
                        key: API_KEY,
                        type: 'video',
                        part: 'snippet',
                        q: searchWord
                    }

                })
                    .then(res => console.log(res))
            }
        }

    }

</script>

<style></style>
