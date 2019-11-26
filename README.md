# opextract

Python implemtation of Keith Horne's algorithm for optimal extraction of 1-d stellar spectra from 2-d images.

The script is at present not part of a larger package, and has no other files associated with it.  To run it, 
put it in your path somewhere and invoke it.

The script needs astropy.io.fits, numpy, matplotlib (for diagnostic graphics) and scipy, 
as well as standard modules such as argparse.  It works in the astroconda 'iraf27' environment. 

While the script does not call any IRAF tasks, it does assume that a file defining the 
spectrum's 'aperture' -- the part of the image where the spectrum sits -- exists and is
in the format produced by IRAF. Its output is a multispec FITS file in the same form
produced by IRAF's apextract.  At present it basically provides an alternative to apextract,
which has some shortcomings (e.g. cosmic-ray rejection can affects large chunks of the spectrum
at low signal-to-noise).  As such it can be substituted in pipelines that presently use IRAF, but
in the future it could be adapted to a more python-esque environment if needed.
