
- replace code by regex: eg `background: @color-white` => `.lib-css(background, @color-white)`
(\S*)\: (@\S*);
.lib-css($1, $2);


# Lib

```less
.lib-css(color, @color-white);

.lib-font-size(@value);
.lib-line-height(@heightValue);

.lib-loading-mask() {
    bottom: 0;
    left: 0;
    margin: auto;
    position: fixed;
    right: 0;
    top: 0;
    z-index: 100;
}

.lib-clearfix();//before, after
.lib-clearer();//after

.lib-wrap-words();
.lib-text-overflow();
.lib-text-hide();
.lib-hyphens();

.lib-input-placeholder();



.lib-inline-block-space-container() {
    font-size: 0;
    letter-spacing: -1px;
    line-height: 0;
}

.flex-container {
    .lib-vendor-prefix-display();//@_value: flex
    .lib-vendor-prefix-flex-wrap();//@_value: wrap;
	.lib-vendor-prefix-flex-direction();//@_value: column;
	.lib-vendor-box-align();//stretch
	.ewave-lib-justify-content();//@_value: flex-start;
}
.flex-item {
    .lib-vendor-prefix-flex-grow();//@_value: 0
    .lib-vendor-prefix-flex-shrink();//@_value: 1
    .lib-vendor-prefix-flex-basis();//@_value: auto;
    .lib-vendor-prefix-order();//0
}


.ewave-lib-single-transition();// transition: all .2s;
.ewave-lib-center(); //horizontal & vertical center
.ewave-lib-center(false);	//vertical center


.lib-background-gradient(
    @_background-gradient-color-start,
    @_background-gradient-color-end,
    @_background-gradient-direction,
    @_background-gradient,
    @_background-gradient-color-position: true
)

.lib-visibility-hidden()
.lib-visually-hidden()
.lib-visually-hidden-reset()


// ui
.lib-arrow(
    @_position,
    @_size,
    @_color
);
.lib-pointer(
    @_size: 6px,
    @_background-color: @color-white,
    @_border-color: @color-gray-light3,
    @_position__vertical: top,
    @_position__horizontal: left,
    @_position__vertical__value: -12px,
    @_position__horizontal__value: @indent__s,
    @_z-index: 99
)


.lib-base64(
    @_base64-display: @base64__display,
    @_base64-position: @base64__position,
    @_base64-top: @base64__top,
    @_base64-right: @base64__right,
    @_base64-bottom: @base64__bottom,
    @_base64-left: @base64__left,
    @_base64-width: @base64__width,
    @_base64-height: @base64__height,
    @_base64-margin: @base64__margin,
    @_base64-padding: @base64__padding,
    @_base64-vertical-align: @base64__vertical-align,
    @_base64-background-image: @base64__background-image,
    @_base64-background-position: @base64__background-position,
    @_base64-background-repeat: @base64__background-repeat,
    @_base64-background-size: @base64__background-size,
    @_base64-hover_background-image: @base64__hover__background-image,
    @_base64-active_background-image: @base64__active__background-image,
    @_base64-text-hide: @base64__text-hide,
    @_base64-pseudo-type: @base64__pseudo-type
)
```


# Responsive
```less
//
//  Variables
//  _____________________________________________

//
//  Common
//  _____________________________________________

& when (@media-common = true) {
    //
}

//
//  Mobile
//  ---------------------------------------------

.media-width(@extremum, @break) when (@extremum = 'max') and (@break = @screen__m) {
    //
}

//
//  Tablet
//  _____________________________________________

.media-width(@extremum, @break_left, @break_right) when (@extremum = 'between') and (@break_left = @screen__m) and (@break_right = @screen__l) {
	//
}

//
//  Tablet+
//  _____________________________________________

.media-width(@extremum, @break) when (@extremum = 'min') and (@break = @screen__m) {
    //
}

//
//  Desktop+
//  _____________________________________________

.media-width(@extremum, @break) when (@extremum = 'min') and (@break = @screen__l) {
    //
}

//
//  X-Desktop+
//  _____________________________________________

.media-width(@extremum, @break) when (@extremum = 'min') and (@break = @screen__xl) {
    //
}
```