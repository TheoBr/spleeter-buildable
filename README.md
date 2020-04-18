Trying to make a shippable binary out of Spleeter. This has been hellish.

To build:
`pyinstaller -F --noupx --log-level=WARN spleeter/__main__.py`

Test:
`./dist/__main__ separate -i {path to an audio file} -p spleeter:2stems -o output`

Current error:

```bash
Traceback (most recent call last):
  File "spleeter/__main__.py", line 58, in <module>
    entrypoint()
  File "spleeter/__main__.py", line 54, in entrypoint
    main(sys.argv)
  File "spleeter/__main__.py", line 36, in main
    enable_logging()
  File "spleeter/utils/logging.py", line 60, in enable_logging
    tf_logger = get_tensorflow_logger()
  File "spleeter/utils/logging.py", line 27, in get_tensorflow_logger
    from tensorflow.compat.v1 import logging
ModuleNotFoundError: No module named 'tensorflow'
[45973] Failed to execute script __main__
```

_Should be_ fixable if we get tensorflow to import nice
