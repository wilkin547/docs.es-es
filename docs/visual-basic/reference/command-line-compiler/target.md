---
description: Mas información sobre -target (Visual Basic)
title: -target
ms.date: 03/13/2018
helpviewer_keywords:
- target compiler options [Visual Basic]
- -target compiler options [Visual Basic]
- /target compiler options [Visual Basic]
ms.assetid: e0954147-548b-461f-9c4b-a8f88845616c
ms.openlocfilehash: 6f07bd081131934b9d7046f0db7b8a35acfce5fe
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100483604"
---
# <a name="-target-visual-basic"></a>-target (Visual Basic)

Especifica el formato de la salida del compilador.

## <a name="syntax"></a>Sintaxis

```console
-target:{exe | library | module | winexe | appcontainerexe | winmdobj}
```

## <a name="remarks"></a>Comentarios

En la siguiente tabla se resumen los efectos de la opción `-target`.

|**Opción**|**Comportamiento**|
|----------------|------------------|
|`-target:exe`|Hace que el compilador cree una aplicación de consola ejecutable.<br /><br /> Es la opción predeterminada si no se especifica ninguna opción `-target`. El archivo ejecutable se crea con una extensión .exe.<br /><br /> A menos que se especifique de otro modo con la opción `-out`, el nombre del archivo de salida toma el nombre del archivo de entrada que el procedimiento `Sub Main` contiene.<br /><br /> Solo se necesita un procedimiento `Sub Main` en los archivos de código fuente que se compilan en un archivo .exe. Use la opción de compilador `-main` para especificar qué clase contiene el procedimiento `Sub Main`.|
|`-target:library`|Hace que el compilador cree una biblioteca de vínculos dinámicos (DLL).<br /><br /> El archivo de biblioteca de vínculos dinámicos se crea con una extensión .dll.<br /><br /> A menos que se especifique lo contrario con la opción `-out`, el archivo de salida toma el nombre del primer archivo de entrada.<br /><br /> Al compilar un archivo DLL, no se necesita un procedimiento `Sub Main`.|
|`-target:module`|Hace que el compilador genere un módulo que se puede agregar a un ensamblado.<br /><br /> El archivo de salida se crea con una extensión .netmodule.<br /><br /> .NET Common Language Runtime no puede cargar un archivo que no tiene un ensamblado. En cambio, este archivo se puede incorporar en el manifiesto de un ensamblado usando `-reference`.<br /><br /> Cuando el código de un módulo hace referencia a tipos en otro módulo, ambos módulos deben incorporarse en un manifiesto de ensamblado usando `-reference`.<br /><br /> La opción [-addmodule](addmodule.md) importa los metadatos de un módulo.|
|`-target:winexe`|Hace que el compilador cree una aplicación basada en Windows ejecutable.<br /><br /> El archivo ejecutable se crea con una extensión .exe. Una aplicación basada en Windows es aquella que ofrece una interfaz de usuario de la biblioteca de clases de .NET Framework o con las API Windows.<br /><br /> A menos que se especifique de otro modo con la opción `-out`, el nombre del archivo de salida toma el nombre del archivo de entrada que el procedimiento `Sub Main` contiene.<br /><br /> Solo se necesita un procedimiento `Sub Main` en los archivos de código fuente que se compilan en un archivo .exe. En los casos en los que el código tiene más de una clase con un procedimiento `Sub Main`, use la opción de compilador `-main` para especificar qué clase contiene el procedimiento `Sub Main`|
|`-target:appcontainerexe`|Hace que el compilador cree una aplicación basada en Windows ejecutable que se debe ejecutar en un contenedor de la aplicación. Esta opción está concebida para usarse con aplicaciones de la Tienda Windows 8.x.<br /><br /> La opción **appcontainerexe** establece un bit en el campo Characteristics del archivo [portable ejecutable](/windows/desktop/Debug/pe-format). Este bit indica que la aplicación se debe ejecutar en un contenedor de la aplicación. Cuando ese bit se establece, se produce un error si el método `CreateProcess` intenta iniciar la aplicación fuera de un contenedor de la aplicación. Además de esta opción de bit, **-target:appcontainerexe** equivale a **-target:winexe**.<br /><br /> El archivo ejecutable se crea con una extensión .exe.<br /><br /> A menos que se especifique de otro modo con la opción `-out`, el nombre del archivo de salida toma el nombre del archivo de entrada que el procedimiento `Sub Main` contiene.<br /><br /> Solo se necesita un procedimiento `Sub Main` en los archivos de código fuente que se compilan en un archivo .exe. Si el código contiene más de una clase con un procedimiento `Sub Main`, use la opción de compilador `-main` para especificar qué clase contiene el procedimiento `Sub Main`|
|`-target:winmdobj`|Hace que el compilador cree un archivo intermedio que se puede convertir en archivo binario de Windows Runtime (.winmd). El archivo .winmd lo pueden usar programas de JavaScript y C++, además de los programas de lenguajes administrados.<br /><br /> El archivo intermedio se crea con una extensión .winmdobj.<br /><br /> A menos que se especifique de otro modo con la opción `-out`, el nombre del archivo de salida toma el nombre del primer archivo de entrada. No se necesita un procedimiento `Sub Main`.<br /><br /> El archivo .winmdobj está concebido para usarse como entrada de la herramienta de exportación <xref:Microsoft.Build.Tasks.WinMDExp> para generar un archivo de metadatos de Windows (WinMD). El archivo WinMD tiene una extensión .winmd, y contiene tanto el código de la biblioteca original como las definiciones de WinMD que JavaScript, C++ y Windows Runtime usan.|

A menos que especifique `-target:module`, `-target` hace que se agregue un manifiesto de ensamblado de .NET Framework a un archivo de salida.

Cada instancia de Vbc.exe genera un archivo de salida como máximo. Si se especifica una opción de compilador como `-out` o `-target` más de una vez, se aplicará la última que el compilador procese. La información sobre todos los archivos de una compilación se agrega al manifiesto. Todos los archivos de salida, excepto los creados con `-target:module`, contienen metadatos de ensamblado en el manifiesto. Use [Ildasm.exe (Desensamblador de IL)](../../../framework/tools/ildasm-exe-il-disassembler.md) para ver los metadatos de un archivo de salida.

La forma abreviada de `-target` es `-t`.

### <a name="to-set--target-in-the-visual-studio-ide"></a>Para establecer -target en el IDE de Visual Studio

1. Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**.

2. Haga clic en la pestaña **Aplicación** .

3. Modifique el valor en el cuadro **Tipo de aplicación**.

## <a name="example"></a>Ejemplo

El siguiente código compila `in.vb`, creando `in.dll`:

```console
vbc -target:library in.vb
```

## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](index.md)
- [-main](main.md)
- [-out (Visual Basic)](out.md)
- [-reference (Visual Basic)](reference.md)
- [-addmodule](addmodule.md)
- [-moduleassemblyname](moduleassemblyname.md)
- [Ensamblados de .NET](../../../standard/assembly/index.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
