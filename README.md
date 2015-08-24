## (Forked) RGeo

[![Join the chat at https://gitter.im/oegr/rgeo](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/oegr/rgeo?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

### Disclaimer

Hi,

As the official RGeo repo seems dead, I forked the project in order to help the community 
to continue the work done by previous maintainer.

Everyone is welcome for PRs.
If you want to become a maintainer with me, just ask ;)
I'll need help !

### Statuses

[![Build Status](https://travis-ci.org/oegr/rgeo.svg?branch=master)](https://travis-ci.org/oegr/rgeo)

### Summary

RGeo is a geospatial data library for Ruby.


RGeo is a key component for writing location-aware applications in the Ruby
programming language. At its core is an implementation of the industry
standard OGC Simple Features Specification, which provides data
representations of geometric objects such as points, lines, and polygons,
along with a set of geometric analysis operations. This makes it ideal for
modeling geolocation data. It also supports a suite of optional add-on modules
that provide various geolocation-related services.

Use the core **rgeo** gem to:

*   Represent spatial and geolocation data objects such as points, lines, and
    polygons in your Ruby application.
*   Perform standard spatial analysis operations such as finding
    intersections, creating buffers, and computing lengths and areas.
*   Correctly handle spherical geometry, and compute geographic projections
    for map display and data analysis.
*   Read and write location data in the WKT and WKB representations used by
    spatial databases.


Several optional modules are currently available:

*   Generate and interpret GeoJSON data for communication with common
    location-based web services using the **rgeo-geojson** gem.
*   Read GIS datasets from ESRI shapefiles using the **rgeo-shapefile** gem.
*   Extend ActiveRecord to handle spatial data in MySQL Spatial, SpatiaLite,
    and PostGIS using RGeo's spatial ActiveRecord adapters. These are
    available via the gems:
    *   **activerecord-mysql2spatial-adapter**
    *   **activerecord-spatialite-adapter**
    *   **activerecord-postgis-adapter**

*   and more to come...


Need help? Join the rgeo-users google group at:
http://groups.google.com/group/rgeo-users

### Dependencies

RGeo is known to work with the following Ruby implementations:

*   Ruby 1.8.7 or later. (2.0 or later preferred.)
*   Rubinius 1.1 or later.
*   Partial support for JRuby 1.6.3 or later. The FFI implementation of GEOS
    is available (ffi-geos gem required) but CAPI is not. Proj4 support is
    expected in the future.


Some features also require the following:

*   GEOS 3.2 or later is highly recommended. (3.3.3 or later preferred.) Some
    functions will not be available without it. This C/C++ library may be
    available via your operating system's package manager, or you can download
    it from http://trac.osgeo.org/geos
*   Proj 4.7 or later is also recommended. This library is needed if you want
    to translate coordinates between geographic projections. It also may be
    available via your operating system's package manager, or from
    http://trac.osgeo.org/proj
*   On some platforms, you should install the ffi-geos gem (version 0.0.6 or
    later recommended.) JRuby requires this gem to link properly with Geos,
    and Windows builds probably do as well.


Note: The build system assumes a unix-like environment. Windows builds may be
possible, but not likely "out of the box". I have heard that some Windows
users have had success getting the ffi-geos implementation working, after
suitably installing the Geos library. However, since I'm not a Windows user
myself, I can't provide any direct support for this configuration.

### Installation

Install RGeo as a gem:

    gem install rgeo

Note: By default, the gem installation looks for the GEOS library in the
following locations: `/usr/local`, `/usr/local/geos`, `/opt/local`,
`/opt/geos`, `/opt`, `/usr`, and `/Library/Frameworks/GEOS.framework/unix`. In
other words, MacPorts, Homebrew, the Kyngchaos port, and building from source
to /usr/local are supported out of the box.

If GEOS has been installed in a different location, you must provide its
installation prefix directory using the "--with-geos-dir" option. This option
must be preceded by "`--`" to separate it, as a build switch, from the
switches interpreted by the gem command. For example:

    gem install rgeo -- --with-geos-dir=/path/to/my/geos/installation

Similarly, the gem installation looks for the Proj4 library in the following
locations by default: `/usr/local`, `/usr/local/proj`, `/usr/local/proj4`,
`/opt/local`, `/opt/proj`, `/opt/proj4`, `/opt`, `/usr`, and
`/Library/Frameworks/PROJ.framework/unix`.

If Proj4 is installed in a different location, you must provide its
installation prefix directory using the "--with-proj-dir" option.

### To-do list

The RGeo suite of tools is evolving rapidly. The current to-do list for the
core library includes:

*   Better error handling and reporting.
*   JRuby support for Proj4.
*   GDAL integration including coordinate system interpretation.
*   Ellipsoidal geography implementation, possibly utilizing geographiclib.
*   Windows build support.


Each of the current add-on modules also has its own feature roadmap, and we
are planning on introducing more add-on modules, including:

*   Raster support via GDAL.
*   GeoRSS and KML format support.
*   Custom spatial indexes.
*   Possible additional ActiveRecord adapters (esp. JDBC-based adapters).
*   Integration with third-party APIs.


### Development and support

RDoc Documentation is available at http://rdoc.info/gems/rgeo

Source code is hosted on Github at http://github.com/rgeo/rgeo

Contributions are welcome. Fork the project on Github.

Report bugs on Github issues at http://github.com/rgeo/rgeo/issues

Support available on the rgeo-users google group at
http://groups.google.com/group/rgeo-users

### Acknowledgments

RGeo is written by Daniel Azuma (http://www.daniel-azuma.com).

Development is supported by Pirq (http://www.pirq.com).

Continuous integration service provided by Travis-CI (http://travis-ci.org).

RGeo calls the GEOS library to handle most Cartesian geometric calculations,
and the Proj4 library to handle projections and coordinate transformations.
These libraries are maintained by the Open Source Geospatial Foundation; more
information is available on OSGeo's web site (http://www.osgeo.org).

JRuby support is made possible by the ffi-geos (and upcoming ffi-proj4) gems,
by J Smith (http://github.com/dark-panda).

### License

Copyright 2012 Daniel Azuma

https://github.com/rgeo/rgeo/blob/master/LICENSE.txt
