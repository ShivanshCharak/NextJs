## React server componenet
- React sevrre component is a new architecture introduced by the react 18
- The architecture intoduces a new wayof creating React componenets, Splitting them into two types
  - Server components
  - Slient components
## React server compponents contd
### Server Components
- In Nextjs all components are serve components by default
- They have the ability to run task like reading files ir fetching data from a database
- However they dont have the abiliyt ti use Hooks or handke user interactions
### Client components

- To create a client componenet, Its necessary to add "use client" at the top of component file
- Clien components cant Perform tasks like reading files, but they have the ability to use hooks and manage interaction


## Routing
- Next.js has a file system based routing mechanism
- URL path that users can access in thr browser are defined by files and folders in you codebase
### Routing conventions
 - All routes must be placed inside the app folder
 - Every file that corresponds to a route must be names page.jsx or page.tsx
 - Every folder corresponds to a path sgement in the browser URL dddd
### File based Rotuing 
The routes is dependednt on the foldername of the cotaining file
for example:- /about route needs a folder structure as src/app/about/page.tsx 
![alt text](image.png)
### Nested routes
![alt text](image-1.png)
![alt text](image-2.png)
## Dynamic routes
![alt text](image-3.png)
![alt text](image-4.png)
## Nested Dynamic routes
![alt text](image-5.png)
## Catch all segements
![alt text](image-6.png)
- Extra [] for handling the docs route without any slug paramss
![alt text](image-7.png)
## Page not found
- The page which we see when we go to any unregitered route we see a 404 page we can customize this page
- We just have to write a `not-found.tsx` file and call it like this
```
import { notFound } from 'next/navigation'
import React from 'react'

function ReviewDetail({
    params
}:{
    params:{
        productId:string,
        reviewId:string,
    }
}) {
    if(parseInt(params.reviewId)>1000){
        notFound()
    }
  return (
    <div>ReviewDetail</div>
  )
}

export default ReviewDetail
```
## File Colocation
- As we know folder name maps to the routes, but routes to work out we need to make sure that every folder has page.tsx
## Private folders
- A Private folder indiatced that it is aprivate implementation detaul and shud not be considered bu the routing system
- The folder and all its subfolders are excluded from routing
- Prefix the folder name with an underscore
![alt text](image-8.png)
The underscore before lib make it unaccessable
### Advantges of using Private folders
- For seperating UI Logic from routing logic
- FOr consistently organizing internal files across a project
- for soritng and grouping file in code editors
- And finally for avoiding potential naming conflicts with future Next.js file conventions
