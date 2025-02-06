# review-app

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for web component registration.
```
npm run build
```
Check the review-app.js file was created in the dist directory

### Serves the built files on port 8080 for local access.
```
npm run start
```

### Lints and fixes files
```
npm run lint
```

## How to use web components for other projects

### Before Using Web Components
Backend micro-services, API Gateway, and built review-app files must be running.

### Load built web component files and required libraries
- Add the libraries, Vuetify, VueJs, to the &lt;head&gt; tag.
- Add files of built Web Components within the &lt;body&gt; tag as &lt;script&gt;.
```
-- index.html
<head>
    <!-- Vuetify, VueJs -->
    <link href="https://fonts.googleapis.com/css?family=Roboto:100,300,400,500,700,900" rel="stylesheet">
    <link href="https://cdn.jsdelivr.net/npm/@mdi/font@6.x/css/materialdesignicons.min.css" rel="stylesheet">
    <link href="https://cdn.jsdelivr.net/npm/vuetify@2.x/dist/vuetify.min.css" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/vuetify@2.x/dist/vuetify.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/vue@2.x/dist/vue.min.js"></script>
</head>
<body>
    <!-- built Web Components file -->
    <script src="http://localhost:8080/review-app.js"></script>
</body>
```

### 2. Using Example
Built Web Components can be used as HTML tags.
```
<template>
    <review-app>
        <!-- The JSON Objectt must be converted to a string using JSON.stringify() -->
        <review-review-cards
            :value="JSON.stringify(reviewData)"
            :show-reviews="showReviews" 
            :show-review-input="showReviewInput" 
            :detail-mode="detailMode"
        ></review-review-cards>
    </review-app>
</template>

<script>
export default {
    name: "App",
    data: () => ({
        reviewData: {`
            'rating': 5,
            'content': 'Very Good'
        },
        showReviews: true,
        showReviewInput: true,
        detailMode: true
    })
}
</script>
```
- The component name and props you want to use must be written in a kebab case.
- If the prop type you want to deliver is JSON Object, you must convert it to a string and deliver it.

