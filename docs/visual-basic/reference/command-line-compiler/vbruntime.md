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
ms.openlocfilehash: 31b719fb7e43cdd6ac44424b359999410dd608a5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403049"
---
# <a name="-vbruntime"></a>-vbruntime
Especifica que el compilador debe compilar sin una referencia a la biblioteca de tiempo de ejecución de Visual Basic o con una referencia a una biblioteca de tiempo de ejecución específica.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a>Argumentos  
 \-  
 Se compila sin una referencia a la biblioteca en tiempo de ejecución de Visual Basic.  
  
 \+  
 Se compila con una referencia a la biblioteca en tiempo de ejecución de Visual Basic predeterminada.  
  
 \*  
 Se compila sin una referencia a la biblioteca en tiempo de ejecución de Visual Basic y se inserta la funcionalidad básica de esa biblioteca en el ensamblado.  
  
 `path`  
 Se compila con una referencia a la biblioteca especificada (DLL).  
  
## <a name="remarks"></a>Comentarios  
 La opción de compilación `-vbruntime` permite especificar que el compilador debe compilar sin una referencia a la biblioteca de tiempo de ejecución de Visual Basic. Si se compila sin una referencia a la biblioteca en tiempo de ejecución de Visual Basic, los errores o las advertencias se registran en construcciones de lenguaje o código que generan una llamada a una aplicación auxiliar en tiempo de ejecución de Visual Basic (una *aplicación auxiliar en tiempo de ejecución de Visual Basic* es una función definida en Microsoft.VisualBasic.dll a la que se llama en tiempo de ejecución para ejecutar una semántica de lenguaje específica).  
  
 La opción `-vbruntime+` produce el mismo comportamiento que sucede cuando no se especifica ningún modificador `-vbruntime`. Puede usar la opción `-vbruntime+` para invalidar modificadores `-vbruntime` anteriores.  
  
 La mayoría de los objetos de tipo `My` no están disponibles cuando se usan las opciones `-vbruntime-` o `-vbruntime:path`.  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a>Inserción de funcionalidad básica en tiempo de ejecución de Visual Basic  
 La opción `-vbruntime*` permite compilar sin una referencia a una biblioteca en tiempo de ejecución. En su lugar, la funcionalidad básica de la biblioteca en tiempo de ejecución de Visual Basic se inserta en el ensamblado del usuario. Esta opción se puede usar si la aplicación se ejecuta en plataformas que no contienen el tiempo de ejecución de Visual Basic.  
  
 Se insertan los siguientes miembros de tiempo de ejecución:  
  
- Clase <xref:Microsoft.VisualBasic.CompilerServices.Conversions>  
  
- Método <xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29>  
  
- Método <xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29>  
  
- Método <xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29>  
  
- Constante <xref:Microsoft.VisualBasic.Constants.vbBack>  
  
- Constante <xref:Microsoft.VisualBasic.Constants.vbCr>  
  
- Constante <xref:Microsoft.VisualBasic.Constants.vbCrLf>  
  
- Constante <xref:Microsoft.VisualBasic.Constants.vbFormFeed>  
  
- Constante <xref:Microsoft.VisualBasic.Constants.vbLf>  
  
- Constante <xref:Microsoft.VisualBasic.Constants.vbNewLine>  
  
- Constante <xref:Microsoft.VisualBasic.Constants.vbNullChar>  
  
- Constante <xref:Microsoft.VisualBasic.Constants.vbNullString>  
  
- Constante <xref:Microsoft.VisualBasic.Constants.vbTab>  
  
- Constante <xref:Microsoft.VisualBasic.Constants.vbVerticalTab>  
  
- Algunos objetos del tipo `My`  
  
 Si se compila con la opción `-vbruntime*` y el código hace referencia a un miembro de la biblioteca en tiempo de ejecución de Visual Basic que no tiene insertada la funcionalidad básica, el compilador devuelve un error que indica que el miembro no está disponible.  
  
## <a name="referencing-a-specified-library"></a>Referencia a una biblioteca especificada  
 El argumento `path` se puede usar para compilar con una referencia a una biblioteca en tiempo de ejecución personalizada, en lugar de a la biblioteca en tiempo de ejecución de Visual Basic predeterminada.  
  
 Si el valor del argumento `path` es una ruta de acceso completa a un archivo DLL, el compilador usará ese archivo como la biblioteca en tiempo de ejecución. Si el valor del argumento `path` no es una ruta de acceso completa a un archivo DLL, el compilador de Visual Basic buscará primero el archivo DLL identificado en la carpeta actual. Después, buscará en la ruta de acceso que se haya especificado, usando para ello la opción de compilador [-sdkpath](sdkpath.md). Si no se usa la opción de compilador `-sdkpath`, el compilador buscará el archivo DLL identificado en la carpeta de .NET Framework (`%systemroot%\Microsoft.NET\Framework\versionNumber`).  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se muestra cómo usar la opción `-vbruntime` para compilar con una referencia a una biblioteca personalizada.  
  
```console
vbc -vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a>Vea también

- [Visual Basic Core: nuevo modo de compilación en Visual Studio 2010 SP1](https://devblogs.microsoft.com/vbteam/vb-core-new-compilation-mode-in-visual-studio-2010-sp1/)
- [Compilador de línea de comandos de Visual Basic](index.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
- [-sdkpath](sdkpath.md)
