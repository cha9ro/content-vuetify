<template>
    <main>
        <h1>Blog</h1>
        <ContentList path="/blog" v-slot="{ list }">
            <div v-for="article in list" :key="article._path">
                <v-card class="ma-4 pa-3" :to="article._path">
                    <v-card-title>{{ article.title }}</v-card-title>
                    <v-card-subtitle>{{ article.description }}</v-card-subtitle>
                    <v-card-actions>
                        <v-btn v-for="tag in article.tags" :key="tag" to="/">{{ tag }}</v-btn>
                    </v-card-actions>
                </v-card>
            </div>
        </ContentList>
        <v-btn class="ma-4 pa-3" to="/">Home</v-btn>
    </main>
</template>