---
description: Opciones del compilador de C# que controlan la salida del compilador. Estas opciones controlan la generación del ensamblado a partir de una compilación.
title: 'Opciones del compilador de C#: opciones de salida'
ms.date: 03/12/2021
f1_keywords:
- cs.build.options
helpviewer_keywords:
- DocumentationFile compiler option [C#]
- OutputAssembly compiler option [C#]
- PlatformTarget compiler option [C#]
- ProduceReferenceAssembly compiler option [C#]
- TargetType compiler option [C#]
ms.openlocfilehash: 2d8b7edbf970875d7300a394ab75756c1316ac9d
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103482476"
---
# <a name="c-compiler-options-that-control-compiler-output"></a>Opciones del compilador de C# que controlan la salida del compilador

Las opciones siguientes controlan la generación de salida del compilador. La nueva sintaxis de MSBuild se muestra en **negrita**. La sintaxis de *csc.exe* anterior se muestra en `code style`.

- **DocumentationFile** / `-doc`: se genera un archivo de documentación XML a partir de los comentarios de `///`.
- **OutputAssembly** / `-out`: se especifica el archivo de ensamblado de salida.
- **PlatformTarget** / `-platform`: se especifica la CPU de la plataforma de destino.
- **ProduceReferenceAssembly** / `-refout`: se genera un ensamblado de referencia.
- **TargetType** `-target`: se especifica el tipo del ensamblado de salida.

## <a name="documentationfile"></a>DocumentationFile

La opción **DocumentationFile** permite insertar comentarios de documentación en un archivo XML. Para obtener más información sobre cómo documentar el código, vea [Etiquetas recomendadas para comentarios de documentación](../../programming-guide/xmldoc/recommended-tags-for-documentation-comments.md). El valor especifica la ruta al archivo XML de salida. El archivo XML contiene los comentarios en los archivos de código fuente de la compilación.

```xml
<DocumentationFile>path/to/file.xml</DocumentationFile>
```

El archivo de código fuente que contiene instrucciones principales o de nivel superior se genera primero en el XML. A menudo, querrá usar el archivo .xml generado con [IntelliSense](/visualstudio/ide/using-intellisense). El nombre de archivo *.xml* debe ser el mismo que el nombre del ensamblado. El archivo *.xml* debe estar en el mismo directorio que el ensamblado. Cuando se hace referencia al ensamblado en un proyecto de Visual Studio, también se encuentra el archivo *.xml*. Para obtener más información sobre la generación de comentarios de código, vea [Proporcionar comentarios de código](/visualstudio/ide/reference/generate-xml-documentation-comments). A menos que realice la compilación con [`<TargetType:Module>`](#targettype), `file` contendrá etiquetas `<assembly>` y `</assembly>` que especifican el nombre del archivo que incluye el manifiesto del ensamblado para el archivo de salida. Para obtener ejemplos, vea [Procedimiento para usar las características de la documentación XML](../../programming-guide/xmldoc/how-to-use-the-xml-documentation-features.md).

> [!NOTE]
> La opción **DocumentationFile** se aplica a todos los archivos del proyecto. Para deshabilitar las advertencias relacionadas con los comentarios de documentación para un archivo específico o una sección de código, use [#pragma warning](../preprocessor-directives/preprocessor-pragma-warning.md).

## <a name="outputassembly"></a>OutputAssembly

La opción **OutputAssembly** especifica el nombre del archivo de salida. En la ruta de salida se especifica la carpeta donde se coloca la salida del compilador.

```xml
<OutputAssembly>folder</OutputAssembly>
```

Hay que especificar el nombre completo y la extensión del archivo que se quiere crear. Si no especifica el nombre del archivo de salida, MSBuild usa el nombre del proyecto para especificar el nombre del ensamblado de salida. Los proyectos de estilo antiguo usan las reglas siguientes:

- Un archivo .exe toma el nombre del archivo de código fuente que contiene el método `Main` o instrucciones de nivel superior.  
- Un archivo .dll o .netmodule toma el nombre del primer archivo de código fuente.

Todos los módulos que se produzcan como parte de una compilación se convierten en archivos asociados a cualquier ensamblado que también se haya producido en la compilación. Use [ildasm.exe](../../../framework/tools/ildasm-exe-il-disassembler.md) para ver el manifiesto del ensamblado y los archivos asociados.

Es obligatorio usar la opción del compilador **OutputAssembly** para que un archivo exe sea el destino de un [ensamblado de confianza](../../../standard/assembly/friend.md).

## <a name="platformtarget"></a>PlatformTarget

Especifica qué versión de CLR puede ejecutar el ensamblado.

```xml
<PlatformTarget>anycpu</PlatformTarget>
```

- **anycpu** (valor predeterminado) compila el ensamblado de forma que se pueda ejecutar en cualquier plataforma. La aplicación se ejecuta como un proceso de 64 bits siempre que sea posible y recurre a 32 bits solo cuando el modo está disponible.
- **anycpu32bitpreferred** compila el ensamblado de forma que se pueda ejecutar en cualquier plataforma. La aplicación se ejecuta en modo de 32 bits en sistemas que admiten aplicaciones de 64 y 32 bits. Solo puede especificar esta opción para los proyectos que tienen como destino .NET Framework 4.5 o versiones posteriores.
- **ARM** compila el ensamblado de forma que pueda ejecutarse en un equipo que tenga un procesador Advanced RISC Machine (ARM).
- **ARM64** compila el ensamblado que se va a ejecutar mediante el CLR de 64 bits en un equipo que tiene un procesador Advanced RISC Machine (ARM) que admite el conjunto de instrucciones A64.
- **x64** compila el ensamblado de forma que el CLR de 64 bits pueda ejecutarlo en equipos compatibles con el conjunto de instrucciones AMD64 o EM64T.
- **x86** compila el ensamblado de forma que el CLR de 32 bits compatible con x86 pueda ejecutarlo.
- **Itanium** compila el ensamblado de forma que el CLR de 64 bits pueda ejecutarlo en un equipo con un procesador Itanium.

En un sistema operativo de Windows de 64 bits:

- Los ensamblados compilados con **x86** se ejecutan en el CLR de 32 bits que se ejecuta en WOW64.
- Un archivo DLL compilado con **anycpu** se ejecuta en el mismo CLR que el proceso en el que se ha cargado.
- Los archivos ejecutables que se compilan con **anycpu** se ejecutan en el CLR de 64 bits.
- Los archivos ejecutables compilados con **anycpu32bitpreferred** se ejecutan en el CLR de 32 bits.

El valor **anycpu32bitpreferred** solo es válido para archivos ejecutables (.EXE) y requiere .NET Framework 4.5 o una versión posterior. Para obtener más información sobre cómo desarrollar una aplicación para que se ejecute en un sistema operativo Windows de 64 bits, consulte [Aplicaciones de 64 bits](../../../framework/64-bit-apps.md).

La opción **PlatformTarget** se establece en la página de propiedades de **compilación** del proyecto en Visual Studio.

El comportamiento de **anycpu** tiene algunos matices adicionales en .NET Core y .NET 5 y versiones posteriores. Cuando establezca **anycpu**, publique la aplicación y ejecútela con `dotnet.exe` de x86 o `dotnet.exe` de x64. En el caso de las aplicaciones independientes, en el paso `dotnet publish` se empaqueta el archivo ejecutable para el RID de configuración.

## <a name="producereferenceassembly"></a>ProduceReferenceAssembly

La opción **ProduceReferenceAssembly** especifica una ruta de archivo donde se debe mostrar el ensamblado de referencia. Se traduce por `metadataPeStream` en la API de emisión. `filepath` especifica la ruta para el ensamblado de referencia. Generalmente debe coincidir con el ensamblado principal. La convención recomendada (que usa MSBuild) consiste en colocar el ensamblado de referencia en una subcarpeta "ref/" con relación al ensamblado principal.

```xml
<ProduceReferenceAssembly>filepath</ProduceReferenceAssembly>
```

Los ensamblados de referencia son un tipo especial de ensamblado que contiene solo la cantidad mínima de metadatos necesarios para representar la superficie de API pública de la biblioteca. Incluyen declaraciones para todos los miembros importantes al hacer referencia a un ensamblado en las herramientas de compilación. Los ensamblados de referencia excluyen todas las implementaciones de miembros y declaraciones de miembros privados. Esos miembros no tienen ningún impacto observable en su contrato de API. Para obtener más información, vea [Ensamblados de referencia](../../../standard/assembly/reference-assemblies.md) en la Guía de .NET.

Las opciones **ProduceReferenceAssembly** y [**ProduceOnlyReferenceAssembly**](./code-generation.md#produceonlyreferenceassembly) son mutuamente excluyentes.

## <a name="targettype"></a>TargetType

La opción del compilador **TargetType** se puede especificar en uno de los formatos siguientes:  
  
- **library**: para crear una biblioteca de código. **library** es el valor predeterminado.
- **exe**: para crear un archivo .exe.  
- **module** para crear un módulo.  
- **winexe** para crear un programa de Windows.
- **winmdobj** para crear un archivo *.winmdobj* intermedio.
- **appcontainerexe** para crear un archivo .exe para aplicaciones Windows 8.x de Microsoft Store.
  
> [!NOTE]
> Para los destinos de .NET Framework, a menos que especifique **module**, esta opción hace que se coloque un manifiesto del ensamblado de .NET Framework en un archivo de salida. Para obtener más información, vea [Ensamblados en .NET](../../../standard/assembly/index.md) y [Atributos comunes](../attributes/global.md).

```xml
<TargetType>library</TargetType>
```

El compilador crea solo un manifiesto de ensamblado por compilación. La información sobre todos los archivos de una compilación se coloca en el manifiesto de ensamblado. Cuando se generan varios archivos de salida en la línea de comandos, solo se puede crear un manifiesto de ensamblado que debe ir en el primer archivo de salida especificado en la línea de comandos.

Si crea un ensamblado, puede indicar que todo o parte del código es conforme a CLS mediante el atributo <xref:System.CLSCompliantAttribute>.

### <a name="library"></a>biblioteca

La opción **library** hace que el compilador cree una biblioteca de vínculos dinámicos (DLL) en lugar de un archivo ejecutable (EXE). El archivo DLL se creará con la extensión *.dll*. A menos que se especifique lo contrario con la opción [**OutputAssembly**](#outputassembly), el archivo de salida adopta el nombre del primer archivo de entrada. Al compilar un archivo *.dll*, no es necesario un método [`Main`](../../programming-guide/main-and-command-args/index.md).

### <a name="exe"></a>exe

La opción **exe** hace que el compilador cree una aplicación de consola ejecutable (EXE). El archivo ejecutable se creará con la extensión .exe. Use **winexe** para crear un archivo ejecutable de un programa de Windows. A menos que se especifique de otro modo con la opción [**OutputAssembly**](#outputassembly), el nombre del archivo de salida toma el del archivo de entrada que contiene el punto de entrada (el método [Main](../../programming-guide/main-and-command-args/index.md) o instrucciones de nivel superior). Solo se necesita un punto de entrada en los archivos de código fuente que se compilan en un archivo .exe. La opción del compilador [**StartupObject**](./advanced.md#mainentrypoint-or-startupobject) le permite especificar qué clase contiene el método `Main`, en aquellos casos en los que el código tenga más de una clase con un método `Main`.  

### <a name="module"></a>module

Esta opción hace que el compilador no genere un manifiesto del ensamblado. De forma predeterminada, el archivo de salida creado al realizar la compilación con esta opción tendrá una extensión *.netmodule*. El entorno de ejecución de .NET no puede cargar un archivo que no tiene un manifiesto del ensamblado. Pero este archivo se puede incorporar en el manifiesto del ensamblado con [**AddModules**](inputs.md#addmodules). Si se crea más de un módulo en una única compilación, los tipos [internal](../keywords/internal.md) que haya en un módulo estarán disponibles para otros módulos de la compilación. Cuando el código de un módulo hace referencia a tipos `internal` de otro, se deben incorporar los dos módulos en un manifiesto del ensamblado, mediante [**AddModules**](inputs.md#addmodules). No se admite la creación de un módulo en el entorno de desarrollo de Visual Studio.

### <a name="winexe"></a>winexe

La opción **winexe** hace que el compilador cree un programa de Windows ejecutable (EXE). El archivo ejecutable se creará con la extensión .exe. Un programa de Windows es el que ofrece una interfaz de usuario de la biblioteca de .NET o con las API Windows. Use **exe** para crear una aplicación de consola. A menos que se especifique de otro modo con la opción [**OutputAssembly**](#outputassembly), el nombre del archivo de salida toma el nombre del archivo de entrada que contiene el método [`Main`](../../programming-guide/main-and-command-args/index.md). Solo se necesita un método `Main` en los archivos de código fuente que se compilan en un archivo .exe. La opción [**StartupObject**](./advanced.md#mainentrypoint-or-startupobject) le permite especificar qué clase contiene el método `Main`, en aquellos casos en los que el código tenga más de una clase con un método `Main`.

### <a name="winmdobj"></a>winmdobj

Si usa la opción **winmdobj**, el compilador crea un archivo *.winmdobj* intermedio que se puede convertir en un archivo binario de Windows Runtime ( *.winmd*). Después, el archivo *.winmd* se puede usar en programas de JavaScript y C++, además de programas de lenguajes administrados.

El valor **winmdobj** indica al compilador que un módulo intermedio es obligatorio. Después, el archivo *.winmdobj* se puede proporcionar por medio de la herramienta de exportación <xref:Microsoft.Build.Tasks.WinMDExp> para generar un archivo de metadatos de Windows ( *.winmd*). El archivo *.winmd* contiene el código de la biblioteca original y los metadatos de WinMD que usan JavaScript o C++, y Windows Runtime. La salida de un archivo compilado mediante la opción del compilador **winmdobj** solo se usa como entrada de la herramienta de exportación WimMDExp. No se hace referencia directamente al archivo *.winmdobj*. A menos que use la opción [**OutputAssembly**](#outputassembly), el nombre del archivo de salida tomar el del primer archivo de entrada. No se necesita un método [`Main`](../../programming-guide/main-and-command-args/index.md).

### <a name="appcontainerexe"></a>appcontainerexe

Si usa la opción del compilador **appcontainerexe**, este crea un archivo ejecutable de Windows ( *.exe*) que se debe ejecutar en un contenedor de la aplicación. Esta opción equivale a [-target:winexe](./target-winexe-compiler-option.md), pero está diseñada para las aplicaciones de la Tienda Windows 8.x.

Para exigir que la aplicación se ejecute en un contenedor de la aplicación, esta opción establece un bit en el archivo [portable ejecutable](/windows/desktop/Debug/pe-format) (PE). Cuando se establece ese bit, se produce un error si el método CreateProcess intenta iniciar el archivo ejecutable fuera de un contenedor de la aplicación. A menos que use la opción [**OutputAssembly**](#outputassembly), el nombre del archivo de salida toma el del archivo de entrada que contiene el método [`Main`](../../programming-guide/main-and-command-args/index.md).
