---
title: -target
ms.date: 03/13/2018
helpviewer_keywords:
- target compiler options [Visual Basic]
- -target compiler options [Visual Basic]
- /target compiler options [Visual Basic]
ms.assetid: e0954147-548b-461f-9c4b-a8f88845616c
ms.openlocfilehash: d186670489ada51fced67ff9adeb73b14909b664
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716686"
---
# <a name="-target-visual-basic"></a>-Target (Visual Basic)

Especifica el formato de los resultados del compilador.

## <a name="syntax"></a>Sintaxis

```console
-target:{exe | library | module | winexe | appcontainerexe | winmdobj}
```

## <a name="remarks"></a>Notas

En la tabla siguiente se resume el efecto de la opción `-target`.

|**Opción**|**Behavior**|
|----------------|------------------|
|`-target:exe`|Hace que el compilador cree una aplicación de consola ejecutable.<br /><br /> Esta es la opción predeterminada cuando no se especifica ninguna opción de `-target`. El archivo ejecutable se crea con una extensión. exe.<br /><br /> A menos que se especifique lo contrario con la opción `-out`, el nombre del archivo de salida toma el nombre del archivo de entrada que contiene el procedimiento `Sub Main`.<br /><br /> Solo se requiere un procedimiento `Sub Main` en los archivos de código fuente que se compilan en un archivo. exe. Use la opción del compilador `-main` para especificar qué clase contiene el procedimiento de `Sub Main`.|
|`-target:library`|Hace que el compilador cree una biblioteca de vínculos dinámicos (DLL).<br /><br /> El archivo de biblioteca de vínculos dinámicos se crea con una extensión. dll.<br /><br /> A menos que se especifique lo contrario con la opción `-out`, el nombre del archivo de salida toma el nombre del primer archivo de entrada.<br /><br /> Al compilar un archivo DLL, no es necesario un procedimiento `Sub Main`.|
|`-target:module`|Hace que el compilador genere un módulo que se puede Agregar a un ensamblado.<br /><br /> El archivo de salida se crea con una extensión de. netmodule.<br /><br /> .NET Common Language Runtime no puede cargar un archivo que no tiene un ensamblado. Sin embargo, puede incorporar este tipo de archivo en el manifiesto del ensamblado de un ensamblado mediante `-reference`.<br /><br /> Cuando el código de un módulo hace referencia a tipos internos en otro módulo, ambos módulos deben incorporarse en un manifiesto de ensamblado mediante `-reference`.<br /><br /> La opción [-AddModule](../../../visual-basic/reference/command-line-compiler/addmodule.md) importa los metadatos de un módulo.|
|`-target:winexe`|Hace que el compilador cree una aplicación ejecutable basada en Windows.<br /><br /> El archivo ejecutable se crea con una extensión. exe. Una aplicación basada en Windows es aquella que proporciona una interfaz de usuario de la biblioteca de clases de .NET Framework o con las API de Windows.<br /><br /> A menos que se especifique lo contrario con la opción `-out`, el nombre del archivo de salida toma el nombre del archivo de entrada que contiene el procedimiento `Sub Main`.<br /><br /> Solo se requiere un procedimiento `Sub Main` en los archivos de código fuente que se compilan en un archivo. exe. En los casos en los que el código tenga más de una clase que tenga un procedimiento `Sub Main`, use la opción del compilador `-main` para especificar qué clase contiene el procedimiento `Sub Main`|
|`-target:appcontainerexe`|Hace que el compilador cree una aplicación ejecutable basada en Windows que se debe ejecutar en un contenedor de la aplicación. Esta opción está diseñada para usarse con aplicaciones de la tienda Windows 8. x.<br /><br /> El valor **appcontainerexe** establece un bit en el campo características del archivo [ejecutable portable](/windows/desktop/Debug/pe-format) . Este bit indica que la aplicación se debe ejecutar en un contenedor de la aplicación. Cuando se establece este bit, se produce un error si el método `CreateProcess` intenta iniciar la aplicación fuera de un contenedor de la aplicación. Además de esta configuración de bits, **-target: appcontainerexe** es equivalente a **-target: winexe**.<br /><br /> El archivo ejecutable se crea con una extensión. exe.<br /><br /> A menos que especifique lo contrario con la opción `-out`, el nombre del archivo de salida toma el nombre del archivo de entrada que contiene el procedimiento `Sub Main`.<br /><br /> Solo se requiere un procedimiento `Sub Main` en los archivos de código fuente que se compilan en un archivo. exe. Si el código contiene más de una clase que tiene un procedimiento `Sub Main`, use la opción del compilador `-main` para especificar qué clase contiene el procedimiento `Sub Main`|
|`-target:winmdobj`|Hace que el compilador cree un archivo intermedio que se puede convertir en un archivo binario de Windows Runtime (. winmd). El archivo. winmd lo pueden usar JavaScript y C++ programas, además de los programas de lenguaje administrados.<br /><br /> El archivo intermedio se crea con una extensión. winmdobj.<br /><br /> A menos que especifique lo contrario con la opción `-out`, el nombre del archivo de salida toma el nombre del primer archivo de entrada. No es necesario un procedimiento `Sub Main`.<br /><br /> El archivo. winmdobj está diseñado para usarse como entrada de la herramienta de exportación de <xref:Microsoft.Build.Tasks.WinMDExp> para generar un archivo de metadatos de Windows (WinMD). El archivo WinMD tiene una extensión. WinMD y contiene el código de la biblioteca original y las definiciones de WinMD que usan JavaScript C++, y el Windows Runtime usar.|

A menos que especifique `-target:module`, `-target` hace que se agregue un manifiesto de ensamblado .NET Framework a un archivo de salida.

Cada instancia de VBC. exe genera, como máximo, un archivo de salida. Si especifica una opción del compilador como `-out` o `-target` más de una vez, se aplicará la última que procese el compilador. La información sobre todos los archivos de una compilación se agrega al manifiesto. Todos los archivos de salida, excepto los creados con `-target:module`, contienen metadatos de ensamblado en el manifiesto. Use [Ildasm. exe (desensamblador de IL)](../../../framework/tools/ildasm-exe-il-disassembler.md) para ver los metadatos de un archivo de salida.

La forma abreviada de `-target` es `-t`.

### <a name="to-set--target-in-the-visual-studio-ide"></a>Para establecer-target en el IDE de Visual Studio

1. Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**.

2. Haga clic en la pestaña **Aplicación** .

3. Modifique el valor en el cuadro **tipo de aplicación** .

## <a name="example"></a>Ejemplo

El código siguiente compila `in.vb`, creando `in.dll`:

```console
vbc -target:library in.vb
```

## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-main](../../../visual-basic/reference/command-line-compiler/main.md)
- [-out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)
- [-Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [-moduleassemblyname](../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md)
- [Ensamblados de .NET](../../../standard/assembly/index.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
