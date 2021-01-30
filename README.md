# font_dataset

This repository contains the fonts dataset. Each dataset is comprised of 62 images of letters and digits representing one of 62 classes (26 upper-case letters, 26 lower-case letters, 10 digits). Each letter was typed in Word using the "Calibri", "Times New Roman" and "Bell MT" fonts (one font per dataset), print-screened, copied to a bit-map file, cropped, and shrunk so that its larger dimension (either horizontal or vertical) will be comprised of 20 pixels (the smaller dimension's size was derived to keep the proportions of the image). The shrinking was done using Windows' painter tool.

Some lower-case letters are smaller in both dimensions than the corresponding upper-case letter (e.g. 'x' is smaller than 'X'). Thus, we further shrank some of the lower-case letter images, so that the larger dimension will be comprised of 16 pixels. Other lower-case letters (e.g.\ 'b' and 'p') were unchanged since in reality, their large dimension is of the same size as an upper-case letter. The lower-case letters that were shrunk are: 'a', 'c', 'e', 'n', 'o', 'r', 's', 'u', 'v', 'w', 'x', 'z'.

The images are contained in 6 folders, each containing the specific font name.

You can use the 'generate_font_dataset' script to get a dataset containing flattened numpy arrays representing the images. If you use this script, you should provide the name of the desired font, and the "external_input_strength"- i.e., the upper bound of the scale of images (the images will be scaled to the range [0, external_input_strength].
The script pads every dimension that is smaller than 20 pixels in every image with black pixels (valued 0), resulting in 20X20 pixel images. The padding is added equally on both sides of the image (where possible; in cases where the number of added pixels is odd, one side is padded with an additional pixel), resulting in a central location for the letter in the final image.
