# 19 MArch

## Upfront design Process.

1. Recommended initial design
   ![alt text](image.png)

2. Now we should identify all the routes and create a table
   ![alt text](image-1.png)

## Why Path helpers?

1. We are creating path helper functions because sometimes the structure of project become very nasty for example attached image
   ![alt text](image-2.png)

2. To Solve to the above problem we are using the path helper functions.
3. Here is an example of path helpers function
   ![alt text](image-3.png)

## Path helper Implementation

1. Create a path.ts in src
2. This is how we create the path helper function
   ![alt text](image-4.png)

# 20 March

## Creating the routing structure

1. Just create the page.tsx files.
   ![alt text](image-5.png)

## Stubbing out server actions

1. Create three separate files in actions folder
   ![alt text](image-6.png)

2. Just create dummy function and export from actions/index.ts

## Planning Revalidating strategies

1. Add comments to server actions for flushing out cache

## Building the header

1. Create header.tsx in component file
2. Import the header in layout
3. here is the jsx
   ![alt text](image-7.png)

## Displaying the signin and sign out buttons

1. Here is the JSX for this lecture
   ![alt text](image-8.png)

## Enabling Sign out

1. Just wire up the actions with signin/signout buttons
2. Updated JSX
   ![alt text](image-9.png)
