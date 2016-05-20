# Sass-Mixins-Kit

A bunch of useful sass/scss mixins that help you write sass/scss faster.

## Usage

1. Install via NPM:

        npm install sass-mixins-kit --save
    
2. Include Sass-Mixins-Kit in your sass file, remember the path must be relative:

        @import '../node_modules/sass-mixins-kit/sass-mixins-kit';

## Mixins

1. clearfix
    
    A clearfix hack. A way for an element to automatically clear its child elements.
    
    Before using this mixin, I recommend you to try Flexbox Layout or `display: inline` first. They are better solutions.
    
        ul {
            @include clearfix();
            
            li {
                float: left;
            }
        }
    
2. text-ellipsis

    Display an ellipsis('...') at the end of overflowed texts.
    
    Only available in block or inline-block elements.
    A specific width is needed.
    
        span {
            display: block;
            width: 100px;
            @include text-ellipsis();
        }

3. user-select($value: none)

    Add vendor prefixes to `user-select` property.
    
    Most of the time I don't add vendor prefixes in this "sass-mixin" way because [PostCSS](http://postcss.org/) can do it for me.
    But it is weird that PostCSS don't add vendor prefixes to 'user-select' property. So I have to add vendor prefixies myself.

        span {
            @include user-select();
        }
        
    will complie to
    
        span {
            -moz-user-select: none;
            -ms-user-select: none;
            -webkit-user-select: none;
            user-select: none;
        }
        
    This mixin accepts a param and its value (default none) will be applied to the 'user-select' property.

## License

MIT