---
publisher: "fullstackpython.com"
title: "Table of Contents for Full Stack Python"
lang: "en"
description: "Full Stack Python is an open book on Python web development, deployments and DevOps."
url: "https://www.fullstackpython.com/table-of-contents.html"
word_count: 4220
reading_time: "16 min read"
---

## Table of Contents

- [Table of Contents](#table-of-contents)
  - [1. Introduction](#1-introduction)
    - [1.1 Learning Programming](#11-learning-programming)
    - [1.2 Python Community](#12-python-community)
  - [2. Development Environments](#2-development-environments)
    - [2.1 Text Editors and IDEs](#21-text-editors-and-ides)
    - [2.2 Shells](#22-shells)
    - [2.3 Terminal multiplexers](#23-terminal-multiplexers)
    - [2.4 Environment configuration](#24-environment-configuration)
    - [2.5 Source Control](#25-source-control)
  - [3. Data](#3-data)
    - [3.1 Relational databases](#31-relational-databases)
    - [3.2 Object-relational mappers](#32-object-relational-mappers)
    - [3.3 NoSQL](#33-nosql)
    - [3.4 Data analysis](#34-data-analysis)
    - [3.5 Data visualization](#35-data-visualization)
    - [3.6 Markup Languages](#36-markup-languages)
  - [4. Web Development](#4-web-development)
    - [4.1 Web Frameworks](#41-web-frameworks)
    - [4.2 Template Engines](#42-template-engines)
    - [4.3 Web design](#43-web-design)
    - [4.4 CSS Frameworks](#44-css-frameworks)
    - [4.5 JavaScript](#45-javascript)
    - [4.6 Task queues](#46-task-queues)
    - [4.7 Static site generators](#47-static-site-generators)
    - [4.8 Testing](#48-testing)
    - [4.9 Networking](#49-networking)
    - [4.10 Web APIs](#410-web-apis)
    - [4.11 API creation](#411-api-creation)
    - [4.12 API integration](#412-api-integration)
    - [4.13 Web application security](#413-web-application-security)
  - [5. Web App Deployment](#5-web-app-deployment)
    - [5.1 Hosting](#51-hosting)
    - [5.2 Virtual Private Servers (VPSs)](#52-virtual-private-servers-vpss)
    - [5.3 Platform-as-a-Service](#53-platform-as-a-service)
    - [5.4 Operating systems](#54-operating-systems)
    - [5.5 Web servers](#55-web-servers)
    - [5.6 WSGI servers](#56-wsgi-servers)
    - [5.7 Continuous integration](#57-continuous-integration)
    - [5.8 Configuration management](#58-configuration-management)
    - [5.9 Containers](#59-containers)
    - [5.10 Serverless Architectures](#510-serverless-architectures)
  - [6. DevOps](#6-devops)
    - [6.1 Monitoring](#61-monitoring)
    - [6.2 Web App Performance](#62-web-app-performance)
  - [7. Meta](#7-meta)
- [Blog Post Tutorials](#blog-post-tutorials)
    - [Application Performance Monitoring AWS Lambda Functions with Sentry](#application-performance-monitoring-aws-lambda-functions-with-sentry)
    - [How to Monitor Python Functions on AWS Lambda with Sentry](#how-to-monitor-python-functions-on-aws-lambda-with-sentry)
    - [Using Django & AssemblyAI for More Accurate Twilio Call Transcriptions](#using-django--assemblyai-for-more-accurate-twilio-call-transcriptions)
    - [Higher Accuracy Twilio Voice Transcriptions with Python and Flask](#higher-accuracy-twilio-voice-transcriptions-with-python-and-flask)
    - [Using Sentry to Handle Python Exceptions in Django Projects](#using-sentry-to-handle-python-exceptions-in-django-projects)
    - [How to Transcribe Speech Recordings into Text with Python](#how-to-transcribe-speech-recordings-into-text-with-python)
    - [Tracking Daily User Data in Django with django-user-visit](#tracking-daily-user-data-in-django-with-django-user-visit)
    - [Quickly Use Bootstrap 4 in a Django Template with a CDN](#quickly-use-bootstrap-4-in-a-django-template-with-a-cdn)
    - [How to Report Errors in Flask Web Apps with Sentry](#how-to-report-errors-in-flask-web-apps-with-sentry)
    - [Reporting Exceptions in Python Scripts with Sentry](#reporting-exceptions-in-python-scripts-with-sentry)
    - [Exporting pandas DataFrames into SQLite with SQLAlchemy](#exporting-pandas-dataframes-into-sqlite-with-sqlalchemy)
    - [Learning pandas by Exploring COVID-19 Data](#learning-pandas-by-exploring-covid-19-data)
    - [The Best Resources for Developers to Learn Finance](#the-best-resources-for-developers-to-learn-finance)
    - [Basic Data Types in Python 3: Booleans](#basic-data-types-in-python-3-booleans)
    - [Basic Data Types in Python 3: Strings](#basic-data-types-in-python-3-strings)
    - [Developer-led Sales for Startups](#developer-led-sales-for-startups)
    - [Introduction to Ansible video course released!](#introduction-to-ansible-video-course-released)
    - [Adding Okta Authentication to an Existing Flask Web App](#adding-okta-authentication-to-an-existing-flask-web-app)
    - [Fresh Tutorials on Full Stack Python](#fresh-tutorials-on-full-stack-python)
    - [How to Provision Ubuntu 18.04 LTS Linux Servers on DigitalOcean](#how-to-provision-ubuntu-1804-lts-linux-servers-on-digitalocean)
    - [How to Add User Authentication to Flask Apps with Okta](#how-to-add-user-authentication-to-flask-apps-with-okta)
    - [Configure Python 3, Flask and Gunicorn on Ubuntu 18.04 LTS](#configure-python-3-flask-and-gunicorn-on-ubuntu-1804-lts)
    - [Running Bottle Apps in Docker Containers on macOS](#running-bottle-apps-in-docker-containers-on-macos)
    - [How to Explain Your Products to Developers](#how-to-explain-your-products-to-developers)
    - [How to Add Maps to Django Web App Projects with Mapbox](#how-to-add-maps-to-django-web-app-projects-with-mapbox)
    - [Full Stack Python at PyCon US 2018](#full-stack-python-at-pycon-us-2018)
    - [Monitoring Python 3.6 Functions on AWS Lambda](#monitoring-python-36-functions-on-aws-lambda)
    - [Developing Flask Apps in Docker Containers on macOS](#developing-flask-apps-in-docker-containers-on-macos)
    - [ReportLab and Future Community Project Launches](#reportlab-and-future-community-project-launches)
    - [Monitoring Django Projects with Rollbar](#monitoring-django-projects-with-rollbar)
    - [5 Years of Full Stack Python](#5-years-of-full-stack-python)
    - [GitPython and New Git Tutorials](#gitpython-and-new-git-tutorials)
    - [First Steps with GitPython](#first-steps-with-gitpython)
    - [DevOps, Thank You Maintainers and Contributing to Open Source](#devops-thank-you-maintainers-and-contributing-to-open-source)
    - [DevOps, Continuous Delivery... and You](#devops-continuous-delivery-and-you)
    - [PyDev of the Week, Django 2.0 and Twilio Voices](#pydev-of-the-week-django-20-and-twilio-voices)
    - [PyCon US 2018 CFP, Python Bytes and Pelican](#pycon-us-2018-cfp-python-bytes-and-pelican)
    - [How to Monitor Python Web Applications](#how-to-monitor-python-web-applications)
    - [How to Provision Ubuntu 16.04 Linux Servers on Linode](#how-to-provision-ubuntu-1604-linux-servers-on-linode)
    - [Creating Bar Chart Visuals with Bokeh, Bottle and Python 3](#creating-bar-chart-visuals-with-bokeh-bottle-and-python-3)
    - [How to Add Hosted Monitoring to Flask Web Applications](#how-to-add-hosted-monitoring-to-flask-web-applications)
    - [How to Create Your First Static Site with Pelican and Jinja2](#how-to-create-your-first-static-site-with-pelican-and-jinja2)
    - [Responsive Bar Charts with Bokeh, Flask and Python 3](#responsive-bar-charts-with-bokeh-flask-and-python-3)
    - [How to Become A Successful Self-Taught Software Developer](#how-to-become-a-successful-self-taught-software-developer)
    - [How to Create Your First Python 3.6 AWS Lambda Function](#how-to-create-your-first-python-36-aws-lambda-function)
    - [Getting Started with AWS Lambda & Python 2.7](#getting-started-with-aws-lambda--python-27)
    - [How to Choose the Right DevOps Tools for You and Your Team](#how-to-choose-the-right-devops-tools-for-you-and-your-team)
    - [Creating SSH Keys on macOS Sierra](#creating-ssh-keys-on-macos-sierra)
    - [Creating SSH Keys on Ubuntu Linux 16.04 LTS](#creating-ssh-keys-on-ubuntu-linux-1604-lts)
    - [How to Make Phone Calls in Python](#how-to-make-phone-calls-in-python)
    - [Dialing Outbound Phone Calls with a Bottle Web App](#dialing-outbound-phone-calls-with-a-bottle-web-app)
    - [Python for Entrepreneurs](#python-for-entrepreneurs)
    - [Setting Up Python 3, Django & Gunicorn on Linux Mint 17.3](#setting-up-python-3-django--gunicorn-on-linux-mint-173)
    - [Configuring Python 3, Pyramid and Gunicorn on Ubuntu 16.04](#configuring-python-3-pyramid-and-gunicorn-on-ubuntu-1604)
    - [Replying to SMS Text Messages with Python and Bottle](#replying-to-sms-text-messages-with-python-and-bottle)
    - [How to Build Your First Slack Bot with Python](#how-to-build-your-first-slack-bot-with-python)
    - [Responding to SMS Text Messages with Python & Flask](#responding-to-sms-text-messages-with-python--flask)
    - [How to Install and Use MySQL on Ubuntu 16.04](#how-to-install-and-use-mysql-on-ubuntu-1604)
    - [Setting up PostgreSQL with Python 3 and psycopg on Ubuntu 16.04](#setting-up-postgresql-with-python-3-and-psycopg-on-ubuntu-1604)
    - [How to Use Redis with Python 3 and redis-py on Ubuntu 16.04](#how-to-use-redis-with-python-3-and-redis-py-on-ubuntu-1604)
    - [How to Send MMS Picture Messages with Python](#how-to-send-mms-picture-messages-with-python)
    - [Configuring Python 3, Bottle and Gunicorn for Development on Ubuntu 16.04 LTS](#configuring-python-3-bottle-and-gunicorn-for-development-on-ubuntu-1604-lts)
    - [How to Send SMS Text Messages with Python](#how-to-send-sms-text-messages-with-python)
    - [How to set up Python 3, Flask and Green Unicorn on Ubuntu 16.04 LTS](#how-to-set-up-python-3-flask-and-green-unicorn-on-ubuntu-1604-lts)
    - [Setting up Python 3, Django and Gunicorn on Ubuntu 16.04 LTS](#setting-up-python-3-django-and-gunicorn-on-ubuntu-1604-lts)
    - [The Full Stack Python Blog](#the-full-stack-python-blog)
- [Books & Videos](#books--videos)
    - [Introduction to Ansible](#introduction-to-ansible)
    - [Python for Entrepreneurs](#python-for-entrepreneurs-1)
    - [Full Stack Python Supporter's Edition](#full-stack-python-supporters-edition)
    - [Deploying Flask Web Apps](#deploying-flask-web-apps)
    - [Developing a Real-Time Taxi App with Django Channels and Angular by Michael Herman](#developing-a-real-time-taxi-app-with-django-channels-and-angular-by-michael-herman)
    - [Test-Driven Development with Python, Flask, and Docker by Michael Herman](#test-driven-development-with-python-flask-and-docker-by-michael-herman)
    - [Deploying a Flask and React Microservice to AWS ECS by Michael Herman](#deploying-a-flask-and-react-microservice-to-aws-ecs-by-michael-herman)
- [Example Python Projects and Code](#example-python-projects-and-code)
  - [Django: Extensions, Plug-ins and Related Libraries & Example Projects and Code](#django-extensions-plug-ins-and-related-libraries--example-projects-and-code)
    - [django.apps.config AppConfig](#djangoappsconfig-appconfig)
    - [django.conf settings, urls.url](#djangoconf-settings-urlsurl)
    - [django.contrib.admin filters.SimpleListFilter,](#djangocontribadmin-filterssimplelistfilter)
    - [django.contrib.admin.helpers ActionForm, AdminForm](#djangocontribadminhelpers-actionform-adminform)
    - [django.contrib.admin.options IS_POPUP_VAR, IncorrectLookupParameters, ModelAdmin, csrf_protect_m](#djangocontribadminoptions-is_popup_var-incorrectlookupparameters-modeladmin-csrf_protect_m)
    - [django.contrib.admin.sites NotRegistered, register, site](#djangocontribadminsites-notregistered-register-site)
    - [django.contrib.auth get_user_model, decorators login_required, hashers make_password](#djangocontribauth-get_user_model-decorators-login_required-hashers-make_password)
    - [django.contrib.staticfiles finders,.finders BaseFinder,.finders BaseStorageFinder,.finders find,.finders get_finders.handlers StaticFilesHandler storage.storage CachedStaticFilesStorage,.storage HashedFilesMixin,.storage ManifestStaticFilesStorage,.storage StaticFilesStorage,.storage staticfiles_storage.utils matches_patterns](#djangocontribstaticfiles-findersfinders-basefinderfinders-basestoragefinderfinders-findfinders-get_findershandlers-staticfileshandler-storagestorage-cachedstaticfilesstoragestorage-hashedfilesmixinstorage-manifeststaticfilesstoragestorage-staticfilesstoragestorage-staticfiles_storageutils-matches_patterns)
    - [django.core cache, checks, exceptions, mail, mail.send_mail, mail.messages EmailMessage, management, management.base BaseCommand, serializers, signals, signing, validators](#djangocore-cache-checks-exceptions-mail-mailsend_mail-mailmessages-emailmessage-management-managementbase-basecommand-serializers-signals-signing-validators)
    - [django.core.exceptions DisallowedRedirect, FieldDoesNotExist, FieldError, ImproperlyConfigured, MiddlewareNotUsed, NON_FIELD_ERRORS, ObjectDoesNotExist, PermissionDenied, SuspiciousFileOperation, SuspiciousMultipartForm, ValidationError](#djangocoreexceptions-disallowedredirect-fielddoesnotexist-fielderror-improperlyconfigured-middlewarenotused-non_field_errors-objectdoesnotexist-permissiondenied-suspiciousfileoperation-suspiciousmultipartform-validationerror)
    - [django.db DEFAULT_DB_ALIAS, DataError, DatabaseError, IntegrityError, OperationalError, ProgrammingError, connection, connections, migrations, router, transaction.backends utils](#djangodb-default_db_alias-dataerror-databaseerror-integrityerror-operationalerror-programmingerror-connection-connections-migrations-router-transactionbackends-utils)
    - [django.db.migrations RunPython,.autodetector MigrationAutodetector,.exceptions IrreversibleError,.executor MigrationExecutor,.loader MIGRATIONS_MODULE_NAME,.loader MigrationLoader,.operations.base Operation,.state ProjectState](#djangodbmigrations-runpythonautodetector-migrationautodetectorexceptions-irreversibleerrorexecutor-migrationexecutorloader-migrations_module_nameloader-migrationloaderoperationsbase-operationstate-projectstate)
    - [django.db.models AutoField, BooleanField, CharField, DateField, DateTimeField, FileField, ForeignKey, GenericIPAddressField, ImageField, IntegerField, Model, PositiveIntegerField, PositiveSmallIntegerField, signal, SlugField, SmallIntegerField, TextField](#djangodbmodels-autofield-booleanfield-charfield-datefield-datetimefield-filefield-foreignkey-genericipaddressfield-imagefield-integerfield-model-positiveintegerfield-positivesmallintegerfield-signal-slugfield-smallintegerfield-textfield)
    - [django.db.models.query BaseIterable, EmptyQuerySet, ModelIterable, Prefetch, Q, QuerySet, prefetch_related_objects](#djangodbmodelsquery-baseiterable-emptyqueryset-modeliterable-prefetch-q-queryset-prefetch_related_objects)
    - [django.db.models.query_utils DeferredAttribute, PathInfo, Q](#djangodbmodelsquery_utils-deferredattribute-pathinfo-q)
    - [django.db.models.signals post_delete, post_save, pre_delete, pre_save](#djangodbmodelssignals-post_delete-post_save-pre_delete-pre_save)
    - [django.dispatch.dispatcher Signal](#djangodispatchdispatcher-signal)
    - [django.forms BaseForm, BooleanField, CharField, CheckboxInput, CheckboxSelectMultiple, ChoiceField, DateField, DateInput, DateTimeField, EmailField, Field, FileInput, FilePathField, Form, HiddenInput, ImageField, IntegerField, Media, MediaDefiningClass, ModelChoiceField, ModelForm, ModelMultipleChoiceField, MultipleChoiceField, Select, SelectMultiple, TypedChoiceField, ValidationError](#djangoforms-baseform-booleanfield-charfield-checkboxinput-checkboxselectmultiple-choicefield-datefield-dateinput-datetimefield-emailfield-field-fileinput-filepathfield-form-hiddeninput-imagefield-integerfield-media-mediadefiningclass-modelchoicefield-modelform-modelmultiplechoicefield-multiplechoicefield-select-selectmultiple-typedchoicefield-validationerror)
    - [django.http HttpResponse, HttpResponseBadRequest, HttpResponseForbidden, HttpResponseNotModified, Http404, HttpResponsePermanentRedirect, HttpResponseRedirect](#djangohttp-httpresponse-httpresponsebadrequest-httpresponseforbidden-httpresponsenotmodified-http404-httpresponsepermanentredirect-httpresponseredirect)
    - [django.shortcuts get_list_or_404, get_object_or_404, redirect, render, resolve_url](#djangoshortcuts-get_list_or_404-get_object_or_404-redirect-render-resolve_url)
    - [django.template.base Context, FilterExpression, Node, NodeList, Parser, Template, TemplateSyntaxError, TextNode, Token, TokenType, VariableDoesNotExist, VariableNode, token_kwargs](#djangotemplatebase-context-filterexpression-node-nodelist-parser-template-templatesyntaxerror-textnode-token-tokentype-variabledoesnotexist-variablenode-token_kwargs)
    - [django.template.context Context](#djangotemplatecontext-context)
    - [django.template.defaultfilters escape, filesizeformat, safe, slugify, striptags, title, truncatechars](#djangotemplatedefaultfilters-escape-filesizeformat-safe-slugify-striptags-title-truncatechars)
    - [django.template.loader get_template, render_to_string, select_template](#djangotemplateloader-get_template-render_to_string-select_template)
    - [django.template.loader_tags BlockNode, ExtendsNode, IncludeNode](#djangotemplateloader_tags-blocknode-extendsnode-includenode)
    - [django.template.loaders.filesystem Loader](#djangotemplateloadersfilesystem-loader)
    - [django.template.response SimpleTemplateResponse, TemplateResponse](#djangotemplateresponse-simpletemplateresponse-templateresponse)
    - [django.urls URLPattern, URLResolver, clear_url_caches, get_callable, get_resolver, get_script_prefix, include, path, re_path, register_converter, resolve, reverse, reverse_lazy](#djangourls-urlpattern-urlresolver-clear_url_caches-get_callable-get_resolver-get_script_prefix-include-path-re_path-register_converter-resolve-reverse-reverse_lazy)
    - [django.urls.exceptions NoReverseMatch, Resolver404](#djangourlsexceptions-noreversematch-resolver404)
    - [django.utils dateformat, dateparse, datetime_safe, formats, module_loading, termcolors, timezone, translation, tree](#djangoutils-dateformat-dateparse-datetime_safe-formats-module_loading-termcolors-timezone-translation-tree)
    - [django.utils.cache add_never_cache_headers, cc_delim_re, patch_cache_control, patch_response_headers, patch_vary_headers](#djangoutilscache-add_never_cache_headers-cc_delim_re-patch_cache_control-patch_response_headers-patch_vary_headers)
    - [django.utils.crypto constant_time_compare, get_random_string](#djangoutilscrypto-constant_time_compare-get_random_string)
    - [django.utils.datastructures MultiValueDict](#djangoutilsdatastructures-multivaluedict)
    - [django.utils.dateparse parse_datetime, parse_duration](#djangoutilsdateparse-parse_datetime-parse_duration)
    - [django.utils.dates MONTHS](#djangoutilsdates-months)
    - [django.utils.datetime_safe datetime](#djangoutilsdatetime_safe-datetime)
    - [django.utils.decorators method_decorator](#djangoutilsdecorators-method_decorator)
    - [django.utils.deprecation MiddlewareMixin, RenameMethodsBase](#djangoutilsdeprecation-middlewaremixin-renamemethodsbase)
    - [django.utils.duration duration_string](#djangoutilsduration-duration_string)
    - [django.utils.encoding DjangoUnicodeDecodeError, filepath_to_uri, force_bytes, force_str, force_text, iri_to_uri, is_protected_type, smart_bytes, smart_str, smart_text, uri_to_iri](#djangoutilsencoding-djangounicodedecodeerror-filepath_to_uri-force_bytes-force_str-force_text-iri_to_uri-is_protected_type-smart_bytes-smart_str-smart_text-uri_to_iri)
    - [django.utils.formats get_format, localize_input, sanitize_separators](#djangoutilsformats-get_format-localize_input-sanitize_separators)
    - [django.utils.functional LazyObject, Promise, SimpleLazyObject, keep_lazy, lazy, total_ordering, wraps](#djangoutilsfunctional-lazyobject-promise-simplelazyobject-keep_lazy-lazy-total_ordering-wraps)
    - [django.utils.html conditional_escape, escape, escapejs, format_html, format_html_join, mark_safe, smart_urlquote, strip_tags](#djangoutilshtml-conditional_escape-escape-escapejs-format_html-format_html_join-mark_safe-smart_urlquote-strip_tags)
    - [django.utils.http base36_to_int, http_date, int_to_base36, is_safe_url, unquote, url_has_allowed_host_and_scheme, urlencode, urlquote, urlunquote](#djangoutilshttp-base36_to_int-http_date-int_to_base36-is_safe_url-unquote-url_has_allowed_host_and_scheme-urlencode-urlquote-urlunquote)
    - [django.utils.ipv6 clean_ipv6_address](#djangoutilsipv6-clean_ipv6_address)
    - [django.utils.itercompat is_iterable](#djangoutilsitercompat-is_iterable)
    - [django.utils.module_loading autodiscover_modules, import_string, module_has_submodule](#djangoutilsmodule_loading-autodiscover_modules-import_string-module_has_submodule)
    - [django.utils.numberformat format](#djangoutilsnumberformat-format)
    - [django.utils.safestring SafeData, SafeText, mark_safe](#djangoutilssafestring-safedata-safetext-mark_safe)
    - [django.utils.termcolors colorize](#djangoutilstermcolors-colorize)
    - [django.utils.text Truncator, capfirst, format_lazy, get_text_list, get_valid_filename, slugify](#djangoutilstext-truncator-capfirst-format_lazy-get_text_list-get_valid_filename-slugify)
    - [django.utils.timezone get_current_timezone, make_aware, now, timedelta](#djangoutilstimezone-get_current_timezone-make_aware-now-timedelta)
    - [django.utils.translation LANGUAGE_SESSION_KEY, activate, deactivate_all, get_language, get_language_from_request, gettext, gettext_lazy, ngettext, override, pgettext, pgettext_lazy, ugettext, ugettext_lazy, ungettext, ungettext_lazy](#djangoutilstranslation-language_session_key-activate-deactivate_all-get_language-get_language_from_request-gettext-gettext_lazy-ngettext-override-pgettext-pgettext_lazy-ugettext-ugettext_lazy-ungettext-ungettext_lazy)
    - [django.utils.version get_complete_version](#djangoutilsversion-get_complete_version)
    - [django.views csrf.debug get_default_exception_reporter_filter.decorators.csrf csrf_exempt.decorators.debug sensitive_post_parameters.decorators.http require_GET,.decorators.http require_POST](#djangoviews-csrfdebug-get_default_exception_reporter_filterdecoratorscsrf-csrf_exemptdecoratorsdebug-sensitive_post_parametersdecoratorshttp-require_getdecoratorshttp-require_post)
    - [django.views.generic CreateView, DeleteView, DetailView, FormView, ListView, RedirectView, TemplateView, UpdateView, View](#djangoviewsgeneric-createview-deleteview-detailview-formview-listview-redirectview-templateview-updateview-view)
    - [django.views.generic.base RedirectView, TemplateResponseMixin, TemplateView, View](#djangoviewsgenericbase-redirectview-templateresponsemixin-templateview-view)
    - [django.views.generic.detail SingleObjectMixin](#djangoviewsgenericdetail-singleobjectmixin)
    - [django.views.generic.edit CreateView, DeleteView, DeletionMixin, FormMixin, FormView](#djangoviewsgenericedit-createview-deleteview-deletionmixin-formmixin-formview)
    - [django.views.generic.list ListView, MultipleObjectMixin](#djangoviewsgenericlist-listview-multipleobjectmixin)
    - [django.views.i18n JavaScriptCatalog](#djangoviewsi18n-javascriptcatalog)
    - [django.views.static serve, was_modified_since](#djangoviewsstatic-serve-was_modified_since)
  - [Flask: Extensions, Plug-ins and Related Libraries & Example Projects and Code](#flask-extensions-plug-ins-and-related-libraries--example-projects-and-code)
    - [flask.app BadRequest, Flask, Headers, ImmutableDict](#flaskapp-badrequest-flask-headers-immutabledict)
    - [flask.blueprints Blueprint](#flaskblueprints-blueprint)
    - [flask.cli AppGroup, DispatchingApp, FlaskGroup, ScriptInfo, pass_script_info, with_appcontext](#flaskcli-appgroup-dispatchingapp-flaskgroup-scriptinfo-pass_script_info-with_appcontext)
    - [flask.ctx after_this_request, has_app_context, has_request_context](#flaskctx-after_this_request-has_app_context-has_request_context)
    - [flask.globals current_app, g, request, session](#flaskglobals-current_app-g-request-session)
    - [flask.helpers flash, get_root_path, make_response, safe_join, send_file, url_for](#flaskhelpers-flash-get_root_path-make_response-safe_join-send_file-url_for)
    - [flask.json JSONEncoder, jsonify](#flaskjson-jsonencoder-jsonify)
    - [flask.sessions BadSignature, SessionInterface, SessionMixin](#flasksessions-badsignature-sessioninterface-sessionmixin)
    - [flask.signals Namespace, got_request_exception](#flasksignals-namespace-got_request_exception)
    - [flask.templating render_template, render_template_string](#flasktemplating-render_template-render_template_string)
    - [flask.views MethodView, View, http_method_funcs](#flaskviews-methodview-view-http_method_funcs)
  - [SQLAlchemy: Extensions, Plug-ins and Related Libraries & Example Projects and Code](#sqlalchemy-extensions-plug-ins-and-related-libraries--example-projects-and-code)
    - [sqlalchemy.databases mysql](#sqlalchemydatabases-mysql)
    - [sqlalchemy.dialects mssql, mysql, oracle, postgresql, sqlite](#sqlalchemydialects-mssql-mysql-oracle-postgresql-sqlite)
    - [sqlalchemy.dialects.mysql pymysql](#sqlalchemydialectsmysql-pymysql)
    - [sqlalchemy.dialects.postgresql ARRAY, BIGINT, BIT, DOUBLE_PRECISION, ExcludeConstraint, INTEGER, JSON, TSVECTOR, array, json, pypostgresql](#sqlalchemydialectspostgresql-array-bigint-bit-double_precision-excludeconstraint-integer-json-tsvector-array-json-pypostgresql)
    - [sqlalchemy.dialects.postgresql.base PGCompiler, PGIdentifierPreparer, PGTypeCompiler](#sqlalchemydialectspostgresqlbase-pgcompiler-pgidentifierpreparer-pgtypecompiler)
    - [sqlalchemy.dialects.postgresql.psycopg2 PGDialect_psycopg2](#sqlalchemydialectspostgresqlpsycopg2-pgdialect_psycopg2)
    - [sqlalchemy.dialects.sqlite pysqlite](#sqlalchemydialectssqlite-pysqlite)
    - [sqlalchemy.engine Connection, Engine, create_engine, default, url](#sqlalchemyengine-connection-engine-create_engine-default-url)
    - [sqlalchemy.engine.default DefaultDialect](#sqlalchemyenginedefault-defaultdialect)
    - [sqlalchemy.engine.interfaces ExecutionContext](#sqlalchemyengineinterfaces-executioncontext)
    - [sqlalchemy.engine.result ResultMetaData, RowProxy](#sqlalchemyengineresult-resultmetadata-rowproxy)
    - [sqlalchemy.engine.strategies EngineStrategy, MockEngineStrategy](#sqlalchemyenginestrategies-enginestrategy-mockenginestrategy)
    - [sqlalchemy.engine.url make_url](#sqlalchemyengineurl-make_url)
    - [sqlalchemy.events SchemaEventTarget](#sqlalchemyevents-schemaeventtarget)
    - [sqlalchemy.exc ArgumentError, DataError, DatabaseError, IntegrityError, InvalidRequestError, NoInspectionAvailable, NoSuchTableError, OperationalError, ProgrammingError, UnsupportedCompilationError](#sqlalchemyexc-argumenterror-dataerror-databaseerror-integrityerror-invalidrequesterror-noinspectionavailable-nosuchtableerror-operationalerror-programmingerror-unsupportedcompilationerror)
    - [sqlalchemy.ext compiler](#sqlalchemyext-compiler)
    - [sqlalchemy.ext.associationproxy AssociationProxy](#sqlalchemyextassociationproxy-associationproxy)
    - [sqlalchemy.ext.automap automap_base](#sqlalchemyextautomap-automap_base)
    - [sqlalchemy.ext.compiler compiles](#sqlalchemyextcompiler-compiles)
    - [sqlalchemy.ext.declarative DeclarativeMeta, declarative_base](#sqlalchemyextdeclarative-declarativemeta-declarative_base)
    - [sqlalchemy.ext.hybrid HYBRID_METHOD, HYBRID_PROPERTY, hybrid_method, hybrid_property](#sqlalchemyexthybrid-hybrid_method-hybrid_property-hybrid_method-hybrid_property)
    - [sqlalchemy.ext.mutable Mutable](#sqlalchemyextmutable-mutable)
    - [sqlalchemy.inspection inspect](#sqlalchemyinspection-inspect)
    - [sqlalchemy.orm ColumnProperty, CompositeProperty, Load, Mapper, Query, RelationshipProperty, Session, SynonymProperty, aliased, attributes, backref, class_mapper, column_property, composite, interfaces, mapper, mapperlib, object_mapper, object_session, query, relationship, session, sessionmaker, strategies](#sqlalchemyorm-columnproperty-compositeproperty-load-mapper-query-relationshipproperty-session-synonymproperty-aliased-attributes-backref-class_mapper-column_property-composite-interfaces-mapper-mapperlib-object_mapper-object_session-query-relationship-session-sessionmaker-strategies)
    - [sqlalchemy.orm.attributes InstrumentedAttribute, QueryableAttribute, flag_modified](#sqlalchemyormattributes-instrumentedattribute-queryableattribute-flag_modified)
    - [sqlalchemy.orm.collections InstrumentedList](#sqlalchemyormcollections-instrumentedlist)
    - [sqlalchemy.orm.exc NoResultFound, UnmappedClassError, UnmappedInstanceError](#sqlalchemyormexc-noresultfound-unmappedclasserror-unmappedinstanceerror)
    - [sqlalchemy.orm.interfaces MapperProperty, PropComparator](#sqlalchemyorminterfaces-mapperproperty-propcomparator)
    - [sqlalchemy.orm.mapper Mapper](#sqlalchemyormmapper-mapper)
    - [sqlalchemy.orm.properties ColumnProperty, RelationshipProperty](#sqlalchemyormproperties-columnproperty-relationshipproperty)
    - [sqlalchemy.orm.query Query, QueryContext](#sqlalchemyormquery-query-querycontext)
    - [sqlalchemy.orm.relationships RelationshipProperty](#sqlalchemyormrelationships-relationshipproperty)
    - [sqlalchemy.orm.session Session, object_session](#sqlalchemyormsession-session-object_session)
    - [sqlalchemy.orm.util AliasedClass, AliasedInsp, identity_key](#sqlalchemyormutil-aliasedclass-aliasedinsp-identity_key)
    - [sqlalchemy.pool NullPool, StaticPool](#sqlalchemypool-nullpool-staticpool)
    - [sqlalchemy.schema CheckConstraint, Column, CreateIndex, CreateTable, DDLElement, ForeignKey, ForeignKeyConstraint, Index, PrimaryKeyConstraint, Table](#sqlalchemyschema-checkconstraint-column-createindex-createtable-ddlelement-foreignkey-foreignkeyconstraint-index-primarykeyconstraint-table)
    - [sqlalchemy.sql ClauseElement, Select, column, expression, extract, functions, operators, schema, select, sqltypes, table](#sqlalchemysql-clauseelement-select-column-expression-extract-functions-operators-schema-select-sqltypes-table)
    - [sqlalchemy.sql.compiler SQLCompiler](#sqlalchemysqlcompiler-sqlcompiler)
    - [sqlalchemy.sql.elements ColumnElement, Label](#sqlalchemysqlelements-columnelement-label)
    - [sqlalchemy.sql.expression ClauseElement, ColumnClause, ColumnElement, Executable, FunctionElement, UnaryExpression](#sqlalchemysqlexpression-clauseelement-columnclause-columnelement-executable-functionelement-unaryexpression)
    - [sqlalchemy.sql.functions FunctionElement, GenericFunction](#sqlalchemysqlfunctions-functionelement-genericfunction)
    - [sqlalchemy.sql.naming conv](#sqlalchemysqlnaming-conv)
    - [sqlalchemy.sql.schema Column, SchemaItem](#sqlalchemysqlschema-column-schemaitem)
    - [sqlalchemy.sql.sqltypes NULLTYPE, NullType](#sqlalchemysqlsqltypes-nulltype-nulltype)
    - [sqlalchemy.sql.util ClauseAdapter](#sqlalchemysqlutil-clauseadapter)
    - [sqlalchemy.sql.visitors traverse](#sqlalchemysqlvisitors-traverse)
    - [sqlalchemy.types BOOLEAN, Boolean, DATE, DATETIME, Date, DateTime, Enum, FLOAT, Float, INTEGER, Integer, Interval, NULLTYPE, NullType, String, TEXT, TIME, Text, Time, TypeEngine, UserDefinedType, to_instance](#sqlalchemytypes-boolean-boolean-date-datetime-date-datetime-enum-float-float-integer-integer-interval-nulltype-nulltype-string-text-time-text-time-typeengine-userdefinedtype-to_instance)
    - [sqlalchemy.util OrderedDict, OrderedSet, set_creation_order, symbol, topological](#sqlalchemyutil-ordereddict-orderedset-set_creation_order-symbol-topological)
    - [sqlalchemy.util.langhelpers public_factory, symbol](#sqlalchemyutillanghelpers-public_factory-symbol)

---

[Full Stack Python](https://www.fullstackpython.com/)

[All topics](https://www.fullstackpython.com/table-of-contents.html) \| [Blog](https://www.fullstackpython.com/blog.html) \| [Supporter's Edition](https://www.deploypython.com/full-stack-python.html) \| [@fullstackpython](https://twitter.com/fullstackpython) \| [Facebook](https://www.facebook.com/fullstackpython) \| [What's new?](https://www.fullstackpython.com/change-log.html)

## Table of Contents

### 1. Introduction

#### 1.1 Learning Programming

[The Python Language](https://www.fullstackpython.com/python-programming-language.html)

[Why Use Python?](https://www.fullstackpython.com/why-use-python.html)

[Python 2 or 3?](https://www.fullstackpython.com/python-2-or-3.html)

[Enterprise Python](https://www.fullstackpython.com/enterprise-python.html)

#### 1.2 Python Community

[Companies Using Python](https://www.fullstackpython.com/companies-using-python.html)

[Best Python Resources](https://www.fullstackpython.com/best-python-resources.html)

[Must-watch Python Videos](https://www.fullstackpython.com/best-python-videos.html)

[Podcasts](https://www.fullstackpython.com/best-python-podcasts.html)

### 2. Development Environments

#### 2.1 Text Editors and IDEs

[Vim](https://www.fullstackpython.com/vim.html)

[Emacs](https://www.fullstackpython.com/emacs.html)

[Sublime Text](https://www.fullstackpython.com/sublime-text.html)

[PyCharm](https://www.fullstackpython.com/pycharm.html)

[Jupyter Notebook](https://www.fullstackpython.com/jupyter-notebook.html)

#### 2.2 Shells

[Bourne-again shell (Bash)](https://www.fullstackpython.com/bourne-again-shell-bash.html)

[Zsh](https://www.fullstackpython.com/zsh-shell.html)

[PowerShell](https://www.fullstackpython.com/powershell.html)

#### 2.3 Terminal multiplexers

[tmux](https://www.fullstackpython.com/tmux.html)

[Screen](https://www.fullstackpython.com/screen.html)

#### 2.4 Environment configuration

[Application dependencies](https://www.fullstackpython.com/application-dependencies.html)

[virtual environments (virtualenvs)](https://www.fullstackpython.com/virtual-environments-virtualenvs-venvs.html)

[Localhost tunnels](https://www.fullstackpython.com/localhost-tunnels.html)

#### 2.5 Source Control

[Git](https://www.fullstackpython.com/git.html)

[Mercurial](https://www.fullstackpython.com/mercurial.html)

### 3. Data

#### 3.1 Relational databases

[PostgreSQL](https://www.fullstackpython.com/postgresql.html)

[MySQL](https://www.fullstackpython.com/mysql.html)

[SQLite](https://www.fullstackpython.com/sqlite.html)

#### 3.2 Object-relational mappers

[SQLAlchemy](https://www.fullstackpython.com/sqlalchemy.html)

[Peewee](https://www.fullstackpython.com/peewee.html)

[Django ORM](https://www.fullstackpython.com/django-orm.html)

[Pony ORM](https://www.fullstackpython.com/pony-orm.html)

#### 3.3 NoSQL

[Redis](https://www.fullstackpython.com/redis.html)

[MongoDB](https://www.fullstackpython.com/mongodb.html)

[Apache Cassandra](https://www.fullstackpython.com/apache-cassandra.html)

[Neo4j](https://www.fullstackpython.com/neo4j.html)

#### 3.4 Data analysis

[pandas](https://www.fullstackpython.com/pandas.html)

[SciPy & Numpy](https://www.fullstackpython.com/scipy-numpy.html)

#### 3.5 Data visualization

[Bokeh](https://www.fullstackpython.com/bokeh.html)

[d3.js](https://www.fullstackpython.com/d3-js.html)

[Matplotlib](https://www.fullstackpython.com/matplotlib.html)

#### 3.6 Markup Languages

[Markdown](https://www.fullstackpython.com/markdown.html)

[reStructuredText](https://www.fullstackpython.com/restructuredtext.html)

### 4. Web Development

#### 4.1 Web Frameworks

[Django](https://www.fullstackpython.com/django.html)

[Flask](https://www.fullstackpython.com/flask.html)

[Bottle](https://www.fullstackpython.com/bottle.html)

[Pyramid](https://www.fullstackpython.com/pyramid.html)

[TurboGears](https://www.fullstackpython.com/turbogears.html)

[Falcon](https://www.fullstackpython.com/falcon.html)

[Morepath](https://www.fullstackpython.com/morepath.html)

[Sanic](https://www.fullstackpython.com/sanic.html)

[Other web frameworks](https://www.fullstackpython.com/other-web-frameworks.html)

#### 4.2 Template Engines

[Jinja2](https://www.fullstackpython.com/jinja2.html)

[Mako](https://www.fullstackpython.com/mako.html)

[Django Templates](https://www.fullstackpython.com/django-templates.html)

#### 4.3 Web design

[HTML](https://www.fullstackpython.com/hypertext-markup-language-html.html)

[CSS](https://www.fullstackpython.com/cascading-style-sheets.html)

[Responsive Design](https://www.fullstackpython.com/responsive-design.html)

[Minification](https://www.fullstackpython.com/minification.html)

#### 4.4 CSS Frameworks

[Bootstrap](https://www.fullstackpython.com/bootstrap-css.html)

[Foundation](https://www.fullstackpython.com/foundation-css.html)

#### 4.5 JavaScript

[React](https://www.fullstackpython.com/react.html)

[Vue.js](https://www.fullstackpython.com/vuejs.html)

[Angular](https://www.fullstackpython.com/angular.html)

#### 4.6 Task queues

[Celery](https://www.fullstackpython.com/celery.html)

[Redis Queue (RQ)](https://www.fullstackpython.com/redis-queue-rq.html)

[Dramatiq](https://www.fullstackpython.com/dramatiq.html)

#### 4.7 Static site generators

[Pelican](https://www.fullstackpython.com/pelican.html)

[Lektor](https://www.fullstackpython.com/lektor.html)

[MkDocs](https://www.fullstackpython.com/mkdocs.html)

#### 4.8 Testing

[Unit testing](https://www.fullstackpython.com/unit-testing.html)

[Integration testing](https://www.fullstackpython.com/integration-testing.html)

[Debugging](https://www.fullstackpython.com/debugging.html)

[Code Metrics](https://www.fullstackpython.com/code-metrics.html)

#### 4.9 Networking

[HTTPS](https://www.fullstackpython.com/https.html)

[WebSockets](https://www.fullstackpython.com/websockets.html)

[WebRTC](https://www.fullstackpython.com/webrtc.html)

#### 4.10 Web APIs

[Microservices](https://www.fullstackpython.com/microservices.html)

[Webhooks](https://www.fullstackpython.com/webhooks.html)

[Bots](https://www.fullstackpython.com/bots.html)

#### 4.11 API creation

[API Frameworks](https://www.fullstackpython.com/api-frameworks.html)

[Django REST Framework](https://www.fullstackpython.com/django-rest-framework-drf.html)

#### 4.12 API integration

[Twilio](https://www.fullstackpython.com/twilio.html)

[Stripe](https://www.fullstackpython.com/stripe.html)

[Slack](https://www.fullstackpython.com/slack.html)

[Okta](https://www.fullstackpython.com/okta.html)

#### 4.13 Web application security

[SQL injection](https://www.fullstackpython.com/sql-injection.html)

[Cross-Site Request Forgery](https://www.fullstackpython.com/cross-site-request-forgery-csrf.html)

### 5. Web App Deployment

#### 5.1 Hosting

[Servers](https://www.fullstackpython.com/servers.html)

[Static content](https://www.fullstackpython.com/static-content.html)

[Content Delivery Networks (CDNs)](https://www.fullstackpython.com/content-delivery-networks-cdns.html)

#### 5.2 Virtual Private Servers (VPSs)

[Linode](https://www.fullstackpython.com/linode.html)

[DigitalOcean](https://www.fullstackpython.com/digitalocean.html)

[Lightsail](https://www.fullstackpython.com/lightsail.html)

#### 5.3 Platform-as-a-Service

[Heroku](https://www.fullstackpython.com/heroku.html)

[PythonAnywhere](https://www.fullstackpython.com/pythonanywhere.html)

[AWS CodeStar](https://www.fullstackpython.com/aws-codestar.html)

#### 5.4 Operating systems

[Ubuntu Linux](https://www.fullstackpython.com/ubuntu.html)

[macOS](https://www.fullstackpython.com/macos.html)

[FreeBSD](https://www.fullstackpython.com/freebsd.html)

[Windows](https://www.fullstackpython.com/microsoft-windows.html)

#### 5.5 Web servers

[Apache HTTP Server](https://www.fullstackpython.com/apache-http-server.html)

[Nginx](https://www.fullstackpython.com/nginx.html)

[Caddy](https://www.fullstackpython.com/caddy.html)

#### 5.6 WSGI servers

[Green Unicorn](https://www.fullstackpython.com/green-unicorn-gunicorn.html)

[uWSGI](https://www.fullstackpython.com/uwsgi.html)

[mod_wsgi](https://www.fullstackpython.com/mod-wsgi.html)

#### 5.7 Continuous integration

[Jenkins](https://www.fullstackpython.com/jenkins.html)

[GoCD](https://www.fullstackpython.com/gocd-continuous-integration.html)

#### 5.8 Configuration management

[Ansible](https://www.fullstackpython.com/ansible.html)

[Salt](https://www.fullstackpython.com/salt.html)

#### 5.9 Containers

[Docker](https://www.fullstackpython.com/docker.html)

[Kubernetes](https://www.fullstackpython.com/kubernetes.html)

#### 5.10 Serverless Architectures

[AWS Lambda](https://www.fullstackpython.com/aws-lambda.html)

[Azure Functions](https://www.fullstackpython.com/azure-functions.html)

[Google Cloud Functions](https://www.fullstackpython.com/google-cloud-functions.html)

### 6. DevOps

#### 6.1 Monitoring

[Datadog](https://www.fullstackpython.com/datadog.html)

[Prometheus](https://www.fullstackpython.com/prometheus.html)

[Rollbar](https://www.fullstackpython.com/rollbar.html)

[Sentry](https://www.fullstackpython.com/sentry.html)

#### 6.2 Web App Performance

[Logging](https://www.fullstackpython.com/logging.html)

[Caching](https://www.fullstackpython.com/caching.html)

[Web Analytics](https://www.fullstackpython.com/web-analytics.html)

### 7. Meta

[Change log](https://www.fullstackpython.com/change-log.html)

[About the author](https://www.fullstackpython.com/about-author.html)

[What "full stack" means](https://www.fullstackpython.com/what-full-stack-means.html)

[Page Statuses](https://www.fullstackpython.com/page-statuses.html)

[Future directions](https://www.fullstackpython.com/future-directions.html)

## Blog Post Tutorials

#### Application Performance Monitoring AWS Lambda Functions with Sentry

#### How to Monitor Python Functions on AWS Lambda with Sentry

#### Using Django & AssemblyAI for More Accurate Twilio Call Transcriptions

#### Higher Accuracy Twilio Voice Transcriptions with Python and Flask

#### Using Sentry to Handle Python Exceptions in Django Projects

#### How to Transcribe Speech Recordings into Text with Python

#### Tracking Daily User Data in Django with django-user-visit

#### Quickly Use Bootstrap 4 in a Django Template with a CDN

#### How to Report Errors in Flask Web Apps with Sentry

#### Reporting Exceptions in Python Scripts with Sentry

#### Exporting pandas DataFrames into SQLite with SQLAlchemy

#### Learning pandas by Exploring COVID-19 Data

#### The Best Resources for Developers to Learn Finance

#### Basic Data Types in Python 3: Booleans

#### Basic Data Types in Python 3: Strings

#### Developer-led Sales for Startups

#### Introduction to Ansible video course released!

#### Adding Okta Authentication to an Existing Flask Web App

#### Fresh Tutorials on Full Stack Python

#### How to Provision Ubuntu 18.04 LTS Linux Servers on DigitalOcean

#### How to Add User Authentication to Flask Apps with Okta

#### Configure Python 3, Flask and Gunicorn on Ubuntu 18.04 LTS

#### Running Bottle Apps in Docker Containers on macOS

#### How to Explain Your Products to Developers

#### How to Add Maps to Django Web App Projects with Mapbox

#### Full Stack Python at PyCon US 2018

#### Monitoring Python 3.6 Functions on AWS Lambda

#### Developing Flask Apps in Docker Containers on macOS

#### ReportLab and Future Community Project Launches

#### Monitoring Django Projects with Rollbar

#### 5 Years of Full Stack Python

#### GitPython and New Git Tutorials

#### First Steps with GitPython

#### DevOps, Thank You Maintainers and Contributing to Open Source

#### DevOps, Continuous Delivery... and You

#### PyDev of the Week, Django 2.0 and Twilio Voices

#### PyCon US 2018 CFP, Python Bytes and Pelican

#### How to Monitor Python Web Applications

#### How to Provision Ubuntu 16.04 Linux Servers on Linode

#### Creating Bar Chart Visuals with Bokeh, Bottle and Python 3

#### How to Add Hosted Monitoring to Flask Web Applications

#### How to Create Your First Static Site with Pelican and Jinja2

#### Responsive Bar Charts with Bokeh, Flask and Python 3

#### How to Become A Successful Self-Taught Software Developer

#### How to Create Your First Python 3.6 AWS Lambda Function

#### Getting Started with AWS Lambda & Python 2.7

#### How to Choose the Right DevOps Tools for You and Your Team

#### Creating SSH Keys on macOS Sierra

#### Creating SSH Keys on Ubuntu Linux 16.04 LTS

#### How to Make Phone Calls in Python

#### Dialing Outbound Phone Calls with a Bottle Web App

#### Python for Entrepreneurs

#### Setting Up Python 3, Django & Gunicorn on Linux Mint 17.3

#### Configuring Python 3, Pyramid and Gunicorn on Ubuntu 16.04

#### Replying to SMS Text Messages with Python and Bottle

#### How to Build Your First Slack Bot with Python

#### Responding to SMS Text Messages with Python & Flask

#### How to Install and Use MySQL on Ubuntu 16.04

#### Setting up PostgreSQL with Python 3 and psycopg on Ubuntu 16.04

#### How to Use Redis with Python 3 and redis-py on Ubuntu 16.04

#### How to Send MMS Picture Messages with Python

#### Configuring Python 3, Bottle and Gunicorn for Development on Ubuntu 16.04 LTS

#### How to Send SMS Text Messages with Python

#### How to set up Python 3, Flask and Green Unicorn on Ubuntu 16.04 LTS

#### Setting up Python 3, Django and Gunicorn on Ubuntu 16.04 LTS

#### The Full Stack Python Blog

## Books & Videos

Each of these videos and books was recorded or written by me, [Matt Makai](https://www.fullstackpython.com/about-author.html).

#### Introduction to Ansible

#### Python for Entrepreneurs

#### Full Stack Python Supporter's Edition

#### Deploying Flask Web Apps

------------------------------------------------------------------------

These books and courses were created by fellow Python developers. I have used each one myself and recommend them all if you are looking to buy high quality resources.

#### Developing a Real-Time Taxi App with Django Channels and Angular by Michael Herman

#### Test-Driven Development with Python, Flask, and Docker by Michael Herman

#### Deploying a Flask and React Microservice to AWS ECS by Michael Herman

## Example Python Projects and Code

### Django: Extensions, Plug-ins and Related Libraries & Example Projects and Code

#### django.apps.config AppConfig

#### django.conf settings, urls.url

#### django.contrib.admin filters.SimpleListFilter,

#### django.contrib.admin.helpers ActionForm, AdminForm

#### django.contrib.admin.options IS_POPUP_VAR, IncorrectLookupParameters, ModelAdmin, csrf_protect_m

#### django.contrib.admin.sites NotRegistered, register, site

#### django.contrib.auth get_user_model, decorators login_required, hashers make_password

#### django.contrib.staticfiles finders,.finders BaseFinder,.finders BaseStorageFinder,.finders find,.finders get_finders.handlers StaticFilesHandler storage.storage CachedStaticFilesStorage,.storage HashedFilesMixin,.storage ManifestStaticFilesStorage,.storage StaticFilesStorage,.storage staticfiles_storage.utils matches_patterns

#### django.core cache, checks, exceptions, mail, mail.send_mail, mail.messages EmailMessage, management, management.base BaseCommand, serializers, signals, signing, validators

#### django.core.exceptions DisallowedRedirect, FieldDoesNotExist, FieldError, ImproperlyConfigured, MiddlewareNotUsed, NON_FIELD_ERRORS, ObjectDoesNotExist, PermissionDenied, SuspiciousFileOperation, SuspiciousMultipartForm, ValidationError

#### django.db DEFAULT_DB_ALIAS, DataError, DatabaseError, IntegrityError, OperationalError, ProgrammingError, connection, connections, migrations, router, transaction.backends utils

#### django.db.migrations RunPython,.autodetector MigrationAutodetector,.exceptions IrreversibleError,.executor MigrationExecutor,.loader MIGRATIONS_MODULE_NAME,.loader MigrationLoader,.operations.base Operation,.state ProjectState

#### django.db.models AutoField, BooleanField, CharField, DateField, DateTimeField, FileField, ForeignKey, GenericIPAddressField, ImageField, IntegerField, Model, PositiveIntegerField, PositiveSmallIntegerField, signal, SlugField, SmallIntegerField, TextField

#### django.db.models.query BaseIterable, EmptyQuerySet, ModelIterable, Prefetch, Q, QuerySet, prefetch_related_objects

#### django.db.models.query_utils DeferredAttribute, PathInfo, Q

#### django.db.models.signals post_delete, post_save, pre_delete, pre_save

#### django.dispatch.dispatcher Signal

#### django.forms BaseForm, BooleanField, CharField, CheckboxInput, CheckboxSelectMultiple, ChoiceField, DateField, DateInput, DateTimeField, EmailField, Field, FileInput, FilePathField, Form, HiddenInput, ImageField, IntegerField, Media, MediaDefiningClass, ModelChoiceField, ModelForm, ModelMultipleChoiceField, MultipleChoiceField, Select, SelectMultiple, TypedChoiceField, ValidationError

#### django.http HttpResponse, HttpResponseBadRequest, HttpResponseForbidden, HttpResponseNotModified, Http404, HttpResponsePermanentRedirect, HttpResponseRedirect

#### django.shortcuts get_list_or_404, get_object_or_404, redirect, render, resolve_url

#### django.template.base Context, FilterExpression, Node, NodeList, Parser, Template, TemplateSyntaxError, TextNode, Token, TokenType, VariableDoesNotExist, VariableNode, token_kwargs

#### django.template.context Context

#### django.template.defaultfilters escape, filesizeformat, safe, slugify, striptags, title, truncatechars

#### django.template.loader get_template, render_to_string, select_template

#### django.template.loader_tags BlockNode, ExtendsNode, IncludeNode

#### django.template.loaders.filesystem Loader

#### django.template.response SimpleTemplateResponse, TemplateResponse

#### django.urls URLPattern, URLResolver, clear_url_caches, get_callable, get_resolver, get_script_prefix, include, path, re_path, register_converter, resolve, reverse, reverse_lazy

#### django.urls.exceptions NoReverseMatch, Resolver404

#### django.utils dateformat, dateparse, datetime_safe, formats, module_loading, termcolors, timezone, translation, tree

#### django.utils.cache add_never_cache_headers, cc_delim_re, patch_cache_control, patch_response_headers, patch_vary_headers

#### django.utils.crypto constant_time_compare, get_random_string

#### django.utils.datastructures MultiValueDict

#### django.utils.dateparse parse_datetime, parse_duration

#### django.utils.dates MONTHS

#### django.utils.datetime_safe datetime

#### django.utils.decorators method_decorator

#### django.utils.deprecation MiddlewareMixin, RenameMethodsBase

#### django.utils.duration duration_string

#### django.utils.encoding DjangoUnicodeDecodeError, filepath_to_uri, force_bytes, force_str, force_text, iri_to_uri, is_protected_type, smart_bytes, smart_str, smart_text, uri_to_iri

#### django.utils.formats get_format, localize_input, sanitize_separators

#### django.utils.functional LazyObject, Promise, SimpleLazyObject, keep_lazy, lazy, total_ordering, wraps

#### django.utils.html conditional_escape, escape, escapejs, format_html, format_html_join, mark_safe, smart_urlquote, strip_tags

#### django.utils.http base36_to_int, http_date, int_to_base36, is_safe_url, unquote, url_has_allowed_host_and_scheme, urlencode, urlquote, urlunquote

#### django.utils.ipv6 clean_ipv6_address

#### django.utils.itercompat is_iterable

#### django.utils.module_loading autodiscover_modules, import_string, module_has_submodule

#### django.utils.numberformat format

#### django.utils.safestring SafeData, SafeText, mark_safe

#### django.utils.termcolors colorize

#### django.utils.text Truncator, capfirst, format_lazy, get_text_list, get_valid_filename, slugify

#### django.utils.timezone get_current_timezone, make_aware, now, timedelta

#### django.utils.translation LANGUAGE_SESSION_KEY, activate, deactivate_all, get_language, get_language_from_request, gettext, gettext_lazy, ngettext, override, pgettext, pgettext_lazy, ugettext, ugettext_lazy, ungettext, ungettext_lazy

#### django.utils.version get_complete_version

#### django.views csrf.debug get_default_exception_reporter_filter.decorators.csrf csrf_exempt.decorators.debug sensitive_post_parameters.decorators.http require_GET,.decorators.http require_POST

#### django.views.generic CreateView, DeleteView, DetailView, FormView, ListView, RedirectView, TemplateView, UpdateView, View

#### django.views.generic.base RedirectView, TemplateResponseMixin, TemplateView, View

#### django.views.generic.detail SingleObjectMixin

#### django.views.generic.edit CreateView, DeleteView, DeletionMixin, FormMixin, FormView

#### django.views.generic.list ListView, MultipleObjectMixin

#### django.views.i18n JavaScriptCatalog

#### django.views.static serve, was_modified_since

### Flask: Extensions, Plug-ins and Related Libraries & Example Projects and Code

#### flask.app BadRequest, Flask, Headers, ImmutableDict

#### flask.blueprints Blueprint

#### flask.cli AppGroup, DispatchingApp, FlaskGroup, ScriptInfo, pass_script_info, with_appcontext

#### flask.ctx after_this_request, has_app_context, has_request_context

#### flask.globals current_app, g, request, session

#### flask.helpers flash, get_root_path, make_response, safe_join, send_file, url_for

#### flask.json JSONEncoder, jsonify

#### flask.sessions BadSignature, SessionInterface, SessionMixin

#### flask.signals Namespace, got_request_exception

#### flask.templating render_template, render_template_string

#### flask.views MethodView, View, http_method_funcs

### SQLAlchemy: Extensions, Plug-ins and Related Libraries & Example Projects and Code

#### sqlalchemy.databases mysql

#### sqlalchemy.dialects mssql, mysql, oracle, postgresql, sqlite

#### sqlalchemy.dialects.mysql pymysql

#### sqlalchemy.dialects.postgresql ARRAY, BIGINT, BIT, DOUBLE_PRECISION, ExcludeConstraint, INTEGER, JSON, TSVECTOR, array, json, pypostgresql

#### sqlalchemy.dialects.postgresql.base PGCompiler, PGIdentifierPreparer, PGTypeCompiler

#### sqlalchemy.dialects.postgresql.psycopg2 PGDialect_psycopg2

#### sqlalchemy.dialects.sqlite pysqlite

#### sqlalchemy.engine Connection, Engine, create_engine, default, url

#### sqlalchemy.engine.default DefaultDialect

#### sqlalchemy.engine.interfaces ExecutionContext

#### sqlalchemy.engine.result ResultMetaData, RowProxy

#### sqlalchemy.engine.strategies EngineStrategy, MockEngineStrategy

#### sqlalchemy.engine.url make_url

#### sqlalchemy.events SchemaEventTarget

#### sqlalchemy.exc ArgumentError, DataError, DatabaseError, IntegrityError, InvalidRequestError, NoInspectionAvailable, NoSuchTableError, OperationalError, ProgrammingError, UnsupportedCompilationError

#### sqlalchemy.ext compiler

#### sqlalchemy.ext.associationproxy AssociationProxy

#### sqlalchemy.ext.automap automap_base

#### sqlalchemy.ext.compiler compiles

#### sqlalchemy.ext.declarative DeclarativeMeta, declarative_base

#### sqlalchemy.ext.hybrid HYBRID_METHOD, HYBRID_PROPERTY, hybrid_method, hybrid_property

#### sqlalchemy.ext.mutable Mutable

#### sqlalchemy.inspection inspect

#### sqlalchemy.orm ColumnProperty, CompositeProperty, Load, Mapper, Query, RelationshipProperty, Session, SynonymProperty, aliased, attributes, backref, class_mapper, column_property, composite, interfaces, mapper, mapperlib, object_mapper, object_session, query, relationship, session, sessionmaker, strategies

#### sqlalchemy.orm.attributes InstrumentedAttribute, QueryableAttribute, flag_modified

#### sqlalchemy.orm.collections InstrumentedList

#### sqlalchemy.orm.exc NoResultFound, UnmappedClassError, UnmappedInstanceError

#### sqlalchemy.orm.interfaces MapperProperty, PropComparator

#### sqlalchemy.orm.mapper Mapper

#### sqlalchemy.orm.properties ColumnProperty, RelationshipProperty

#### sqlalchemy.orm.query Query, QueryContext

#### sqlalchemy.orm.relationships RelationshipProperty

#### sqlalchemy.orm.session Session, object_session

#### sqlalchemy.orm.util AliasedClass, AliasedInsp, identity_key

#### sqlalchemy.pool NullPool, StaticPool

#### sqlalchemy.schema CheckConstraint, Column, CreateIndex, CreateTable, DDLElement, ForeignKey, ForeignKeyConstraint, Index, PrimaryKeyConstraint, Table

#### sqlalchemy.sql ClauseElement, Select, column, expression, extract, functions, operators, schema, select, sqltypes, table

#### sqlalchemy.sql.compiler SQLCompiler

#### sqlalchemy.sql.elements ColumnElement, Label

#### sqlalchemy.sql.expression ClauseElement, ColumnClause, ColumnElement, Executable, FunctionElement, UnaryExpression

#### sqlalchemy.sql.functions FunctionElement, GenericFunction

#### sqlalchemy.sql.naming conv

#### sqlalchemy.sql.schema Column, SchemaItem

#### sqlalchemy.sql.sqltypes NULLTYPE, NullType

#### sqlalchemy.sql.util ClauseAdapter

#### sqlalchemy.sql.visitors traverse

#### sqlalchemy.types BOOLEAN, Boolean, DATE, DATETIME, Date, DateTime, Enum, FLOAT, Float, INTEGER, Integer, Interval, NULLTYPE, NullType, String, TEXT, TIME, Text, Time, TypeEngine, UserDefinedType, to_instance

#### sqlalchemy.util OrderedDict, OrderedSet, set_creation_order, symbol, topological

#### sqlalchemy.util.langhelpers public_factory, symbol

------------------------------------------------------------------------

[Matt Makai](https://www.fullstackpython.com/about-author.html) [2012-2022](https://www.fullstackpython.com/change-log.html)