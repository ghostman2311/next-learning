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

## More Caching Issues

1. Right now if we try build the app then homepage will be dynamic but we are not using anything there that will make the page dynamic.
2. For best performance, we want to build our pages statically as much as we can.
3. Problem is cookie is changing inside the header when we are checking if user is logged in or not. That is responsible for making the homepage dynamic.

## Static Caching while using auth

1. Every page that is displaying the header will be dynamic.
2. Solution is to make header component as client components.
3. useSession doesn't directly access cookies.
   ![alt text](image-10.png)

4. Add a new case authContent = null because now we are using client component

## Creating topics

1. Create topic create form component.
2. Update the root page.tsx jsx like this
   ![alt text](image-11.png)

## Creating a Popover form

1. Here is the jsx for TopicCreateForm
   ![alt text](image-12.png)

## Receiving Form Data

1. Just add a name field to Input and text area
2. Fetch name and description from formdata

## Adding Form Validation with Zod

1. Install zod library
2. Create createTopicSchema in server action
   ![alt text](image-14.png)
3. Regex shoud be like this
   ![alt text](image-13.png)
4. Schema will have safe parse function which will work like this
   ![alt text](image-15.png)
5. This is how we will validate form data with zod schema safeparse function
   ![alt text](image-16.png)

## Reminder on the UseFormState Hook

1. Whatever we will be returning from our server actions, will be sent to our component
2. Here is how useFormState hook will work
   ![alt text](image-17.png)

## Fixing UserFormState Type Errors

1. Import useFormState in topic create form. Make it as client component.
2. How to fix the error we are getting when we pass action to useFormState hook.
3. What we return from server action must match with what we put as initial state
   ![alt text](image-18.png)

## Here's our form state type

1. Create this type in action
   ![alt text](image-19.png)
2. Update the server action like this
   ![alt text](image-20.png)

## Displaying validation errors

1. Add this prop to Input or TextArea
   ![alt text](image-21.png)

## Handling General Form Errors

1. add new property to the interface i.e '\_form'
   ![alt text](image-22.png)
2. Now we want to display errors if user is not signed and he is creating new topic.
3. Add this check
   ![alt text](image-23.png)
4. Display the form error like this
   ![alt text](image-24.png)
