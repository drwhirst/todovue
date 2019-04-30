<template>
    <div class='ui basic content center aligned segment'>
        <button class='ui basic button icon' v-on:click="openForm" v-show="!isCreating">
            <i class='plus icon'></i>
        </button>
        <div class='ui centered card' v-show="isCreating">
            <div class='content'>
                <div class='ui form'>
                    <div class='field'>
                        <label>Title</label>
                        <input v-model="titleText" type='text' ref='title' defaultValue=''>
                    </div>
                    <div class='field'>
                        <label>Project</label>
                        <input v-model=''

