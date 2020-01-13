# image_dissection
get dominant color, replace given color by choice of color, get fine image quality based on image nature

Algorithm for image dissection: 

1. get the list of all possible standard colors including white and black
2. a. Build dictionary that has key as standard color and values is the list of all nearest color in image exist.
3. Now for all above list :
   1. *get the percent of rgb count out of total image rgb's.
   2. Make dictionary (img_prime_rgb_dict) of key as most common rgb in list and values as list of rest of rgbs. 
   3. Make list (imp_prime_rgb) of those keys with its pix percent in respective segment, which has pix percent more than         3%.
4. get exceptional rgbs list (exceptional_rgbs) that has more than 3% pixels but not included into imp_prime_rgb.
5. For all exceptional rgbs:
   1. include these exceptional rgbs as keys in img_prime_rgb_dict.
   2. Append the rgbs into 5th step keys from the rgbs involve in its closest existing key based on lower distance.
6. final_prime_rgbs will be included both imp_prime_rgb and exceptional_rgbs.
7. In img_prime_rgb_dict, dictionary key's list diluted to closest final_prime_rgbs as key's list .
8. Now, this way, imp_prime_dict is builded. this dictinary will help to replace color in image.
