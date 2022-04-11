# Cheat Sheet

## Create Project

```bash
yarn create redwood-app ./damlakoksal.com
yarn rw dev
```

## How to Add Packages to Workspace

- They are just an example, do not add them.

```bash
yarn workspace web add marked
yarn workspace api add better-fs
```

## Directory Structure

### API

- `db` folder contains plumbing for the database.
- `dist` folder contains the compiled code for the api side.
- `src` folder contains all of the backend code.

### WEB

- Components, pages and routing found in here.

### SCRIPTS

- Scripts for seeding etc.

## Generating Page

`yarn rw g page home /`

- rw => redwood
- g => generate
- page => generated component type
- home => component/page name
- / => route (you may override route by giving this option)

`yarn redwood g layout blog` to create layout.

```jsx
<Set wrap={BlogLayout}>
    <Route path="/about" page={AboutPage} name="about" />
    <Route path="/" page={HomePage} name="home" />
</Set>
```

- Set is used to wrap the routes with blog layout.

## Getting Dynamic

- Under `api/db/schema.prisma` change the model according to your requirements.
- Afterwards, run `yarn rw prisma migrate dev` to take a snapshot of db.

## Generating Scaffold

- `yarn rw generate scaffold post` will create a page with CRUD operations on plural version of the page which means, posts.

- `posts.sdl.js` generated after this command. It defines fields and types for graphql schema.

## Generating Cell

- `yarn rw g cell Articles` will create a cell with all of the components for these scenarios;
  - Fetching data
  - Loading
  - No data
  - Error
  - Success

⚠️ If you generate cell with plural name, it will query the data as a list. Otherwise, it will query it with id.
