<template>
  <div class="app">
    <header>
      <h1>Postingan Pengguna</h1>
      <select v-model="selectedUser" @change="fetchPosts">
        <option v-for="user in users" :key="user.id" :value="user.id">{{ user.name }}</option>
      </select>

    </header>
    <main>
      <section v-if="loading" class="loading">Memuat...</section>
      <section v-else class="posts" v-if="posts.length">
        <div v-for="post in posts" :key="post.id">
        <h3>{{ post.title }}</h3>
        <p>{{ post.body }}</p>
      </div>
      </section>
    </main>
  </div>
</template>