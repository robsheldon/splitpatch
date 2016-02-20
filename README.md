## splitpatch - split big unified patch files into numbered smaller patch files

splitpatch is a shell script that reads in a unified patch file containing patches for multiple other files, and produces a series of numbered smaller patch files as output. Each output patch file modifies a single target file. splitpatch displays the name of each patch file it creates in the current directory along with the target file that the patch file will modify.

I wrote this because the popular splitdiff utility won't produce numbered output files, and I needed to troubleshoot an issue in a big unified patch file (obligatory "Magento sucks"). I wanted to be able to apply each patch in the unified patch file sequentially and splitdiff made that difficult. Also, it's written in Ruby and I thought something a little more portable would be nice.

I've tried to make the shell script fairly idiomatic and easy to read or modify. It should be compatible with most shells. Running it without arguments will give you a nicely formatted usage and description text. There are probably a lot of patch file formats that will break it. If you encounter something like that, please open an issue and I'll look into it. Including the patch file you're working with would be handy.


## Usage

splitpatch [-a] [-o] FILE


## Example

```
$ splitpatch PATCH_SUPEE-6788_CE_1.9.2.0_v1-2015-10-26-11-37-50.sh    

Writing 001.patch (.htaccess)...
Writing 002.patch (.htaccess.sample)...
```


## License

I am releasing this under the [ISC License](http://www.isc.org/downloads/software-support-policy/isc-license/), aka the OpenBSD license. You may use it, modify it, or share it for any purpose. A LICENSE file is included along with a brief version at the top of the splitpatch file.