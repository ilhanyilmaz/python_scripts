# Shrinks images in the folder provided by scaleDownFactor (default=3) and saves them in another folder
# Usage : python smaller_copies.py FOLDERNAME

import os, sys
from PIL import Image

folderSuffix = "_small"
scaleDownFactor = 3

for folderName in sys.argv[1:]:
	fileList = os.listdir(folderName)
	os.mkdir(folderName+folderSuffix)

	for infile in fileList:
		outfile = os.path.splitext(infile)[0] + "_"

		if infile != outfile:
			try:
				im = Image.open(folderName + "/" + infile)
				size = [im.size[0]/scaleDownFactor, im.size[1]/scaleDownFactor]
				im = im.resize(size)
				im.save(folderName + folderSuffix + "/" + outfile + ".jpg", "JPEG")

			except IOError:
				print "cannot create thumbnail for '%s'" % infile
