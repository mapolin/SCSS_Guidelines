### Nesting rules
  - 
    Do not nest selectors more than 3 levels

    **wrong**
    ```scss
    .level-1 {
        .level-2 {
            .level-3 {
                .level-4 {
                }
            }
        }
    }
    ```
    **correct**
    ```scss
    .level 1 {
        .level-2 {
            .level-3 {
            }
        }
        .level-3 {
            .level-4 {
            }
        }
    }
    ```
