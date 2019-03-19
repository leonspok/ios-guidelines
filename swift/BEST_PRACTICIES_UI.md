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
 
 It's not recommended to use any *third-party* tools for autolayout. 

