### Selectors
- Do not use tag selectors ourside content specific rules

    **wrong**
    ```scss
    p {
        font-weight: bold;
    }
    ```
    **correct**
    ```scss
    // create helper class and apply to <p> tag
    .bold {
        font-weight: bold;
    }
    // or
    .content-item {
        .description {
            p {
                font-weight: bold;
            }
        }
    }
    ```
    
- Do not use ID selectors unless absolutely necessary

    **wrong**
    ```scss
    #content-box {
    }
    ```
    **correct**
    ```scss
    .content-box {
    }
    ```
    
- Do not use combinations of selectors on a single line

    **wrong**
    ```scss
    .content-box.wide-box {
    }
    .button:after {
    }
    ```
    **correct**
    ```scss
    .content-box {
    }
    .wide-box {
    }
    // or
    .content-box {
        &.wide-box {
        }
    }
    .button {
        &:after {
        }
    }
    ```

- If possible, write media queries per general styles

    **wrong**
    ```scss
    .content-box {
        .content-box-header {
        }
    }
    @media (max-width: 640px) {
        .content-box {
            .content-box-header {
            }
        }
    }
    ```
    **correct**
    ```scss
    .content-box {
        .content-box-header {
        }
        
        @media (max-width: 640px) {
            // content-box styles go here
            .content-box-header {
                // content-box-header styles go here
            }
        }
    }
    ```
    
- Use [attribute] selectors for universal javascript related functionalities and styles

    **wrong**
    ```scss
    .modal-box {
        position: absolute;
    }
    ```
    **correct**
    ```scss
    [modal-box] {
        position: absolute;
    }
    ```
