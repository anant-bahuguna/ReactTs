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
    
  - Using Interface for props' types
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
- #### Hooks
  - #### useState
    - Here we haven't given any type so it itself infers the type to be number
      ```
      const [count, setCount] = useState(5);
      ```
    - To give a specific tyape to the state, use <>
      ```
      const [count, setCount] = useState<number>(5);
      ```
    - We can also give different types to be accepted like here `count` accepts any `number` value or `null` value
      ```
      const [count, setCount] = useState<number | null>(5);
      ```
    - State type may be an object
      ```
      const [obj, setObj] = useState<{ text: string }>({text: 'hello'})
      ```
    - We can also have state type in form of an Interface
      ```
      interface textState {
      text: string;
      }

      const [count, setCount] = useState<textState>({text: 'hello'})
      ```
   - #### useRef
     - Unlike the state type in useState hook, ref type is mandatory in useRef
       ```
        const inputRef = useRef<HTMLInputElement>(null);
        const divRef = useRef<HTMLDivElement>(null);
        return (
            <div ref={divRef}>
                <input ref={inputRef} />
            </div>
        );
        ```
    - #### useReducer
     - You need to pass state and action type to reducer
 
- #### Render Props
       
       
    
