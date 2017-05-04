# sizeClassProgrammatically


     override func traitCollectionDidChange(_ previousTraitCollection: UITraitCollection?) {
          super.traitCollectionDidChange(previousTraitCollection)

          if (self.view.traitCollection.horizontalSizeClass == UIUserInterfaceSizeClass.compact) {
              print("horizontal: Compact")
          } else {
              print("Horizontal: Regular")
          }

          if (self.view.traitCollection.verticalSizeClass == UIUserInterfaceSizeClass.compact) {
              print("vertical: Compact ")
          } else {
              print("Vertical: Regular ")
          }
      }
      
Test:      

//iphone 7,6
Portrait:
(height)Vertical: Regular 
(width)horizontal: Compact 


rotate -> Landscape
(height) horizontal: Compact
(width)  vertical: Compact

//iphone 7plus,6plus

(height)Vertical: Regular 
(width)horizontal: Compact 

rotate -> Landscape
(height)vertical: Compact 
(width)Horizontal: Regular


