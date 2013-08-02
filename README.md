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
        @include flexprop(flex-basis, 200px); //helper mixin for single properties
      }
    }

Let this mixin do all the hard work of remembering which IE properties and values translate into which standards-based property and what legacy property maps to which new properties!

A [Mighty Spring](http://www.mightyspring.com) creation.
