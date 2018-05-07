---
title: -vbruntime
ms.date: 03/13/2018
f1_keywords:
- vbruntime
- -vbruntime
helpviewer_keywords:
- vbruntime compiler option [Visual Basic]
- -vbruntime compiler option [Visual Basic]
- /vbruntime compiler option [Visual Basic]
ms.assetid: 1aa0239e-511a-4c29-957d-fd72877b350a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d28d0556a662099e4e5e74b22583fc3c8b4c313f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="-vbruntime"></a>-vbruntime
Especifica que el compilador debe compilar sin una referencia a la biblioteca de tiempo de ejecución de Visual Basic o con una referencia a una biblioteca de tiempo de ejecución específica.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a>Argumentos  
 \-  
 Compilar sin una referencia a la biblioteca en tiempo de ejecución de Visual Basic.  
  
 \+  
 Compilar con una referencia a la biblioteca en tiempo de ejecución de Visual Basic predeterminada.  
  
 \*  
 Compilar sin una referencia a la biblioteca en tiempo de ejecución de Visual Basic e incrustar la funcionalidad básica de la biblioteca en tiempo de ejecución de Visual Basic en el ensamblado.  
  
 `path`  
 Compilar con una referencia a la biblioteca especificada (DLL).  
  
## <a name="remarks"></a>Comentarios  
 El `-vbruntime` opción del compilador le permite especificar que el compilador debe compilar sin una referencia a la biblioteca en tiempo de ejecución de Visual Basic. Si compila sin una referencia a la biblioteca en tiempo de ejecución de Visual Basic, errores o advertencias se registran en construcciones de código o lenguaje que generan una llamada a una aplicación auxiliar de tiempo de ejecución de Visual Basic. (Un *aplicación auxiliar de tiempo de ejecución de Visual Basic* es una función definida en Microsoft.VisualBasic.dll a la que se llama en tiempo de ejecución para ejecutar una semántica concreta del lenguaje.)  
  
 El `-vbruntime+` opción produce el mismo comportamiento que se produce si no hay ningún `-vbruntime` ha especificado el modificador. Puede usar el `-vbruntime+` opción para invalidar anterior `-vbruntime` conmutadores.  
  
 Mayoría de los objetos de la `My` tipo no están disponibles cuando se usa el `-vbruntime-` o `-vbruntime:path` opciones.  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a>Incrustar la funcionalidad básica de tiempo de ejecución de Visual Basic  
 El `-vbruntime*` opción le permite compilar sin una referencia a una biblioteca en tiempo de ejecución. En su lugar, la funcionalidad básica de la biblioteca en tiempo de ejecución de Visual Basic se incrusta en el ensamblado de usuario. Puede usar esta opción si la aplicación se ejecuta en plataformas que no contienen el tiempo de ejecución de Visual Basic.  
  
 Se incrustan los siguientes miembros de tiempo de ejecución:  
  
-   Clase <xref:Microsoft.VisualBasic.CompilerServices.Conversions>  
  
-   Método <xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29>  
  
-   Método <xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29>  
  
-   Método <xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbBack> (constante)  
  
-   <xref:Microsoft.VisualBasic.Constants.vbCr> (constante)  
  
-   <xref:Microsoft.VisualBasic.Constants.vbCrLf> (constante)  
  
-   <xref:Microsoft.VisualBasic.Constants.vbFormFeed> (constante)  
  
-   <xref:Microsoft.VisualBasic.Constants.vbLf> (constante)  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNewLine> (constante)  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNullChar> (constante)  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNullString> (constante)  
  
-   <xref:Microsoft.VisualBasic.Constants.vbTab> (constante)  
  
-   <xref:Microsoft.VisualBasic.Constants.vbVerticalTab> (constante)  
  
-   Algunos objetos de la `My` tipo  
  
 Si se compila utilizando el `-vbruntime*` opción y el código hace referencia a un miembro de la biblioteca en tiempo de ejecución de Visual Basic que no se incrusta con la funcionalidad básica, el compilador devuelve un error que indica que el miembro no está disponible.  
  
## <a name="referencing-a-specified-library"></a>Hacer referencia a una biblioteca especificada  
 Puede usar el `path` argumento para compilar con una referencia a una biblioteca en tiempo de ejecución personalizado en lugar de la biblioteca en tiempo de ejecución de Visual Basic predeterminada.  
  
 Si el valor de la `path` argumento es una ruta de acceso completa a un archivo DLL, el compilador usará ese archivo como la biblioteca en tiempo de ejecución. Si el valor de la `path` argumento no es una ruta de acceso completa a un archivo DLL, el compilador de Visual Basic buscará la DLL identificada en la carpeta actual en primer lugar. A continuación, buscará en la ruta de acceso que ha especificado mediante el uso de la [- sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) opción del compilador. Si el `-sdkpath` no se utiliza la opción del compilador, el compilador buscará la DLL identificada en la carpeta .NET Framework (`%systemroot%\Microsoft.NET\Framework\versionNumber`).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar el `-vbruntime` opción de compilar con una referencia a una biblioteca personalizada.  
  
```console
vbc -vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a>Vea también  
 [Núcleo de Visual Basic: nuevo modo de compilación en Visual Studio 2010 SP1](http://blogs.msdn.com/b/vbteam/archive/2011/01/10/vb-core-new-compilation-mode-in-visual-studio-2010-sp1.aspx)  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
