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
ms.openlocfilehash: 8c7789c6af7b82ecb40ecd73d09f64aa1da3fd4b
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005058"
---
# <a name="-vbruntime"></a>-vbruntime
Especifica que el compilador debe compilar sin una referencia a la biblioteca de tiempo de ejecución de Visual Basic o con una referencia a una biblioteca de tiempo de ejecución específica.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a>Argumentos  
 \-  
 Compile sin una referencia a la biblioteca en tiempo de ejecución de Visual Basic.  
  
 \+  
 Compilar con una referencia a la biblioteca en tiempo de ejecución de Visual Basic predeterminada.  
  
 \*  
 Compile sin una referencia a la biblioteca en tiempo de ejecución de Visual Basic e inserte la funcionalidad básica de la biblioteca en tiempo de ejecución de Visual Basic en el ensamblado.  
  
 `path`  
 Compilar con una referencia a la biblioteca especificada (DLL).  
  
## <a name="remarks"></a>Comentarios  
 La opción del compilador `-vbruntime` le permite especificar que el compilador debe compilar sin una referencia a la biblioteca en tiempo de ejecución de Visual Basic. Si compila sin una referencia a la biblioteca en tiempo de ejecución de Visual Basic, se registran errores o advertencias en construcciones de código o de lenguaje que generan una llamada a una aplicación auxiliar de Visual Basic en tiempo de ejecución. (Una *aplicación auxiliar en tiempo de ejecución de Visual Basic* es una función definida en Microsoft. VisualBasic. dll a la que se llama en tiempo de ejecución para ejecutar una semántica específica del lenguaje).  
  
 La opción `-vbruntime+` produce el mismo comportamiento que se produce si no se especifica ningún modificador `-vbruntime`. Puede usar la opción `-vbruntime+` para invalidar los conmutadores `-vbruntime` anteriores.  
  
 La mayoría de los objetos del tipo `My` no están disponibles cuando se usan las opciones `-vbruntime-` o `-vbruntime:path`.  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a>Incrustar Visual Basic funcionalidad básica en tiempo de ejecución  
 La opción `-vbruntime*` le permite compilar sin una referencia a una biblioteca en tiempo de ejecución. En su lugar, la funcionalidad básica de la biblioteca en tiempo de ejecución de Visual Basic se incrusta en el ensamblado del usuario. Puede usar esta opción si la aplicación se ejecuta en plataformas que no contienen el tiempo de ejecución de Visual Basic.  
  
 Los siguientes miembros en tiempo de ejecución están incrustados:  
  
- Clase <xref:Microsoft.VisualBasic.CompilerServices.Conversions>  
  
- Método <xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29>  
  
- Método <xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29>  
  
- Método <xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29>  
  
- <xref:Microsoft.VisualBasic.Constants.vbBack> (constante)  
  
- <xref:Microsoft.VisualBasic.Constants.vbCr> (constante)  
  
- <xref:Microsoft.VisualBasic.Constants.vbCrLf> (constante)  
  
- <xref:Microsoft.VisualBasic.Constants.vbFormFeed> (constante)  
  
- <xref:Microsoft.VisualBasic.Constants.vbLf> (constante)  
  
- <xref:Microsoft.VisualBasic.Constants.vbNewLine> (constante)  
  
- <xref:Microsoft.VisualBasic.Constants.vbNullChar> (constante)  
  
- <xref:Microsoft.VisualBasic.Constants.vbNullString> (constante)  
  
- <xref:Microsoft.VisualBasic.Constants.vbTab> (constante)  
  
- <xref:Microsoft.VisualBasic.Constants.vbVerticalTab> (constante)  
  
- Algunos objetos del tipo `My`  
  
 Si se compila con la opción `-vbruntime*` y el código hace referencia a un miembro de la biblioteca en tiempo de ejecución de Visual Basic que no está incrustada con la funcionalidad básica, el compilador devuelve un error que indica que el miembro no está disponible.  
  
## <a name="referencing-a-specified-library"></a>Hacer referencia a una biblioteca especificada  
 Puede usar el argumento `path` para compilar con una referencia a una biblioteca en tiempo de ejecución personalizada en lugar de la biblioteca en tiempo de ejecución de Visual Basic predeterminada.  
  
 Si el valor del argumento `path` es una ruta de acceso completa a un archivo DLL, el compilador usará ese archivo como la biblioteca en tiempo de ejecución. Si el valor del argumento `path` no es una ruta de acceso completa a un archivo DLL, el compilador de Visual Basic buscará primero el archivo DLL identificado en la carpeta actual. A continuación, buscará en la ruta de acceso que ha especificado mediante la opción del compilador [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) . Si no se utiliza la opción del compilador `-sdkpath`, el compilador buscará el archivo DLL identificado en la carpeta de .NET Framework (`%systemroot%\Microsoft.NET\Framework\versionNumber`).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar la opción `-vbruntime` para compilar con una referencia a una biblioteca personalizada.  
  
```console
vbc -vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a>Vea también

- [Visual Basic Core: nuevo modo de compilación en Visual Studio 2010 SP1](https://devblogs.microsoft.com/vbteam/vb-core-new-compilation-mode-in-visual-studio-2010-sp1/)
- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
