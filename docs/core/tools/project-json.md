---
title: Referencia project.json | Microsoft Docs
description: referencia de project.json
keywords: .NET, .NET Core, project.json
author: aL3891
ms.author: mairaw
ms.date: 12/21/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 3aef32bd-ee2a-4e24-80f8-a2b615e0336d
translationtype: Human Translation
ms.sourcegitcommit: 8fba5c76375763abf90e2e17d3bcc9d0039089f0
ms.openlocfilehash: 2cdb43a9095217498c12c97548e4aa632b13a59c

---

# <a name="projectjson-reference"></a>referencia de project.json

> [!WARNING]
> Este tema se aplica a .NET Core Tools Preview 2. Para la documentación de .NET Core Tools RC4, consulte el tema [Herramientas de la interfaz de la línea de comandos de .NET Core (.NET Core Tools RC4)](../preview3/tools/index.md).

El archivo project.json se usa en proyectos .NET Core para definir los metadatos del proyecto, información sobre la compilación y las dependencias. En este tema de referencia verá la lista de todas las propiedades que puede definir en el archivo project.json.

> [!NOTE]
> En una futura versión, las herramientas de .NET Core migrarán de project.json a proyectos basados en MSBuild. Por ahora, se recomienda que siga usando archivos project.json para los proyectos nuevos de .NET Core porque existirá una ruta para convertir el proyecto a MSBuild cuando se lancen las herramientas.
>
> Para más información, consulte la entrada [Changes to project.json](https://blogs.msdn.microsoft.com/dotnet/2016/05/23/changes-to-project-json/) (Cambios en project.json) del blog .NET y el tema [Using MSBuild to build .NET Core projects](../tutorials/target-dotnetcore-with-msbuild.md) (Uso de MSBuild para compilar proyectos de .NET Core).

## <a name="overview"></a>Información general

```
{
    "name": String,
    "version": String,
    "description": String,
    "copyright": String,
    "title": String,
    "entryPoint": String,
    "testRunner": String,
    "authors": String[],
    "language": String,
    "embedInteropTypes": Boolean,
    "preprocess": String or String[],
    "shared": String or String[],
    "dependencies": Object {
        version: String,
        type: String,
        target: String,
        include: String,
        exclude: String,
        suppressParent: String
    },
    "tools": Object,
    "scripts": Object,
    "buildOptions": Object {
        "define": String[],
        "nowarn": String[],
        "additionalArguments": String[],
        "warningsAsErrors": Boolean,
        "allowUnsafe": Boolean,
        "emitEntryPoint": Boolean,
        "optimize": Boolean,
        "platform": String,
        "languageVersion": String,
        "keyFile": String,
        "delaySign": Boolean,
        "publicSign": Boolean,
        "debugType": String,
        "xmlDoc": Boolean,
        "preserveCompilationContext": Boolean,
        "outputName": String,
        "compilerName": String,
        "compile": Object {
            "include": String or String[],
            "exclude": String or String[],
            "includeFiles": String or String[],
            "excludeFiles": String or String[],
            "builtIns": Object,
            "mappings": Object
        },
        "embed": Object {
            "include": String or String[],
            "exclude": String or String[],
            "includeFiles": String or String[],
            "excludeFiles": String or String[],
            "builtIns": Object,
            "mappings": Object
        },
        "copyToOutput": Object {
            "include": String or String[],
            "exclude": String or String[],
            "includeFiles": String or String[],
            "excludeFiles": String or String[],
            "builtIns": Object,
            "mappings": Object
        }
    },
    "publishOptions": Object {
        "include": String or String[],
        "exclude": String or String[],
        "includeFiles": String or String[],
        "excludeFiles": String or String[],
        "builtIns": Object,
        "mappings": Object
    },
    "runtimeOptions": Object {
        "configProperties": Object {
            "System.GC.Server": Boolean,
            "System.GC.Concurrent": Boolean,
            "System.GC.RetainVM": Boolean,
            "System.Threading.ThreadPool.MinThreads": Integer,
            "System.Threading.ThreadPool.MaxThreads": Integer
        },
        "framework": Object {
            "name": String,
            "version": String,
        },
        "applyPatches": Boolean
    },
    "packOptions": Object {
        "summary": String,
        "tags": String[],
        "owners": String[],
        "releaseNotes": String,
        "iconUrl": String,
        "projectUrl": String,
        "licenseUrl": String,
        "requireLicenseAcceptance": Boolean,
        "repository": Object {
            "type": String,
            "url": String
        },
        "files": Object {
            "include": String or String[],
            "exclude": String or String[],
            "includeFiles": String or String[],
            "excludeFiles": String or String[],
            "builtIns": Object,
            "mappings": Object
        }
    },
    "analyzerOptions": Object {
        "languageId": String
    },
    "configurations": Object,
    "frameworks": Object {
        "dependencies": Object {
            version: String,
            type: String,
            target: String,
            include: String,
            exclude: String,
            suppressParent: String
        },        
        "frameworkAssemblies": Object,
        "wrappedProject": String,
        "bin": Object {
            assembly: String
        }
    },
    "runtimes": Object,
    "userSecretsId": String
}
```

## <a name="name"></a>name
Tipo: string

El nombre del proyecto; se usa como nombre del ensamblado y, además, como el nombre del paquete. Si esta propiedad no se especifica, se usa el nombre de la carpeta de nivel superior.

Por ejemplo:

```json
{
    "name": "MyLibrary"
}
```

## <a name="version"></a>version
Tipo: string

La versión [Semver](http://semver.org/spec/v1.0.0.html) del proyecto; también se usa para el paquete NuGet.

Por ejemplo:

```json
{
    "version": "1.0.0-*"
}
```

## <a name="description"></a>Descripción
Tipo: string

Una descripción más larga del proyecto. Se usa en las propiedades de ensamblado.

Por ejemplo:

```json
{
    "description": "This is my library and it's really great!"
}
```

## <a name="copyright"></a>copyright
Tipo: string

La información de copyright del proyecto. Se usa en las propiedades de ensamblado.

Por ejemplo:

```json
{
    "copyright": "Fabrikam 2016"
}
```

## <a name="title"></a>título
Tipo: string

El nombre descriptivo del proyecto; puede incluir espacios y caracteres especiales que no se permiten cuando se usa la propiedad `name`. Se usa en las propiedades de ensamblado.

Por ejemplo:

```json
{
    "title": "My Library"
}
```

## <a name="entrypoint"></a>entryPoint
Tipo: string

El método de punto de entrada del proyecto. `Main` es el valor predeterminado.

Por ejemplo:

```json
{
    "entryPoint": "ADifferentMethod"
}
```
    
## <a name="testrunner"></a>testRunner
Tipo: string

El nombre del ejecutor de pruebas, como [NUnit](http://nunit.org/) o [xUnit](http://xunit.github.io/), que se usa con este proyecto. Establecer este valor también marca el proyecto como un proyecto de prueba.

Por ejemplo:

```json
{
    "testRunner": "NUnit"
}
```

## <a name="authors"></a>authors
Tipo: String[]

Una matriz de cadenas con los nombres de los autores del proyecto.

Por ejemplo:

```json
{
    "authors": ["Anne", "Bob"]
}
```

## <a name="language"></a>lenguaje
Tipo: string

El idioma (humano) del proyecto. Corresponde al argumento "neutral-language" del compilador.

Por ejemplo:

```json
{
    "language": "en-US"
}
```

## <a name="embedinteroptypes"></a>embedInteropTypes
Tipo: booleano

`true` para insertar tipos de interoperabilidad COM en el ensamblado; de lo contrario, `false`. 

Por ejemplo:

```json
{
    "embedInteropTypes": true
}
```

## <a name="preprocess"></a>preprocess
Tipo: String o String[] con un patrón comodín

Especifica los archivos que se incluyen en el preprocesamiento.

Por ejemplo:

```json
{
    "preprocess": "compiler/preprocess/**/*.cs"
}
```

## <a name="shared"></a>compartidos
Tipo: String o String[] con un patrón comodín

Especifica los archivos que se comparten; se usa para la exportación de la biblioteca.

Por ejemplo:

```json
{
    "shared": "shared/**/*.cs"
}
```

## <a name="dependencies"></a>dependencias
Tipo: objeto

Un objeto que define las dependencias de paquete del proyecto; cada clave de este objeto es el nombre de un paquete y cada valor contiene información sobre la versión.
Para más información, consulte el artículo sobre la [resolución de dependencia](https://docs.microsoft.com/nuget/consume-packages/dependency-resolution#dependency-resolution-in-nuget-3x) que se encuentra en el sitio de documentación de NuGet.

Por ejemplo:

```json
    "dependencies": {
        "System.Reflection.Metadata": "1.3.0",
        "Microsoft.Extensions.JsonParser.Sources": {
          "type": "build",
          "version": "1.0.0-rc2-20221"
        },
        "Microsoft.Extensions.HashCodeCombiner.Sources": {
          "type": "build",
          "version": "1.1.0-alpha1-21456"
        },
        "Microsoft.Extensions.DependencyModel": "1.0.0-*"
    }
```

### <a name="version"></a>version
Tipo: string

Especifica la versión o el intervalo de versiones de la dependencia. Use el comodín \* para especificar una [versión de dependencia flotante](https://docs.microsoft.com/nuget/consume-packages/dependency-resolution#floating-versions).

Por ejemplo:

```json
"dependencies": { 
    "Newtonsoft.Json": { 
        "version": "9.0.1" 
    }
}
```

### <a name="type"></a>tipo
Tipo: string

Especifica el tipo de la dependencia. Puede ser uno de los valores siguientes: `default`, `build` o `platform`. El valor predeterminado es `default`.

`build` se conoce como una dependencia de desarrollo y solo se usa para el tiempo de compilación. Esto significa que el paquete no se publicará ni agregará como dependencia al archivo `.nupkg` de salida. Tiene el mismo efecto que establecer [supressParent](#supressparent) en `all`.

`platform` hace referencia al SDK compartido. Para más información, consulte la sección "Deploying a framework-dependent deployment with third-party dependencies" (Implementación dependiente de la estructura con dependencias de terceros) del tema [.NET Core Application Deployment](../deploying/index.md) (Implementación de aplicaciones .NET Core).

Por ejemplo:

```json
 "dependencies": {
   "Microsoft.NETCore.App": {
     "type": "platform",
     "version": "1.0.0"
   }
 }
```

### <a name="target"></a>target
Tipo: string

Restringe la dependencia para que solo coincida con un `project` o un `package`.

### <a name="include"></a>include
Tipo: string

Incluye partes de paquetes de dependencias. Puede usar una o varias de las marcas siguientes: `all`, `runtime`, `compile`, `build`, `contentFiles`, `native`, `analyzers` o `none`.
Las marcas múltiples se definen con una lista delimitada por comas.
Para más información, consulte la especificación [Managing dependency package assets](https://github.com/NuGet/Home/wiki/%5BSpec%5D-Managing-dependency-package-assets) (Administración de recursos de paquetes de dependencias) en el repositorio de NuGet.

Por ejemplo:

```json
{
  "dependencies": {
    "packageA": {
      "version": "1.0.0",
      "include": "runtime"
    }
  }
}
```

### <a name="exclude"></a>exclude
Tipo: string

Excluye partes de paquetes de dependencias. Puede ser una o varias de las marcas siguientes: `all`, `runtime`, `compile`, `build`, `contentFiles`, `native`, `analyzers` o `none`.
Las marcas múltiples se definen con una lista delimitada por comas.
Para más información, consulte la especificación [Managing dependency package assets](https://github.com/NuGet/Home/wiki/%5BSpec%5D-Managing-dependency-package-assets) (Administración de recursos de paquetes de dependencias) en el repositorio de NuGet.

Por ejemplo:

```json
{
  "dependencies": {
    "packageA": {
      "version": "1.0.0",
      "exclude": "contentFiles"
    }
  }
}
```

### <a name="supressparent"></a>supressParent
Tipo: string

Define exclusiones adicionales para los consumidores del proyecto. Puede ser una de las marcas siguientes: `all`, `runtime`, `compile`, `build`, `contentFiles`, `native`, `analyzers` o `none`.
Para más información, consulte la especificación [Managing dependency package assets](https://github.com/NuGet/Home/wiki/%5BSpec%5D-Managing-dependency-package-assets) (Administración de recursos de paquetes de dependencias) en el repositorio de NuGet.

```json
{
  "dependencies": {
    "packageA": {
      "version": "1.0.0",
      "suppressParent": "compile"
    }
  }
}
```

## <a name="tools"></a>herramientas
Tipo: objeto

Objeto que define las dependencias de paquete que se usan como herramientas en el proyecto actual, no como referencias. Los paquetes que se definen aquí están disponibles en scripts que se ejecutan durante el proceso de compilación, pero no es posible tener acceso a ellos en el código mismo del proyecto. Por ejemplo, las herramientas pueden incluir generadores de código o herramientas posteriores a la compilación que realizan tareas relacionadas con el empaquetado.

Por ejemplo:

```json
{
    "tools": {
    "MyObfuscator": "1.2.4"
    }
}
```

## <a name="scripts"></a>scripts
Tipo: objeto

Objeto que define los scripts que se ejecutan durante el proceso de compilación. Cada clave de este objeto identifica en qué parte de la compilación se ejecuta el script. Cada valor es una cadena con el script que se ejecutará o una matriz de cadenas que contiene los scripts que se ejecutarán en orden.
Los eventos admitidos son:
* precompilación
* poscompilación
* prepublicación
* pospublicación

Por ejemplo:

```json
{
    "scripts": {
        "precompile": "generateCode.cmd",
        "postcompile": [ "obfuscate.cmd", "removeTempFiles.cmd" ]
    }
}
```

## <a name="buildoptions"></a>buildOptions
Tipo: objeto

Objeto cuyas propiedades controlan diversos aspectos de la compilación. Las propiedades válidas se muestran a continuación: También se puede especificar por plataforma de destino, tal como se describe en la [sección frameworks](#frameworks).

Por ejemplo:

```json
    "buildOptions": {
      "allowUnsafe": true,
      "emitEntryPoint": true
    }
```

### <a name="define"></a>define
Tipo: String[]

Lista de definiciones, como "DEBUG" o "TRACE", que se pueden usar en compilación condicional en el código.

Por ejemplo:

```json
{
    "buildOptions": {
        "define": ["TEST", "OTHERCONDITION"]
    }
}
```

### <a name="nowarn"></a>nowarn
Tipo: String[]

Lista de las advertencias que se van a ignorar.

Por ejemplo:

```json
{
    "buildOptions": {
        "nowarn": ["CS0168", "CS0219"]
    }
}
```

Con esto se omiten las advertencias `The variable 'var' is declared but never used` y `The variable 'var' is assigned but its value is never used`.

### <a name="additionalarguments"></a>additionalArguments
Tipo: String[]

Lista de argumentos adicionales que se pasarán al compilador.

Por ejemplo:

```json
{
    "buildOptions": {
        "additionalArguments": ["/parallel", "/nostdlib"]
    }
}
```

### <a name="warningsaserrors"></a>warningsAsErrors
Tipo: booleano

`true` para tratar las advertencias como errores; de lo contrario, `false`. De manera predeterminada, es `false`.

Por ejemplo:

```json
{
    "buildOptions": {
        "warningsAsErrors": true
    }
}
```

### <a name="allowunsafe"></a>allowUnsafe
Tipo: booleano

`true` para permitir el uso de código no seguro en este proyecto; de lo contrario, `false`. De manera predeterminada, es `false`.

Por ejemplo:

```json
{
    "buildOptions": {
        "allowUnsafe": true
    }
}
```

### <a name="emitentrypoint"></a>emitEntryPoint
Tipo: booleano

`true` para crear un archivo ejecutable; `false` para generar una biblioteca. De manera predeterminada, es `false`.

Por ejemplo:

```json
{
    "buildOptions": {
        "emitEntryPoint": true
    }
}
```

### <a name="optimize"></a>optimize
Tipo: booleano

`true` para permitir que el compilador optimice el código de este proyecto; de lo contrario,`false` . De manera predeterminada, es `false`.

Por ejemplo:

```json
{
    "buildOptions": {
        "optimize": true
    }
}
```

### <a name="platform"></a>platform
Tipo: string

Nombre de la plataforma de destino, como AnyCpu, x86 o x64.

Por ejemplo:

```json
{
    "buildOptions": {
        "platform": "x64"
    }
}
```

### <a name="languageversion"></a>languageVersion
Tipo: string

La versión del lenguaje que usa el compilador: ISO-1, ISO-2, 3, 4, 5, 6 o Default.

Por ejemplo:

```json
{
    "buildOptions": {
        "languageVersion": "5"
    }
}
```

### <a name="keyfile"></a>keyFile
Tipo: string

La ruta de acceso del archivo de clave que se usa para firmar este ensamblado.

Por ejemplo:

```json
{
    "buildOptions": {
        "keyFile": "../keyfile.snk"
    }
}
```

### <a name="delaysign"></a>delaySign
Tipo: booleano

`true` para retrasar la firma; de lo contrario, `false`. De manera predeterminada, es `false`.

Por ejemplo:

```json
{
    "buildOptions": {
        "delaySign": true
    }
}
```

### <a name="publicsign"></a>publicSign
Tipo: booleano

`true` para permitir la firma del ensamblado resultante; de lo contrario, `false`. De manera predeterminada, es `false`.

Por ejemplo:

```json
{
    "buildOptions": {
        "publicSign": true
    }
}
```

### <a name="debugtype"></a>debugType
Tipo: string

Indica el tipo de archivo de símbolo (archivo PDB) que se generará. Las opciones son: "portátil" (para proyectos .NET Core) o "completo" (los archivos PDB tradicionales solo para Windows).

Por ejemplo:

```json
{
    "buildOptions": {
        "debugType": "portable"
    }
}
```

### <a name="xmldoc"></a>xmlDoc
Tipo: booleano

`true` para generar documentación XML a partir de comentarios insertados con tres barras diagonales en el código fuente; de lo contrario, `false`. De manera predeterminada, es `false`.

Por ejemplo:

```json
{
    "buildOptions": {
        "xmlDoc": true
    }
}
```

### <a name="preservecompilationcontext"></a>preserveCompilationContext
Tipo: booleano

`true` para conservar los ensamblados de referencia y otros datos de contexto para permitir la compilación en el entorno de ejecución; de lo contrario, `false`. De manera predeterminada, es `false`.

Por ejemplo:

```json
{
    "buildOptions": {
        "preserveCompilationContext": true
    }
}
```

### <a name="outputname"></a>outputName
Tipo: string

Cambie el nombre del archivo de salida. 

Por ejemplo:

```json
{
    "buildOptions": {
        "outputName": "MyApp"
    }
}
```

### <a name="compilername"></a>compilerName
Tipo: string

El nombre del compilador que se usa en este proyecto. `csc` es el valor predeterminado. Actualmente se admiten `csc` (el compilador de C#) o `fsc` (el compilador de F#).
 
Por ejemplo:

```json
{
    "compilerName": "fsc"
}
```
    
### <a name="compile"></a>compile
Tipo: objeto

Objeto que contiene propiedades para la configuración de la compilación

#### <a name="include"></a>include
Tipo: String o String[] con un patrón comodín

Especifica los archivos que se incluirán en la compilación. Los patrones están en la raíz de la carpeta del proyecto. El valor predeterminado es none.

Por ejemplo:

```json
{
    "include":["wwwroot", "Views"]
}
```

#### <a name="exclude"></a>exclude
Tipo: String o String[] con un patrón comodín

Especifica los archivos que se excluirán de la compilación. Los patrones de exclusión tienen mayor prioridad que los patrones de inclusión, por lo que se excluirá un archivo que se encuentre en ambos. Los patrones están en la raíz de la carpeta del proyecto. El valor predeterminado es none.

Por ejemplo:

```json
{
    "exclude": ["bin/**", "obj/**"]
}
```

#### <a name="includefiles"></a>includeFiles

Tipo: String o String[] con un patrón comodín

Una lista de las rutas de acceso a archivos que se van a incluir. Las rutas de acceso están en la raíz de la carpeta del proyecto. Esta lista tiene una prioridad mayor que los patrones comodines de inclusión y exclusión; por lo tanto, si un archivo aparece aquí y en el patrón comodín de exclusión, se incluirá de todos modos. El valor predeterminado es none.

Por ejemplo:

```json
{
    "includeFiles": []
}
```

#### <a name="excludefiles"></a>excludeFiles

Tipo: String o String[] con un patrón comodín

Una lista de las rutas de acceso a archivos que se van a excluir. Las rutas de acceso están en la raíz de la carpeta del proyecto. Esta lista tiene una prioridad mayor que los patrones comodín y las rutas de acceso de inclusión; por lo tanto, si un archivo aparece en todos ellos, se excluirá. El valor predeterminado es none.

Por ejemplo:

```json
{
    "excludeFiles":[],
}
```

#### <a name="builtins"></a>builtIns

Tipo: objeto

Los valores predeterminados que proporciona el sistema. Puede tener los patrones comodín `include` y `exclude`, los que se combinan con los valores correspondientes de las propiedades `include` y `exclude`.

Por ejemplo:

```json
{
    "builtIns":{}
}
```

#### <a name="mappings"></a>asignaciones
Tipo: objeto

Las claves del objeto representan las rutas de destino en el diseño de salida.

Los valores son una cadena o un objeto que representa la ruta de acceso de origen de los archivos que se van a incluir.  La representación del objeto puede tener sus propias secciones `include`, `exclude`, `includeFiles` y `excludeFiles`.

Ejemplo de cadena:

```json
{
    "mappings": {
        "dest/path": "./src/path"
    }
}
```

Ejemplo de objeto:

```json
{
    "mappings": {
        "dest/path":{
            "include":"./src/path"
        }
    }
}
```

### <a name="embed"></a>embed
Tipo: objeto

Objeto que contiene propiedades para la configuración de la compilación

#### <a name="include"></a>include
Tipo: String o String[] con un patrón comodín

```json
{
    "include":["wwwroot", "Views"]
}
```

#### <a name="exclude"></a>exclude
Tipo: String o String[] con un patrón comodín

Especifica los archivos que se excluirán de la compilación.

Por ejemplo:

```json
{
    "exclude": ["bin/**", "obj/**"]
}
```

#### <a name="includefiles"></a>includeFiles

Tipo: String o String[] con un patrón comodín

```json
{
    "includeFiles":[],
}
```

#### <a name="excludefiles"></a>excludeFiles

Tipo: String o String[] con un patrón comodín

```json
{
    "excludeFiles":[],
}
```

#### <a name="builtins"></a>builtIns
Tipo: objeto

```json
{
    "builtIns":{}
}
```

#### <a name="mappings"></a>asignaciones
Tipo: objeto

Las claves del objeto representan las rutas de destino en el diseño de salida.

Los valores son una cadena o un objeto que representa la ruta de acceso de origen de los archivos que se van a incluir.  La representación del objeto puede tener sus propias secciones `include`, `exclude`, `includeFiles` y `excludeFiles`.

Ejemplo de cadena:

```json
{
    "mappings": {
        "dest/path": "./src/path"
    }
}
```

Ejemplo de objeto:

```json
{
    "mappings": {
        "dest/path":{
            "include":"./src/path"
        }
    }
}
```

### <a name="copytooutput"></a>copyToOutput
Tipo: objeto

Objeto que contiene propiedades para la configuración de la compilación

#### <a name="include"></a>include
Tipo: String o String[] con un patrón comodín

```json
{
    "include":["wwwroot", "Views"]
}
```

#### <a name="exclude"></a>exclude
Tipo: String o String[] con un patrón comodín

Especifica los archivos que se excluirán de la compilación.

Por ejemplo:

```json
{
    "exclude": ["bin/**", "obj/**"]
}
```

#### <a name="includefiles"></a>includeFiles

Tipo: String o String[] con un patrón comodín

```json
{
    "includeFiles":[],
}
```

#### <a name="excludefiles"></a>excludeFiles

Tipo: String o String[] con un patrón comodín

```json
{
    "excludeFiles":[],
}
```

#### <a name="builtins"></a>builtIns
Tipo: objeto

```json
{
    "builtIns":{}
}
```

#### <a name="mappings"></a>asignaciones
Tipo: objeto

Las claves del objeto representan las rutas de destino en el diseño de salida.

Los valores son una cadena o un objeto que representa la ruta de acceso de origen de los archivos que se van a incluir.  La representación del objeto puede tener sus propias secciones `include`, `exclude`, `includeFiles` y `excludeFiles`.

Ejemplo de cadena:

```json
{
    "mappings": {
        "dest/path": "./src/path"
    }
}
```

Ejemplo de objeto:

```json
{
    "mappings": {
        "dest/path":{
            "include":"./src/path"
        }
    }
}
```

## <a name="publishoptions"></a>publishOptions
Tipo: objeto

Objeto que contiene propiedades para la configuración de la compilación

### <a name="include"></a>include
Tipo: String o String[] con un patrón comodín

```json
{
    "include":["wwwroot", "Views"]
}
```

### <a name="exclude"></a>exclude
Tipo: String o String[] con un patrón comodín

Especifica los archivos que se excluirán de la compilación.

Por ejemplo:

```json
{
    "exclude": ["bin/**", "obj/**"]
}
```

### <a name="includefiles"></a>includeFiles

Tipo: String o String[] con un patrón comodín

```json
{
    "includeFiles":[],
}
```

### <a name="excludefiles"></a>excludeFiles

Tipo: String o String[] con un patrón comodín

```json
{
    "excludeFiles":[],
}
```

### <a name="builtins"></a>builtIns
Tipo: objeto

```json
{
    "builtIns":{}
}
```

### <a name="mappings"></a>asignaciones
Tipo: objeto

Las claves del objeto representan las rutas de destino en el diseño de salida.

Los valores son una cadena o un objeto que representa la ruta de acceso de origen de los archivos que se van a incluir.  La representación del objeto puede tener sus propias secciones `include`, `exclude`, `includeFiles` y `excludeFiles`.

Ejemplo de cadena:

```json
{
    "mappings": {
        "dest/file": "./src/file",
        "dest/folder/": "./src/folder/**/*"
    }
}
```

Ejemplo de objeto:

```json
{
    "mappings": {
        "dest/file":{
            "include":"./src/file"
        },
        "dest/folder/":{
            "include":"./src/folder/**/*"
        }
    }
}
```

## <a name="runtimeoptions"></a>runtimeOptions
Tipo: objeto

Especifica los parámetros que se proporcionarán al entorno de ejecución durante la inicialización.

### <a name="configproperties"></a>configProperties
Tipo: objeto

Incluye las propiedades de configuración para configurar el entorno de ejecución y el marco de trabajo.

#### <a name="systemgcserver"></a>System.GC.Server
Tipo: booleano

`true` para habilitar la recolección de elementos no utilizados del servidor; de lo contrario, `false`. De manera predeterminada, es `false`.

Por ejemplo:

```json
{
    "runtimeOptions": {
        "configProperties": {
            "System.GC.Server": true
        }
    }
}
```

#### <a name="systemgcconcurrent"></a>System.GC.Concurrent
Tipo: booleano

`true` para habilitar la recolección de elementos no utilizados simultánea; de lo contrario, `false`. De manera predeterminada, es `false`.

Por ejemplo:

```json
{
    "runtimeOptions": {
        "configProperties": {
            "System.GC.Concurrent": true
        }
    }
}
```

#### <a name="systemgcretainvm"></a>System.GC.RetainVM
Tipo: booleano

`true` para colocar los segmentos que se deben eliminar en una lista de modo de espera para usarlos en el futuro en lugar de devolverlos al sistema operativo (SO); de lo contrario, `false`.
De manera predeterminada, es `false`.

Por ejemplo:

```json
{
    "runtimeOptions": {
        "configProperties": {
            "System.GC.RetainVM": true
        }
    }
}
```

#### <a name="systemthreadingthreadpoolminthreads"></a>System.Threading.ThreadPool.MinThreads
Tipo: entero

Reemplaza la cantidad mínima de subprocesos para el grupo de trabajo ThreadPool.

```json
{
    "runtimeOptions": {
        "configProperties": {
            "System.Threading.ThreadPool.MinThreads": 4
        }
    }
}
```

#### <a name="systemthreadingthreadpoolmaxthreads"></a>System.Threading.ThreadPool.MaxThreads
Tipo: entero

Reemplaza la cantidad máxima de subprocesos para el grupo de trabajo ThreadPool.

```json
{
    "runtimeOptions": {
        "configProperties": {
            "System.Threading.ThreadPool.MaxThreads": 25
        }
    }
}
```

### <a name="framework"></a>marco de trabajo
Tipo: objeto

Contiene propiedades del marco de trabajo compartido para usar cuando se active la aplicación. La presencia de esta sección indica que la aplicación es una aplicación portátil diseñada para usar un marco de trabajo redistribuible compartida.

#### <a name="name"></a>name
Tipo: string

El nombre del marco de trabajo compartido.

```json
{
    "runtimeOptions": {
        "framework": {
            "name": "Microsoft.DotNetCore"
        }
    }
}
```

#### <a name="version"></a>version
Tipo: string

La versión del marco de trabajo compartido.

```json
{
    "runtimeOptions": {
        "framework": {
            "version": "1.0.1"
        }
    }
}
```

### <a name="applypatches"></a>applyPatches
Tipo: booleano

`true` para usar el marco de trabajo desde la misma versión o una versión superior que solo difiere en el campo de revisión `SemVer`. `false` para que el host solo use la versión de marco de trabajo exacta. De manera predeterminada, es `true`.

```json
{
    "runtimeOptions": {
        "applyPatches": false
    }
}
```

## <a name="packoptions"></a>packOptions
Tipo: objeto

Define las opciones correspondientes con el empaquetado de la salida del proyecto en un paquete NuGet.

### <a name="summary"></a>resumen
Tipo: string

Una descripción breve del proyecto.

Por ejemplo:

```json
{
    "packOptions": {
        "summary": "This is my library."
    }
}
```

### <a name="tags"></a>etiquetas
Tipo: String[]

Una matriz de cadenas con marcas para el proyecto; se usa para realizar búsquedas en NuGet.

Por ejemplo:

```json
{
    "packOptions": {
        "tags": ["hyperscale", "cats"]
    }
}
```

### <a name="owners"></a>owners
Tipo: String[]

Una matriz de cadenas con los nombres de los propietarios del proyecto.

Por ejemplo:

```json
{
    "packOptions": {
        "owners": ["Fabrikam", "Microsoft"]
    }
}
```

### <a name="releasenotes"></a>releaseNotes
Tipo: string

Notas de la versión para el proyecto.

Por ejemplo:

```json
{
    "packOptions": {
        "releaseNotes": "Initial version, implemented flimflams."
    }
}
```

### <a name="iconurl"></a>iconUrl
Tipo: string

La dirección URL de un icono que se usará en varios lugares, como el explorador de paquetes.

Por ejemplo:

```json
{
    "packOptions": {
        "iconUrl": "http://www.mylibrary.gov/favicon.ico"
    }
}
```

### <a name="projecturl"></a>projectUrl
Tipo: string

La dirección URL de la página principal del proyecto.

Por ejemplo:

```json
{
    "packOptions": {
        "projectUrl": "http://www.mylibrary.gov"
    }
}
```

### <a name="licenseurl"></a>licenseUrl
Tipo: string

La dirección URL de la licencia que el proyecto usa.

Por ejemplo:

```json
{
    "packOptions": {
        "licenseUrl": "http://www.mylibrary.gov/licence"
    }
}
```

### <a name="requirelicenseacceptance"></a>requireLicenseAcceptance
Tipo: booleano

`true` para hacer que la solicitud acepte la licencia del paquete cuando se muestre la instalación del paquete; de lo contrario, `false`. Solo se usa para los paquetes NuGet y se ignora en otros usos. De manera predeterminada, es `false`.

Por ejemplo:

```json
{
    "packOptions": {
        "requireLicenseAcceptance": true
    }
}
```
   
### <a name="repository"></a>repositorio
Tipo: objeto

Incluye información sobre el repositorio donde está almacenado el proyecto.

#### <a name="type"></a>tipo
Tipo: string

Tipo del repositorio. El valor predeterminado es "git".

Por ejemplo:

```json
{
    "packOptions": {
        "repository": {
            "type": "git"
        }
    }
}
```

#### <a name="url"></a>url
Tipo: string

Dirección URL del repositorio donde está almacenado el proyecto.

Por ejemplo:

```json
{
    "packOptions": {
        "repository": {
            "url": "http://github.com/dotnet/corefx"
        }
    }
}
```

### <a name="files"></a>archivos
Tipo: objeto

#### <a name="include"></a>include
Tipo: String o String[] con un patrón comodín

```json
{
    "include":["wwwroot", "Views"]
}
```

#### <a name="exclude"></a>exclude
Tipo: String o String[] con un patrón comodín

Especifica los archivos que se excluirán de la compilación.

Por ejemplo:

```json
{
    "exclude": ["bin/**", "obj/**"]
}
```

#### <a name="includefiles"></a>includeFiles

Tipo: String o String[] con un patrón comodín

```json
{
    "includeFiles":[]
}
```

#### <a name="excludefiles"></a>excludeFiles

Tipo: String o String[] con un patrón comodín

```json
{
    "excludeFiles":[]
}
```

#### <a name="builtins"></a>builtIns
Tipo: objeto

```json
{
    "builtIns":{}
}
```

#### <a name="mappings"></a>asignaciones
Tipo: objeto

Las claves del objeto representan las rutas de destino en el diseño de salida.

Los valores son una cadena o un objeto que representa la ruta de acceso de origen de los archivos que se van a incluir.  La representación del objeto puede tener sus propias secciones `include`, `exclude`, `includeFiles` y `excludeFiles`. 

Ejemplo de cadena:

```json
{
    "mappings": {
        "dest/path": "./src/path"
    }
}
```

Ejemplo de objeto:

```json
{
    "mappings": {
        "dest/path":{
            "include":"./src/path"
        }
    }
}
```

## <a name="analyzeroptions"></a>analyzerOptions
Tipo: objeto

Objeto con propiedades que los analizadores de código usan.

Por ejemplo:

```json
{
    "analyzerOptions": { }
}
```

### <a name="languageid"></a>languageId
Tipo: string

El identificador del lenguaje que se analizará. "cs" representa C#, "vb" representa Visual Basic y "fs" representa F#.

Por ejemplo:

```json
"analyzerOptions": {
    "languageId": "vb"
}
```

## <a name="configurations"></a>configuraciones
Tipo: objeto

Objeto cuyas propiedades definen distintas configuraciones para este proyecto, como las configuraciones para depuración y lanzamiento. Cada valor es un objeto que puede incluir un objeto `buildOptions` con opciones específicas para dicha configuración.

Por ejemplo:

```json
"configurations": {
    "Release": {
        "buildOptions": {
            "allowUnsafe": false
        }
    }
}
```

## <a name="frameworks"></a>frameworks
Tipo: objeto

Especifica los marcos de trabajo que admite este proyecto: .NET Framework o Plataforma universal de Windows (UWP). Debe ser un moniker de plataforma de destino (TFM) válido. Cada valor es un objeto que puede contener información específica relacionada con este marco de trabajo, como `buildOptions`, `analyzerOptions`, `dependencies`, además de las propiedades que se muestran en las siguientes secciones.

Por ejemplo:

```json
"frameworks": {
    "netcoreapp1.0": {
        "buildOptions": {
            "define": ["FOO", "BIZ"]
        }
    }
}
```

### <a name="dependencies"></a>dependencias
Tipo: objeto

Las dependencias específicas para este marco de trabajo. Resulta útil en escenarios en los que no puede simplemente especificar una dependencia a nivel de paquete en todos los destinos. Las razones para esto pueden incluir un destino que no tiene la compatibilidad integrada que tienen otros destinos, o bien que tiene una versión distinta de una dependencia que la que tienen los otros destinos. Para ver una lista de las otras propiedades de este nodo, consulte la sección sobre [dependencias](#dependencies) que apareció anteriormente.

Por ejemplo:

```json
    "frameworks": {
        "netstandard1.5": {
        "dependencies": {
            "Microsoft.Extensions.JsonParser.Sources": "1.0.0-rc2-20221"
        }
    }
}
```

### <a name="frameworkassemblies"></a>frameworkAssemblies
Tipo: objeto

Similar a las dependencias, pero incluye referencias a los ensamblados en la GAC que no son paquetes NuGet. También puede especificar la versión que usa, además del tipo de dependencia. Se usa cuando los destinos son .NET Framework y Biblioteca de clases portable (PCL). Solo puede compilar un proyecto con esta especificación en Windows.

Por ejemplo:

```json
"frameworks": {
    "net451": {
        "frameworkAssemblies": {
            "System.Runtime": {
                "type": "build",
                "version": "4.0.0"
            }
        }
    }
}
```

### <a name="wrappedproject"></a>wrappedProject
Tipo: string

Especifica la ubicación del proyecto de dependencia. 

Por ejemplo:

```json
"frameworks": {
    "net451": {
        "wrappedProject": "MyProject.csproj"
    }
}
```

### <a name="bin"></a>bin
Tipo: objeto

Se usa para encapsular un archivo DLL. Puede hacer referencia a un paquete que contiene este DLL y también generarlo. 

Contiene solo una propiedad de cadena, `assembly`, cuyo valor es la ruta de acceso al ensamblado..   

Por ejemplo:

```json
"frameworks": {
    "netcoreapp1.0": {
        "bin": {
            "assembly": "c:/otherProject/otherdll.dll"
        }
    }
}
```

## <a name="runtimes"></a>runtimes
Tipo: objeto

Lista de los [identificadores del entorno de ejecución (RID)](../rid-catalog.md) que admite el proyecto (se usa cuando se publican [implementaciones autocontenidas](../deploying/index.md#self-contained-deployments-scd)).

Por ejemplo:

```json
"runtimes": {
    "win7-x64": {},
    "win8-x64": {},
    "win81-x64": {},
    "win10-x64": {},
    "osx.10.11-x64": {},
    "ubuntu.16.04-x64": {}
}
```

## <a name="usersecretsid"></a>userSecretsId
Tipo: string

Especifica un identificador secreto de usuario que se usará en tiempo de desarrollo. Para más información, consulte [Safe storage of app secrets during development](https://docs.microsoft.com/aspnet/core/security/app-secrets) (Almacenamiento seguro de secretos de aplicación durante el desarrollo).

Por ejemplo:

```json
{
    "userSecretsId": "aspnet-WebApp1-c23d27a4-eb88-4b18-9b77-2a93f3b15119"
}
```



<!--HONumber=Feb17_HO3-->


