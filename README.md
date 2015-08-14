# xcassets enum automatic generator
Automatic generate  enum based on `.xcassets` file

![preview](https://raw.githubusercontent.com/webpatch/xcassets-enum-automatic-generator/master/preview/preview.jpg)

## Enum
The enum file `AssetImages.swift` will look like the following:

```swift
import UIKit
extension UIImage {
	enum Asset : String {
		case Check = "check"
		case List = "list"
		case Back = "back"
		case Backward = "backward"
		case Forward = "forward"
		case Full_Screen = "full_screen"
		case Lock_Screen = "lock_screen"
		case Mini_Screen = "mini_screen"
	}

	convenience init!(asset: Asset) {
		self.init(named: asset.rawValue)
	}
}
```

Once the enum file generated and added to Xcode, you can use it like the following:

```swift
let img1 = UIImage(asset: .Back)
let img2 = UIImage(asset: .Forward)
```

##Usage
###Install (Once for all)
1. Download the [xcassets.py](https://raw.githubusercontent.com/webpatch/xcassets-enum-automatic-generator/master/xcassets.py) and copy it to project's root directory (where the `.xcodeproj` file is located).

2. Excute the script in terminal:

	```shell
	python xcassets.py -i
	```
3. All done!

> <font color="#ff0000">When you change the `.xcassets` file, you need to rebuild the project first, and then it will automatic update the enum file.</font>

###Uninstall
1. Delete the `AssetImages.swift` (choose `Move to Trash`) from Xcode.
2. In project's `Build Phases` settings, delete the entry of `Auto generate xcassets enums`.
3. Delete `xcassets.py`.

##Script argument

|arg|description|
|---|---|
|`-i`|init the script|
|`-u`|update the enum file|
|`-f`|force to update the enum file|
|`-h`|help|
