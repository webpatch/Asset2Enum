# xcassets enum automatic generator
Automatic generate  enum based on `.xcassets` file

## Enum
The enum file `AssetImages.swift` will look something like the following:

```
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

```
let img1 = UIImage(asset: .Back)
let img2 = UIImage(asset: .Forward)
```

##Script usage
1. Copy the script `xcassets.py` to project's root directory (where .xcodeproj file in).

2. Excute the script in terminal:

	```
	python xcassets.py -i
	```
3. All done!


##Script argument

|arg|description|
|---|---|
|`-i`|init the script|
|`-u`|update the enum file|
|`-f`|force to update the enum file|
|`-h`|help|