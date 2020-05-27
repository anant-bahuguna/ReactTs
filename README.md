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
    
  - Using Interface for props
    ```
    interface Props {
        name: string;
        isSingle: boolean;
        age: number;
        fn: (name: string) => void;
        obj: {
            x2: number;
        };
    }

    const TextField: FC<Props> = () => {
        return (
            <div>
                <input />
            </div>
        );
    };
    ```
   - Optional Props can be used using `?:`
      Here isSingle, fn and obj are optional
      ```
      interface Props {
          name: string;
          isSingle?: boolean; //Optional
          age: number;
          fn?: (name: string) => void; //optional
          obj?: {            
              x2: number;
          };    //optional
      }
       ```
