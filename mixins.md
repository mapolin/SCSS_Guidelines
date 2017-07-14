### Mixins and extending

- Avoid using mixins for applying styles as much as possible

    **wrong**
    ```scss
    @mixin card() {
        padding: 10px;
        border: 1px solid #cecece;
    }
    
    .user-box {
        @include card();
        border: 2px solid #000;
    }
    ```
    **correct**
    ```scss
    %card {
        padding: 10px;
        border: 1px solid #cecece;
    }
    
    .user-box {
        @extend .card;
        border: 2px solid #000;
    }
    ```
    **best**
    `<div class="card user-box"></div>>`
    ```scss
    .card {
        padding: 10px;
        border: 1px solid #cecece;
    }
    
    .user-box {
        border: 2px solid #000;
    }
    ```
    
- Always add default values to mixin arguments
    **wrong**
    ```scss
    @mixin card($padding) {
        padding: $padding;
        border: 1px solid #cecece;
    }
    ```
    **correct**
    ```scss
    @mixin card($padding: 10px) {
        padding: $padding;
        border: 1px solid #cecece;
    }
    ```
    
- Write mixin names using dash notation
    **wrong**
    ```scss
    @mixin cardGenerator($padding) {
        padding: $padding;
        border: 1px solid #cecece;
    }
    ```
    **correct**
    ```scss
    @mixin card-generator($padding: 10px) {
        padding: $padding;
        border: 1px solid #cecece;
    }
    ```
    
- Always think about using a `pure function mixin` instead of a traditional one
    **wrong**
    ```scss
    @mixin padding-generator($columns, $gutter) {
        padding: $columns * $gutter;
    }
    
    .padded-item {
        @include padding-generator(4, 10px);
    }
    ```
    **correct**
    ```scss
    @mixin padding-generator($columns, $gutter) {
        return $columns * $gutter;
    }
    
    .padded-item {
        padding: padding-generator(4, 10px);
    }
    ```
