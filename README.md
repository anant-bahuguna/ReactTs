# ReactTs
React setup with Typescript


### Changes in the react code

- #### Functional Component -
  - We have to use FC type for functional components
     ```
     import React, { FC } from "react";
          const App: FC = () => {
            return <div>🤟</div>;
          };

     export default App; 
      ```
    
- #### Props in typescript
  - Props are enclosed in `<>`
  - Here the TextField component is getting the prop text of type string
    ```
    import React,{ FC } from 'react'

     const TextField: FC<{ text: string }> = () => {
        return (
            <div>
                <input />
            </div>
         )
     }

    export default TextField
    ```
