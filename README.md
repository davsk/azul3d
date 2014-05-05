azul3d
======

Package azul3d is a test and demo of azul3d.org and qml.
The graphic primitives, the Azul3d glf/obects, the qmltypes defined in go, and/or the qml files may be used in your program by importing subpackages.

Overview
--------

The following exports are available:
 * mesh
 ** Cube
 ** Cone
 ** Dice
 ** Sphere
 * object
 ** Cube
 ** Cone
 ** Dice
 ** DiceWestern
 ** DiceEastern
 ** Sphere
 ** Earth
 ** Moon
 ** Mars
 * qmltype
 ** GoRect
 ** GoCube
 ** GoDice
 ** GoSolarSystem

 In addition, engine can be used to run qml files bundled with azul3d

Installation
------------

This package uses:
 * azul3d.org graphics package. It has support for linux and windows but with windows you may need to follow the specific installation instructions at [http://azul3d.org](http://azul3d.org).
 * gopkg.in/qml/v0 gui package. It has rather detailed installation instructions at [http://godoc.org/gopkg.in/qml.v0](http://godoc.org/gopkg.in/qml.v0).
 * gopkg.in/cookieo9/resources-go.v2 allows file resources in the package to be accessed by the package. Instructions for embedding zipfiles to create a standalone deployment are at [https://github.com/cookieo9/resources-go/tree/v2](https://github.com/cookieo9/resources-go/tree/v2)

We recommend that you use:

    $ go get gopkg.in/azul3d.v1

Usage Examples
--------------

for OpenGL mesh use:
	
	import "gopkg.in/azul3d.v1/mesh"
	cube := mesh.Cube(1.0)

for Azul3d gfx/object use:
	
	import "gopkg.in/azul3d.v1/object"
	cube := object.Cube(1.0)

for QML file use:
	
	import "gopkg.in/qml.v0"
	import "gopkg.in/azul3d.v1/qmltype"
	qml.RegisterTypes("GoExtensions", 1, 0, []qml.TypeSpec{{
		Init: func(r *qmltype.GoCube, obj qml.Object) { r.SetObject(obj) },
	}})	

for secondary window use:
	
	import "gopkg.in/azul3d.v1/engine"
	engine.Start()
	engine.Run("cube.qml")

for the test demo executable use:
    
    $ go install gopkg.in/azul3d.v1/atestdemo
    $ atestdemo

Documentation
-------------

For detailed API documentation see [http://godoc.org/gopkg.in/azul3d.v1](http://godoc.org/gopkg.in/azul3d.v1)

Inspiration
-----------

The inspiration for this package came from a desire to support and promote the Azul3d.org graphics engine.