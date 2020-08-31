[< Back to index](index.md)

## JHP Audit Plugin
-----
The **JHP Audit** plugin adds 2 new submenu items to the _JHP_ > _Audit_ menu within Archicad.
- **LiveAudit** - Toggles on and off the LiveAudit visual feedback
- **Help** - Opens this document in your web browser

The **LiveAudit** feature is intended to be a suite of visual feedbacks for the user. 

At it's core, this plugin allows us to define a series of "tests" or _audits_ that drawn elements must pass to avoid being highlighted.  
The highlight of these elements **does not print or show up in the final set in any way**. It is not a graphic override.

When the LiveAudit tool is toggled on, it will automatically perform all available audits on all applicable elements, and provide   
highlighted visual feedback for any that fail the audits. As you draw new elements, the same audits will be performed when the element is placed.  
If you select an element and change it, it will also be audited again as soon as you _deselect_ the element.

Currently, the plugin only supports two audits:
- Wall Angle
- Wall Length

---
#### Wall Angle

The Wall Angle audit is performed by checking that the two end points of a wall are even to the nearest half a degree.   
While some projects will require odd angles, the hope is that all walls can be drawn to at least a half a degree and can be assumed that walls   
with angles to greater decimals are not intentional.

Be aware that even though the angle itself may be correct, the angle may introduce a condition where the length will fail, even though the wall is   
drawn correctly. It's possibly to modify the tool to avoid highlighting these cases, but in practice it becomes more effective to be able to easily see  
where the "odd" lengths are and manage them accordingly.

----
#### Wall Length

The Wall Length audit is performed by checking that the overall length of a wall is within a specific tolerance. For now, this tolerance is set to be  
1/4" for wood walls and 1/8" for metal walls. 

This means that if a wall is drawn using the wood composite and its length is 1/8" or beyond (1/16, 1/32, 1/64 etc), the wall will be highlighted.

However, when using a metal composite, the wall is allowed to be to a nearest 1/8" dimension.

Again, this is a means of locating incorrect inputs, or where walls clean up and create odd dimensions that can become visible when dimensioned, as Archicad   
doesn't show us lengths to a smaller fracter than 1/64". 

----

#### Note: 
This tool is designed to aid in the drawing of new walls and ensure that the angle and length are input _as intended_, to **help reduce** the number  
of errors down the line when dimensioned. It will be less effective for projects further along that may already have these errors.   
It is **not** intended as a tool of shame.