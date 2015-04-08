# mecab
Yet another Japanese morphological analyzer

## Python Bindings
Regarding broken Python bindings. Under Windows mecab-config is not available. Change setup.py accordingly.

``` python
setup(name = "mecab-python",
	version = "0.996",
	py_modules=["MeCab"],
	ext_modules = [
		Extension("_MeCab",
			["MeCab_wrap.cxx",],
			include_dirs=[r"C:\Program Files (x86)\MeCab\sdk"],
			library_dirs=[r"C:\Program Files (x86)\MeCab\sdk"],
			libraries=cmd2["libmecab"])
			])
```

Other error while building: error C2039: 'set_result' : is not a member of 'MeCab::Lattice'

``` c
class MECAB_DLL_CLASS_EXTERN Lattice {
public:
  virtual void set_result(const char *str) = 0;
```

For other problems: http://simudaru.hatenablog.com/entry/2014/05/11/010622
