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

## Handling Database errors in forms

1. Import these statements
   ![alt text](image-25.png)
2. Update the function like this
   ![alt text](image-26.png)

3. After that revalidate and redirect the user
   ![alt text](image-27.png)

---

# 25 March

## Showing Loading Spinners with UseFormStatus

1. Just add small delay
   ![alt text](image-28.png)

2. We can not use useFormStatus hook directly on parent component.
   ![alt text](image-29.png)

3. Create common inside the component and create form-button in it.
4. Here's the tsx for our new component
   ![alt text](image-30.png)

# 28 March

## Fetching and listing content from prisma

1. Create topic-list.tsx in components/topics directory
2. Here are the tsx for this components
   ![alt text](image-31.png)
   ![alt text](image-32.png)

## Scaffolding the topic show page

1. Add this interface in topic show page
   ![alt text](image-33.png)

2. Here is the tsx for this lecture
   ![alt text](image-34.png)

## Displaying a creation form

1. Create new directory inside the components called posts and create post-create-form.tsx file.
2. Import post create form inside the topic show page
3. Here is the tsx for this lecture
   ![alt text](image-35.png)

## Applying validation to post creation

1. This is how our createPost action looks
   ![alt text](image-36.png)

2. Wire up useFormState in PostCreate Form

## Checking authentication status

1. Just add this piece of code in create post server actions
   ![alt text](image-37.png)

2. Add this jsx above the form button in create-post form
   ![alt text](image-38.png)

## Passing additional args to a server action

1. Here is the visual representation of our table
   ![alt text](image-39.png)
2. Currently we don't have access to the topic id in create post server actions
3. This is our current component diagram
   ![alt text](image-40.png)

4. Pass slug from topic show page to postcreate form
5. This is how we pass extra args using useFormState to server actions
   ![alt text](image-41.png)

6. This is how we will find the topic inside the server actions because we need topic id.
   ![alt text](image-42.png)

## Creating the record

1. Here is code the create new post
   ![alt text](image-43.png)

2. After you have created the post now, revalidate and redirect
   ![alt text](image-44.png)

## Merging few files

1. Merge the downloaded files
