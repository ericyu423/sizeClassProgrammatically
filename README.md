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



# Rotation only layout change 

           override func traitCollectionDidChange(_ previousTraitCollection: UITraitCollection?) {
                  super.traitCollectionDidChange(previousTraitCollection)



                  if (UIDevice.current.orientation.isPortrait) {
                      view.removeConstraints(view.constraints)
                      view1.removeConstraints(view1.constraints)
                      view2.removeConstraints(view2.constraints)
                      view3.removeConstraints(view3.constraints)
                      view4.removeConstraints(view4.constraints)


                      view1.anchor(top: view.topAnchor, left: view.leftAnchor, bottom: nil, right: view.rightAnchor, paddingTop: 0, paddingLeft: 0, paddingBottom: 00, paddingRight: 0, width: 0, height: view.bounds.height * (2/3))
                      view2.anchor(top: view1.bottomAnchor, left: view.leftAnchor, bottom: nil, right: view.rightAnchor, paddingTop: 0, paddingLeft: 0, paddingBottom: 00, paddingRight: 0, width: 0, height: view.bounds.height * (1/6))
                      view3.anchor(top: view2.bottomAnchor, left: view.leftAnchor, bottom: nil, right: nil, paddingTop: 0, paddingLeft: 0, paddingBottom: 00, paddingRight: 0, width: view.bounds.width * (1/2), height: view.bounds.height * (1/6))
                      view4.anchor(top: view2.bottomAnchor, left: view3.rightAnchor, bottom: nil, right: nil, paddingTop: 0, paddingLeft: 0, paddingBottom: 00, paddingRight: 0, width: view.bounds.width * (1/2), height: view.bounds.height * (1/6))

                      print("\(view.bounds)")
                      print("\(view.frame)")
                  }else{
                      view.removeConstraints(view.constraints)
                      view1.removeConstraints(view1.constraints)
                      view2.removeConstraints(view2.constraints)
                      view3.removeConstraints(view3.constraints)
                      view4.removeConstraints(view4.constraints)

                      view1.anchor(top: view.topAnchor, left: view.leftAnchor, bottom: view.bottomAnchor, right: nil, paddingTop: 0, paddingLeft: 0, paddingBottom: 0, paddingRight: 0, width: view.bounds.width * (1/2), height: 0)
                      view2.anchor(top: view.topAnchor, left: view1.rightAnchor, bottom: nil, right: view.rightAnchor, paddingTop: 0, paddingLeft: 0, paddingBottom: 0, paddingRight: 0, width: view.bounds.width * (1/2), height: view.bounds.height * (1/2))
                      view3.anchor(top: view2.bottomAnchor, left: view1.rightAnchor, bottom: nil, right: nil, paddingTop: 0, paddingLeft: 0, paddingBottom: 0, paddingRight: 0, width: view.bounds.width * (1/4), height: view.bounds.height * (1/2))

                      view4.anchor(top: view2.bottomAnchor, left: view3.rightAnchor, bottom: nil, right: view.rightAnchor, paddingTop: 0, paddingLeft: 0, paddingBottom: 0, paddingRight: 0, width: view.bounds.width * (1/4), height: view.bounds.height * (1/2))
                      // v1v1v2v2
                      // v1v1v3v4
                      print("\(view.bounds)")
                      print("\(view.frame)")

                  }

<p align="center">
  <img src="https://github.com/ericyu423/sizeClassProgrammatically/blob/master/land.png" width="350"/>
  <img src="https://github.com/ericyu423/sizeClassProgrammatically/blob/master/port.png" width="150"/>
</p>

