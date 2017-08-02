### Extending

- Styles that are meant to be used only when extending, should be created using the `%` selector

    **wrong**
    ```scss
    .list-of-styles-created-for-extends {
        font-weight: normal;
        line-height: 1.3;
        font-size: 1em;
    }
    
    .content-description {
        @extend .list-of-styles-created-for-extends;
    }
    ```
    **correct**
    ```scss
    %list-of-styles-created-for-extends {
        font-weight: normal;
        line-height: 1.3;
        font-size: 1em;
    }
    
    .content-description {
        @extend %list-of-styles-created-for-extends;
    }
    ```
    
- Always try to create subset ot extendable classes | `namespace` declarations
    
    **correct**
    ```scss
    %card {
        padding: 10px;
        border: 1px solid black;
        
        &.blue {
            // optional @extend %card;
            border-color: blue;
        }
        
        &.red {
            // optional @extend %card;
            border-color: red;
        }
    }
    
    .colorful-card {
        // optional @extend %card;
        @extend %card.blue;
    }
    ```
    
