 ## Layout
 
 ### Autolayout
 
 We prefer to use anchor-based autolayout:
 
 **Preferred:**
 
 ```swift
 let constraint = contentView.leadingAnchor.constraint(equalTo: self.leadingAnchor, constant: 20)
 ```
 
 **Not preferred:**
 
 ```swift
 let constraint = NSLayoutConstraint(item: contentView, attribute: .leading, relatedBy: .equal, toItem: self, attribute: .leading, multiplier: 1, constant: 20)
 ```
 
 and
 
 ```swift
 let constraints = NSLayoutConstraint.constraints(withVisualFormat: "V:|-20-[view(30)]", metrics: nil, views: views)
 ```
 
 ### Autolayout tools
 
 It's not recommended to use any *third-party* autolayout tools. Instead, we have our own helper-extensions for UIView. It's recommended to use them.
 
 **Preferred:**
 
 ```swift
 // Create and activate constraint for width anchor
 view.pinWidth(100)
 
 // Create and activate constraints for edge anchors
 view.fitAnchors(to: superview, insets: UIEdgeInsets(top: 10, left: 10, bottom: 10, right: 0), edges: [.left, .top, .bottom], preferSafeAnchors: true)
 
 // Create and activate constraints for center anchors
 activityIndicator.alignCenters(with: view, offset: CGVector(dx: 5, dy: 7))
 ```
 
 ### Manual Layout
 
 1. Manual layout should be used only where it's necessary
 2. Mixing manual layout and autolayout within one UIView is not recommended

