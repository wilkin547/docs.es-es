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
ms.openlocfilehash: e83a85e29eb4447f8d3b9dddc4f6ccdbc771b23c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43515621"
---
# <a name="-vbruntime"></a>-vbruntime
Especifica que el compilador debe compilar sin una referencia a la biblioteca de tiempo de ejecución de Visual Basic o con una referencia a una biblioteca de tiempo de ejecución específica.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a>Argumentos  
 \-  
 Compilar sin referencia alguna a la biblioteca en tiempo de ejecución de Visual Basic.  
  
 \+  
 Compilar con una referencia a la biblioteca en tiempo de ejecución de Visual Basic predeterminada.  
  
 \*  
 Compilar sin referencia alguna a la biblioteca en tiempo de ejecución de Visual Basic e incrustar la funcionalidad básica de la biblioteca en tiempo de ejecución de Visual Basic en el ensamblado.  
  
 `path`  
 Compilar con una referencia a la biblioteca especificada (DLL).  
  
## <a name="remarks"></a>Comentarios  
 El `-vbruntime` opción del compilador le permite especificar que el compilador debe compilar sin referencia alguna a la biblioteca en tiempo de ejecución de Visual Basic. Si se compila sin una referencia a la biblioteca en tiempo de ejecución de Visual Basic, errores o advertencias se registran en construcciones de código o lenguaje que generan una llamada a una aplicación auxiliar de tiempo de ejecución de Visual Basic. (Un *aplicación auxiliar de tiempo de ejecución de Visual Basic* es una función definida en Microsoft.VisualBasic.dll que se llama en tiempo de ejecución para ejecutar un semántica de lenguaje específico.)  
  
 El `-vbruntime+` opción produce el mismo comportamiento que se produce si no hay ningún `-vbruntime` ha especificado el modificador. Puede usar el `-vbruntime+` opción de invalidar anterior `-vbruntime` conmutadores.  
  
 Mayoría de los objetos de la `My` tipo no están disponibles cuando se usa el `-vbruntime-` o `-vbruntime:path` opciones.  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a>Incrustar funcionalidad de tiempo de ejecución de Visual Basic  
 El `-vbruntime*` opción le permite compilar sin una referencia a una biblioteca en tiempo de ejecución. En su lugar, la funcionalidad básica de la biblioteca en tiempo de ejecución de Visual Basic se incrusta en el ensamblado de usuario. Puede usar esta opción si la aplicación se ejecuta en plataformas que no contienen el tiempo de ejecución de Visual Basic.  
  
 Se insertan los siguientes miembros de tiempo de ejecución:  
  
-   Clase <xref:Microsoft.VisualBasic.CompilerServices.Conversions>  
  
-   Método <xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29>  
  
-   Método <xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29>  
  
-   Método <xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbBack> Constante  
  
-   <xref:Microsoft.VisualBasic.Constants.vbCr> Constante  
  
-   <xref:Microsoft.VisualBasic.Constants.vbCrLf> Constante  
  
-   <xref:Microsoft.VisualBasic.Constants.vbFormFeed> Constante  
  
-   <xref:Microsoft.VisualBasic.Constants.vbLf> Constante  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNewLine> Constante  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNullChar> Constante  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNullString> Constante  
  
-   <xref:Microsoft.VisualBasic.Constants.vbTab> Constante  
  
-   <xref:Microsoft.VisualBasic.Constants.vbVerticalTab> Constante  
  
-   Algunos objetos de la `My` tipo  
  
 Si compila con la `-vbruntime*` opción y el código hace referencia a un miembro de la biblioteca en tiempo de ejecución de Visual Basic que no están integrados con la funcionalidad básica, el compilador devuelve un error que indica que el miembro no está disponible.  
  
## <a name="referencing-a-specified-library"></a>Hacer referencia a una biblioteca especificada  
 Puede usar el `path` argumento para compilar con una referencia a una biblioteca de tiempo de ejecución personalizado en lugar de la biblioteca en tiempo de ejecución de Visual Basic predeterminada.  
  
 Si el valor de la `path` argumento es una ruta de acceso completa a un archivo DLL, el compilador usará ese archivo como la biblioteca en tiempo de ejecución. Si el valor de la `path` argumento no es una ruta de acceso completa a un archivo DLL, el compilador de Visual Basic buscará la DLL identificada en la carpeta actual en primer lugar. A continuación, buscará en la ruta de acceso que ha especificado mediante el uso de la [- sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) opción del compilador. Si el `-sdkpath` no se usa la opción del compilador, el compilador buscará la DLL identificada en la carpeta de .NET Framework (`%systemroot%\Microsoft.NET\Framework\versionNumber`).  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo usar el `-vbruntime` opción de compilar con una referencia a una biblioteca personalizada.  
  
```console
vbc -vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a>Vea también  
 [Principales de Visual Basic: nuevo modo de compilación en Visual Studio 2010 SP1](https://blogs.msdn.com/b/vbteam/archive/2011/01/10/vb-core-new-compilation-mode-in-visual-studio-2010-sp1.aspx)  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
