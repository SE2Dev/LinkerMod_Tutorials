# Hitboxes
In Black Ops, hitboxes work slightly differently from how they worked in previous titles. In previous titles, specifically World at War, you could simply allow converter to automatically generate a hitbox for a given character model (and its gibbed variants) and everything would function exactly as you would expect it to; In Black Ops however, following the same steps will result in an issue where gibbed versions of characters have no head on their hitboxes, meaning it's impossible to headshot a gibbed character. Since most gibbed character variant models have no head present, the automatically generated hitboxes don't have a head - and when you gib the character the standard hitbox is replaced with the hitbox for the gibbed model that is used. Fortunately, this issue isn't incredibly difficult to fix.

## Option 1: Rip the hitbox models
The easiest way to get *correct* hitbox models is to simply rip the hitbox models from the game using [Wraith](http://aviacreations.com/wraith/). To do this, simple enable the exporting of hitbox models through the settings menu (`Settings->Model Settings->Export the model hitbox`). If you want to export directly to XMODEL_EXPORT, make sure that you have "Export .XMODEL_EXPORT" enabled.

![](resources/hitbox_wraith_example.gif "Use the \"hitBoxModel\" field in Asset Manager")

## Option 2: Manually create hitbox models
Alternatively, you could manually create hitbox models for your character (although this isnt really recommended in most cases). The process for this is pretty straightforward: for each variant of a given character model, open the model file in Blender or Maya, attach a head model to the model, and then export the model to a new file (which will be your new hitbox model for that variant)

## Using a hitbox model
To associate a given hitbox model with a normal model, simply navigate to the model you want to add the hitbox to in Asset Manager, and select your hitbox's XMODEL_EXPORT file under the `hitBoxModel` field.


![](resources/hitbox_assetmanager_location.png "Use the \"hitBoxModel\" field in Asset Manager")