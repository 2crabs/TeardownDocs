---
title: This will be used as the title-tag of the page head
---

## Teardown API

This is an attempt at documenting the Teardown lua api. 

## UI
```
- UiFont()
- UiSound()
- UiPush()
- UiPop()
- UiWidth()
- UiHeight()
- UiCenter()
- UiMIddle()
- UiColor()
- UIColorFilter()
- UiTranslate()
- UiRotate()
- UiScale()
- UiWindow()
- UiSafeMargins
- UiAlign
- UiModalBegin
- UiModalEnd
- UiEnableInput
- UiDisableInput
- UiGetMousePos
- UiGetMouseWheel
- UiIsMouseInRect()
- UiIsMouseDown()
- UiIsMousePressed()
- UiIsMouseReleased
- UiIsKeyPressed()
- UiWorldToPixel
- UiGetRelativePos
- UiBlur
- UiFont
- UiFontHeight
- UiWordWrap
- UiGetTextSize
- UiText
- UiTextOutline
- UiTextShadow
- UiRect
- UiImage
- UiGetImageSize
- UiImageBox
- UiSound
- UiSoundLoop
- UiMute
- UiButtonIMageBox
- UiButtonHoverColor
- UiButtonPressColor
- UiButtonPressDist
- UiTextButton
- UiImageButton
- UiBlankButton
- UiSlider
```

## Getter
```
- GetInt
- GetFloat
- GetBool
- GetString
- GetTime
- GetTimeStep
- GetIntParam
- GetFloatParam
- GetBoolParam
- GetStringParam
- GetTagValue
- GetLastSound
- GetDescription
- GetInteractShape
- GetInteractBody
- GetFireCount
- GetBodyTransform
- GetBodyMass
- GetBodyShapes
- GetBodyBOunds
- GetShapeLocalTransform
- GetShapeWorldTransform
- GetShapeBody
- GetShapeBounds
- GetShapeCLosestPoint
- GetLocationTransform
- GetJointsConnectecToShape
- GetOtherJoinShape
- GetJointType
- GetJointMovement
- GetJointLimits
- GetLightPos
- GetLightShape
- GetTriggerTransform
- GetPlayerPos
- GetPlayerTransform
- GetPlayerGrabBody
- GetPlayerGrabShape
- GetPlayerVehicle
- GetVehicleBody
- GetBodyVehicle
- GetCameraTransform
```

## Setters
```
- SetInt
- SetFloat
- SetBool
- SetString
- SetValue
- SetTag
- SetCameraTransform
- SetBodyTransform
- SetBodyDynamic
- SetBodyVelocity
- SetShapeLocalTransform
- SetShapeWorldTransform
- SetShaspeEmissiveScale
- SetJointMotor
- SetLightEnabled
- SetLightColor
- SetTriggerTransform
- SetPlayerTransform
```

## Strings
```
- game.tool.gun.damage
- game.tool.shotgun.damage
- game.tool.rocket.damage
- game.input.up, game.input.down, game.input.left, game.input.right
- game.player.health
- game.player.picking
- game.player.grabbing
- game.player.throwing
- game.player.pickvehicle
- game.player.cangrab
- game.player.picktarget
- game.player.canusetool
- game.player.caninteract
- game.player.caninteractvehicle
- game.player.caninteract.x
- game.player.caninteract.y
- game.player.caninteract.z
- game.player.pickdesc
- game.player.idling
- game.player.usevehicle
- game.player.usescreen
- game.paused
- game.vehicle.health
- game.deploy
- game.levelid
- game.levelpath
- game.canquickload
- game.cctv.hits
- game.map.enabled
- game.map.fade
- game.path.recording
- game.path.loaded
- game.path.pos
- game.path.recording
- game.path.loaded
- game.path.length
- game.path.loaded
- game.path.alpha
- game.path.current.x, game.path.current.y, game.path.current.z
- game.pause
- game.unpause
- game.quicksave
- game.quickload
- game.restart
- game.respawn
- game.exitlevel
- game.menu
- game.about
- game.quit
- game.startui
- game.openurl
- game.startlevel
- game.startmission
- game.applygraphics
- game.applydisplay
- game.path.record
- game.path.stop
- game.path.save
- game.path.load
- game.path.has
```
