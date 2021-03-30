---
description: Opciones avanzadas del compilador de C#. Estas opciones se usan en escenarios avanzados.
title: 'Opciones del compilador de C#: escenarios avanzados'
ms.date: 03/12/2021
f1_keywords:
- cs.build.options
helpviewer_keywords:
- BaseAddress compiler option [C#]
- ChecksumAlgorithm compiler option [C#]
- CodePage compiler option [C#]
- Utf8Output compiler option [C#]
- MainEntryPoint compiler option [C#]
- GenerateFullPaths compiler option [C#]
- FileAlignment compiler option [C#]
- PathMap compiler option [C#]
- PdbFile compiler option [C#]
- ErrorEndLocation compiler option [C#]
- NoStandardLib compiler option [C#]
- PreferredUILang compiler option [C#]
- SubsystemVersion compiler option [C#]
- AdditionalLibPaths compiler option [C#]
- ApplicationConfiguration compiler option [C#]
- ModuleAssemblyName compiler option [C#]
ms.openlocfilehash: 5c51a4dd950a33fb51c338dbd1d86bb5b03eb694
ms.sourcegitcommit: e16315d9f1ff355f55ff8ab84a28915be0a8e42b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "105111041"
---
# <a name="advanced-c-compiler-options"></a>Opciones avanzadas del compilador de C#

Las opciones siguientes admiten escenarios avanzados. La nueva sintaxis de MSBuild se muestra en **negrita**. La sintaxis de `csc.exe` anterior se muestra en `code style`.

- **MainEntryPoint**, **StartupObject** / `-main`: se especifica el tipo que contiene el punto de entrada.
- **PdbFile** / `-pdb`: se especifica el nombre del archivo de información de depuración.
- **PathMap** / `-pathmap`: se especifica una asignación para los nombres de rutas de acceso de origen generados por el compilador.
- **ApplicationConfiguration** / `-appconfig`: se especifica un archivo de configuración de la aplicación que contenga la configuración de enlace de ensamblados.
- **AdditionalLibPaths** / `-lib`: se especifican los directorios adicionales en los que buscar referencias.
- **GenerateFullPaths** / `-fullpath`: el compilador genera rutas de acceso completas.
- **PreferredUILang** / `-preferreduilang`: se especifica el nombre del lenguaje de salida preferido.
- **BaseAddress** / `-baseaddress`: se especifica la dirección base de la biblioteca que se va a compilar.
- **ChecksumAlgorithm** / `-checksumalgorithm`: se especifica el algoritmo para calcular la suma de comprobación del archivo de origen almacenada en el archivo PDB.
- **CodePage** / `-codepage`: se especifica la página de códigos que se va a usar al abrir los archivos de código fuente.
- **Utf8Output** / `-utf8output`: se muestran los mensajes del compilador en codificación UTF-8.
- **FileAlignment** / `-filealign`: se especifica la alineación utilizada para las secciones de archivos de salida.
- **ErrorEndLocation** / `-errorendlocation`: se muestra la línea y la columna de salida de la ubicación final de cada error.
- **NoStandardLib** / `-nostdlib`: no se hace referencia a la biblioteca estándar *mscorlib.dll*.
- **SubsystemVersion** / `-subsystemversion`: se especifica la versión del subsistema de este ensamblado.
- **ModuleAssemblyName** / `-moduleassemblyname`: nombre del ensamblado del que este módulo formará parte.

## <a name="mainentrypoint-or-startupobject"></a>MainEntryPoint o StartupObject

Esta opción especifica la clase que contiene el punto de entrada al programa si hay más de una clase que contenga un método `Main`.

```xml
<StartupObject>MyNamespace.Program</StartupObject>
```

or

```xml
<MainEntryPoint>MyNamespace.Program</MainEntryPoint>
```

Donde `Program` es el tipo que contiene el método `Main`. El nombre de clase proporcionado debe ser completo: debe incluir el espacio de nombres completo que contiene la clase, seguido del nombre de clase. Por ejemplo, cuando el método `Main` se encuentra dentro de la clase `Program` en el espacio de nombres `MyApplication.Core`, la opción del compilador tiene que ser `-main:MyApplication.Core.Program`. Si la compilación incluye más de un tipo con un método [`Main`](../../programming-guide/main-and-command-args/index.md), puede especificar qué tipo contiene el método `Main`.

> [!NOTE]
> Esta opción no se puede usar para un proyecto que incluya [instrucciones de nivel superior](../../programming-guide/main-and-command-args/top-level-statements.md), incluso si contiene uno o más métodos `Main`.

## <a name="pdbfile"></a>PdbFile

La opción del compilador **PdbFile** especifica el nombre y la ubicación del archivo de símbolos de depuración.  El valor `filename` especifica el nombre y la ubicación del archivo de símbolos de depuración.  

```xml
<PdbFile>filename</PdbFile>
```

Al especificar [**DebugType**](code-generation.md#debugtype), el compilador creará un archivo *.pdb* en el mismo directorio donde creará el archivo de salida (.exe o .dll). El archivo *.pdb* tiene el mismo nombre de archivo base que el del archivo de salida. **PdbFile** le permite especificar un nombre de archivo y una ubicación distintos a los predeterminados para el archivo .pdb. No se puede establecer esta opción del compilador en el entorno de desarrollo de Visual Studio, ni se puede cambiar mediante programación.  

## <a name="pathmap"></a>PathMap

La opción del compilador **PathMap** especifica cómo asignar rutas de acceso físicas a los nombres de rutas de acceso de origen generados por el compilador. Esta opción asigna cada ruta de acceso física en la máquina donde el compilador se ejecuta a una ruta de acceso correspondiente que debe escribirse en los archivos de salida. En el ejemplo siguiente, `path1` es la ruta completa a los archivos de código fuente en el entorno actual y `sourcePath1` es la ruta de origen sustituida por `path1` en cualquier archivo de salida. Para especificar varias rutas de acceso de origen asignadas, sepárelas mediante punto y coma.

```xml
<PathMap>path1=sourcePath1;path2=sourcePath2</PathMap>
```

El compilador escribe la ruta de acceso de origen en la salida por las razones siguientes:

1. La ruta de acceso de origen se sustituye por un argumento cuando se aplica <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> a un parámetro opcional.
1. La ruta de acceso de origen se inserta en un archivo PDB.
1. La ruta de acceso del archivo PDB se inserta en un archivo PE (ejecutable portable).

## <a name="applicationconfiguration"></a>ApplicationConfiguration

La opción del compilador **ApplicationConfiguration** permite a una aplicación de C# especificar la ubicación del archivo de configuración de la aplicación de un ensamblado (app.config) al Common Language Runtime (CLR) en tiempo de enlace del ensamblado.

```xml
<ApplicationConfiguration>file</ApplicationConfiguration>
```

`file` es el archivo de configuración de la aplicación que contiene los valores de enlace del ensamblado. Un uso de **ApplicationConfiguration** es para escenarios avanzados en los que un ensamblado tiene que hacer referencia a la versión de .NET Framework y a la de .NET Framework para Silverlight de un ensamblado de referencia determinado al mismo tiempo. Por ejemplo, un diseñador de XAML escrito en Windows Presentation Foundation (WPF) podría tener que hacer referencia al escritorio de WPF, para la interfaz de usuario del diseñador, y al subconjunto de WPF que se incluye con Silverlight. El mismo ensamblado del diseñador tiene que tener acceso a ambos ensamblados. De forma predeterminada, las referencias independientes producen un error del compilador, ya que el enlace del ensamblado considera los dos ensamblados equivalentes. La opción del compilador **ApplicationConfiguration** permite especificar la ubicación de un archivo app.config que deshabilita el comportamiento predeterminado mediante una etiqueta `<supportPortability>`, como se muestra en el ejemplo siguiente.

```xml
<supportPortability PKT="7cec85d7bea7798e" enable="false"/>
```

El compilador pasa la ubicación del archivo a la lógica de enlace del ensamblado de CLR.

> [!NOTE]
> Para usar el archivo app.config que ya está establecido en el proyecto, agregue la etiqueta de propiedades `<UseAppConfigForCompiler>` al archivo *.csproj* y establezca su valor en `true`. Para especificar otro archivo app.config, agregue la etiqueta `<AppConfigForCompiler>` de propiedades y establezca su valor en la ubicación del archivo.

En el siguiente ejemplo se muestra un archivo app.config que permite a una aplicación tener referencias a la implementación de .NET Framework y de .NET Framework para Silverlight de cualquier ensamblado de .NET Framework que exista en ambas implementaciones. La opción del compilador **ApplicationConfiguration** especifica la ubicación de este archivo app.config.

```xml
<configuration>
  <runtime>
    <assemblyBinding>
      <supportPortability PKT="7cec85d7bea7798e" enable="false"/>
      <supportPortability PKT="31bf3856ad364e35" enable="false"/>
    </assemblyBinding>
  </runtime>
</configuration>
```

## <a name="additionallibpaths"></a>AdditionalLibPaths

La opción **AdditionalLibPaths** especifica la ubicación de los ensamblados a los que se hace referencia con la opción [**References**](inputs.md#references).

```xml
<AdditionalLibPaths>dir1[,dir2]</AdditionalLibPaths>
```

`dir1` es un directorio donde el compilador busca si un ensamblado al que se hace referencia no se encuentra en el directorio de trabajo actual (el directorio desde el que se invoca al compilador) o en el directorio del sistema de Common Language Runtime. `dir2` es uno o varios directorios adicionales en los que buscar referencias a ensamblados. Separe los nombres de directorio con una coma y sin espacio en blanco entre ellos. El compilador busca referencias a ensamblados que no presentan la ruta completa en el siguiente orden:  

1. Directorio de trabajo actual.
1. El directorio del sistema de Common Language Runtime.
1. Directorios especificados por **AdditionalLibPaths**.
1. Directorios especificados por la variable de entorno LIB.

Use **Reference** para especificar una referencia a un ensamblado. **AdditionalLibPaths** es aditivo. Si se especifica más de una vez, se anexa a los valores existentes. Como en el manifiesto del ensamblado no se especifica la ruta al ensamblado dependiente, la aplicación buscará y usará el ensamblado en la caché global de ensamblados. El compilador que hace referencia al ensamblado no implica que el Common Language Runtime pueda encontrar y cargar el ensamblado en tiempo de ejecución. Vea [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../framework/deployment/how-the-runtime-locates-assemblies.md) para obtener los detalles sobre cómo busca el motor en tiempo de ejecución los ensamblados a los que se hace referencia.  

## <a name="generatefullpaths"></a>GenerateFullPaths

La opción **GenerateFullPaths** hace que el compilador especifique la ruta completa al archivo cuando se muestran los errores de compilación y las advertencias.
  
```Xml
<GenerateFullPaths>true</GenerateFullPaths>
```

De manera predeterminada, los errores y advertencias que se producen de la compilación especifican el nombre del archivo en el que se ha detectado el error. La opción **GenerateFullPaths** hace que el compilador especifique la ruta completa al archivo. Esta opción del compilador no está disponible en Visual Studio y no se puede cambiar mediante programación.

## <a name="preferreduilang"></a>PreferredUILang

Mediante la opción del compilador **PreferredUILang** puede especificar el idioma en el que el compilador de C# muestra el resultado, como los mensajes de error.

```xml
<PreferredUILang>language</PreferredUILang>
```

`language` es el [nombre del idioma](/windows/desktop/Intl/language-names) que se va a usar para la salida del compilador. Puede usar la opción del compilador **PreferredUILang** para especificar el idioma que quiere que use el compilador de C# para los mensajes de error y otra salida de la línea de comandos. Si el paquete de idioma para el idioma no está instalado, en su lugar se usa la configuración de idioma del sistema operativo.

## <a name="baseaddress"></a>BaseAddress

La opción **BaseAddress** permite especificar la dirección base preferida en la que cargar un archivo DLL. Para obtener más información sobre cuándo y por qué usar esta opción, vea el [blog de Larry Osterman](/archive/blogs/larryosterman/why-should-i-even-bother-to-use-dlls-in-my-system).

```xml
<BaseAddress>address</BaseAddress>
```

`address` es la dirección base del archivo DLL. Esta dirección puede especificarse como un número octal, hexadecimal o decimal. La dirección base predeterminada para un archivo DLL se establece mediante Common Language Runtime de .NET. La palabra de orden inferior en esta dirección se redondeará. Por ejemplo, si especifica `0x11110001`, se redondeará a `0x11110000`. Para completar el proceso de firma para un archivo DLL, use SN.EXE con la opción -R.

## <a name="checksumalgorithm"></a>ChecksumAlgorithm

Esta opción controla el algoritmo de suma de comprobación que se usa para codificar los archivos de código fuente en el archivo PDB.

```xml
<ChecksumAlgorithm>algorithm</ChecksumAlgorithm>
```

`algorithm` debe ser `SHA1` (el valor predeterminado) o `SHA256`.

## <a name="codepage"></a>CodePage

Esta opción especifica qué página de códigos se va a usar durante la compilación si la página necesaria no es la página de códigos predeterminada actual del sistema.
  
```xml
<CodePage>id</CodePage>
```

`id` es el id. de la página de códigos que se va a usar para todos los archivos de código fuente de la compilación. El compilador primero intenta interpretar todos los archivos de código fuente como UTF-8. Si los archivos de código fuente se encuentran en una codificación distinta de UTF-8 y usan caracteres que no sean ASCII de 7 bits, utilice la opción **CodePage** para especificar qué página de códigos se debe usar. **CodePage** se aplica a todos los archivos de código fuente de la compilación. Vea [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo) para obtener información sobre cómo buscar las páginas de códigos que se admiten en su sistema.

## <a name="utf8output"></a>Utf8Output

La opción **Utf8Output** muestra los resultados del compilador en codificación UTF-8.

```xml
<Utf8Output>true</Utf8Output>
```

En algunas configuraciones internacionales, el resultado del compilador no puede mostrarse correctamente en la consola. Use **Utf8Output** y redirija el resultado del compilador a un archivo.

## <a name="filealignment"></a>FileAlignment

La opción **FileAlignment** permite especificar el tamaño de las secciones en el archivo de salida. Los valores válidos son 512, 1024, 2048, 4096 y 8192. Estos valores están en bytes.

```xml
<FileAlignment>number</FileAlignment>
```

La opción **FileAlignment** se establece en la página **Avanzado** de las propiedades de **Compilación** del proyecto en Visual Studio. Cada sección se alineará en un límite que es un múltiplo del valor **FileAlignment**. No hay ningún valor predeterminado fijo. Si no se especifica **FileAlignment**, Common Language Runtime elige un valor predeterminado en tiempo de compilación. Al especificar el tamaño de la sección, el tamaño del archivo de salida se ve afectado. Modificar el tamaño de la sección puede ser útil para los programas que se ejecutan en dispositivos más pequeños. Use [DUMPBIN](/cpp/build/reference/dumpbin-options) para ver información sobre las secciones en el archivo de salida.

## <a name="errorendlocation"></a>ErrorEndLocation

Indica al compilador que muestre la línea y la columna de salida de la ubicación final de cada error.

```xml
<ErrorEndLocation>filename</ErrorEndLocation>
```

De forma predeterminada, el compilador escribe la ubicación inicial en el origen para todos los errores y advertencias. Cuando esta opción se establece en true, el compilador escribe la ubicación inicial y final para todos los errores y advertencias.

## <a name="nostandardlib"></a>NoStandardLib

**NoStandardLib** impide la importación de mscorlib.dll, que define el espacio de nombres System completo.

```xml
<NoStandardLib>true</NoStandardLib>
```

Use esta opción si desea definir o crear sus propios objetos y espacio de nombres System. Si no se especifica **NoStandardLib**, mscorlib.dll se importa en el programa (equivale a especificar `<NoStandardLib>false</NoStandardLib>`).

## <a name="subsystemversion"></a>SubsystemVersion

Especifica la versión mínima del subsistema en el que se ejecuta el archivo ejecutable. Normalmente, esta opción garantiza que el archivo ejecutable pueda usar características de seguridad que no están disponibles en versiones anteriores de Windows.

> [!NOTE]
> Para especificar el subsistema en sí mismo, use la opción del compilador [**TargetType**](./output.md#targettype).

```xml
<SubsystemVersion>major.minor</SubsystemVersion>
```

`major.minor` especifica la versión mínima necesaria del subsistema, expresada en una notación de puntos para las versiones principales y secundarias. Por ejemplo, puede especificar que una aplicación no se pueda ejecutar en un sistema operativo anterior a Windows 7. Establezca el valor de esta opción en 6.01, como se describe en la tabla que se muestra más adelante en este artículo. Especifique los valores de `major` y `minor` como números enteros. Los ceros a la izquierda en la versión `minor` no cambian la versión, pero los ceros a la derecha sí. Por ejemplo, 6.1 y 6.01 hacen referencia a la misma versión, pero 6.10 hace referencia a una versión diferente. Se recomienda expresar la versión secundaria como dos dígitos para evitar confusiones.

En la tabla siguiente se enumeran las versiones de subsistema habituales de Windows.

|Versión de Windows|Versión de subsistema|
|---------------------|-----------------------|
|Windows 2000|5.00|
|Windows XP|5.01|
|Windows Server 2003|5.02|
|Windows Vista|6.00|
|Windows 7|6.01|
|Windows Server 2008|6.01|
|Windows 8|6.02|

El valor predeterminado de la opción del compilador **SubsystemVersion** depende de las condiciones de la lista siguiente:

- El valor predeterminado es 6.02 si se establece cualquier opción del compilador en la siguiente lista:
  - [/target:appcontainerexe](output.md)
  - [/target:winmdobj](output.md)
  - [-platform:arm](output.md)
- El valor predeterminado es 6,00 si usa MSBuild, tiene como destino .NET Framework 4.5 y no ha configurado ninguna de las opciones del compilador que se han especificado anteriormente en esta lista.
- El valor predeterminado es 4.00 si no se cumple ninguna de las condiciones anteriores.

## <a name="moduleassemblyname"></a>ModuleAssemblyName

Especifica el nombre de un ensamblado con tipos no públicos a los que puede acceder un archivo *.netmodule*.

```xml
<ModuleAssemblyName>assembly_name</ModuleAssemblyName>
```

Se debería usar **ModuleAssemblyName** al compilar un archivo *.netmodule* cuando se cumplan las condiciones siguientes:

- *.netmodule* necesita acceder a los tipos no públicos de un ensamblado existente.
- Sabe el nombre del ensamblado en el que se compilará .netmodule.
- El ensamblado existente ha concedido acceso de ensamblado de confianza al ensamblado en el que se compilará *.netmodule*.

Para obtener más información sobre cómo crear un archivo .netmodule, vea la opción [**TargetType**](output.md#targettype) de **module**. Para obtener más información sobre los ensamblados de confianza, vea [Ensamblados de confianza](../../../standard/assembly/friend.md).
