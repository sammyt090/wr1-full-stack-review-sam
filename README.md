## MVP
<ul>
    <li>login functionality</li>
    <li>post posts</li>
    <li>delete/ edit posts</li>
    <li>control the view based on authorization</li>
</ul>

**icebox**
<ul>
<li>delete account</li>
    <li>play music</li>
    <li>customize background</li>
    <li>datamine customers</li>
    <li>Fav Five List</li>
</ul>

### Database
User
```SQL
CREATE TABLE users(
    user_id SERIAL PRIMARY KEY,
    email VARCHAR(100),
    password TEXT
);
```

Post
```SQL
CREATE TABLE posts (
    post_id    SERIAL PRIMARY KEY,
    user_id INT REFERENCES users(user_id),
    content VARCHAR(250),
    created_at DATE
);
```

### Server

**dependencies**:
<ul>
    <li>express</li>
    <li>express-session</li>
    <li>massive</li>
    <li>dotenv</li>
    <li>bcrypt</li>
</ul>

**endpoints**:
auth:
        - app.post('/auth/login')
        - app.post('/auth/register')
        - app.delete('/auth/logout')
        - app.get('/auth/user')

post:
    - app.get('/api/posts')
    - app.post('/api/post')
    - app.put('/api/posts/:post_id')
    - app.delete('/api/posts/:post_id')

### Client

**dependencies**:
<ul>
    <li>axios</li>
    <li>react-router-dom</li>
    <li>redux</li>
    <li>react-redux</li>
    <li>redux-promise-middleware</li>
</ul>

**routes**
- landing (/)
- register (/register)
- dashboard (/dashboard)
- profile (/profile)

**file structure**

- src/
    - App.js
    - App.css
    - index.js
    - reset.css
    - redux/
        - store
        - reducer
    - components/
        - Landing.js /.css
        - Register.js /.css
        - Dashboard.js /.css
        - Profile.js /.css
        - PostContainer.js /.css
        - Post.js /.css
        - Edit.js /.css
        - Header.js /.css
        - AuthHeader.js /.css