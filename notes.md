## Sass notes

in array we can use lists, its syntax is a little bit different with others.
We define array like below:

```
$breakpoints: (
    small: 499px,
    medium: 899px,
    large: 999px,
    xlarge: 1399px
);
```

In order to use it we call map-get (map.get not sure )

```
@mixin breakpoint($size){ //this is normal mixen with param
    $breakpoint-value: map-get($breakpoints, $size);

    @media screen and (min-width: $breakpoint-value){
        @content;
    }
}
// it means it will when we call this array $breakpoint-value: will be equals
// what $size value equals in list of $breakpoints
@include breakpoint(large){
            width: 185px;
    }
```

In our design we have curved design in background, in order to have that design we can use :after pseudo element like below and set its bg to the photo we need.

```
&:after {
    content: '';//this is mandatory
    position: absolute;
    z-index: 0;
    width: 100%;
    height: 40vw;
    bottom: 0px;
    background-image: url('/images/bg-curvy-mobile.svg');
    background-size: cover;
    background-repeat: no-repeat;
    background-position: bottom center;
  }
```
