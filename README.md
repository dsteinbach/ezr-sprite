#ezr-sprite

This compass script will generate sprite css for retina, non-retina and old IE. Whenever an image is added to a subfolder, classnames will automatically be generated and ready to use.

###Instructions

1. Create sub-folders in your image directory called `sprite` and `sprite-2x`.
2. Create identical images for each directory except images in the `sprite-2x` must be exactly twice the size.
3. Setup your scss code as shown in `example.scss`
4. Run `compass watch`


###Options


*folderName* (String) - Which subfolder of `/images/` to look for sprite images.

*spriteClass* (String) - The desired outputted classname for the sprite.

*imageClassPrepend* (String) - What to prepend your sprite image classnames with.

*additionalSizes* (Object) - A sass list (key-value map) of additional sizes you want to generate.

*spacing* (Number) - Padding between images in sprite. Defaults to 0.

###Basic Example

####Images
```
/images/sprite/avatar.png
/images/sprite-2x/avatar.png
```

####Scss
```
@include ezrSprite('sprite', '.ezr-sprite', '.my-app-img-');
```

####Markup
```
<i class="ezr-sprite my-app-img-avatar"></i>
```

###Advanced Example

####Images
```
/images/sprite/avatar.png
/images/sprite-2x/avatar.png
```

####Scss
```
$generate_additional_sizes:     "help-icon" 33,
                                "avatar": 25;

@include ezrSprite('sprite', '.ezr-sprite', '.my-app-img-', $generate_additional_sizes, 5);
```

####Markup
```
<i class="ezr-sprite my-app-img-avatar"></i> Avatar image displayed at original 1x size

<i class="ezr-sprite my-app-img-avatar-25"></i> Avatar image constrained to 25px width.
```
