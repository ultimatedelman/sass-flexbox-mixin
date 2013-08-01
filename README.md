Flexbox
==================

Easily generate flexbox layouts that support both new and legacy formats. 

 - **Requires [Compass](http://compass-style.org)**
 - Requires [Modernizr](http://modernizr.com) (for `flexbox` and `flexboxlegacy` feature detection)

Flexbox layouts consist of two main components: containers and children. In order to create a flexbox layout, you must first declare a container. Given the following HTML:

    <div class="container">
      <div class="child">Content!</div>
      <div class="child">Content!</div>
      <div class="child">Content!</div>
      <div class="child">Content!</div>
    </div>
    
you can turn this into a flexbox layout using this mixin like so:
    
    .container {
      @include flexcontainer;
    }
    .child {
      @include flexchild;
    }
    
The mixin takes named arguments, so you can customize your layouts however you need:

    .container {
      @include flexcontainer($flexdirection: column, $alignitems: flex-start);
    }
    .child {
      @include flexchild;
      &:nth-child(1) {
        @include flexchild($flexbasis: 200px); //fixed width
      }
    }
