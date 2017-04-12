---
title: /vbruntime | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbruntime
- /vbruntime
dev_langs:
- VB
helpviewer_keywords:
- vbruntime compiler option [Visual Basic]
- -vbruntime compiler option [Visual Basic]
- /vbruntime compiler option [Visual Basic]
ms.assetid: 1aa0239e-511a-4c29-957d-fd72877b350a
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 455f950988b540b74874ce38882c59059f77ea8f
ms.lasthandoff: 03/13/2017

---
# <a name="vbruntime"></a>/vbruntime
Especifica que el compilador debe compilar sin una referencia a la biblioteca de tiempo de ejecución de Visual Basic o con una referencia a una biblioteca de tiempo de ejecución específica.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/vbruntime:{ - | + | * | path }  
```  
  
## <a name="arguments"></a>Argumentos  
 \-  
 Compilar sin una referencia a la biblioteca de tiempo de ejecución de Visual Basic.  
  
 \+  
 Compilar con una referencia a la biblioteca en tiempo de ejecución de Visual Basic predeterminada.  
  
 \*  
 Compilar sin una referencia a la biblioteca de tiempo de ejecución de Visual Basic e incrustar funcionalidad de la biblioteca en tiempo de ejecución de Visual Basic en el ensamblado.  
  
 `path`  
 Compilar con una referencia a la biblioteca especificada (DLL).  
  
## <a name="remarks"></a>Comentarios  
 El `/vbruntime` opción del compilador permite especificar que el compilador debe compilar sin una referencia a la biblioteca de tiempo de ejecución de Visual Basic. Si compila sin una referencia a la biblioteca de tiempo de ejecución de Visual Basic, errores o advertencias se registran en construcciones de código o lenguaje que generan una llamada a una aplicación auxiliar de tiempo de ejecución de Visual Basic. (Un *aplicación auxiliar de tiempo de ejecución de Visual Basic* es una función definida en Microsoft.VisualBasic.dll a la que se llama en tiempo de ejecución para ejecutar una semántica concreta del lenguaje.)  
  
 El `/vbruntime+` opción produce el mismo comportamiento que se produce si no hay ningún `/vbruntime` ha especificado el modificador. Puede usar el `/vbruntime+` opción para invalidar anterior `/vbruntime` conmutadores.  
  
 La mayoría de los objetos de la `My` tipo no están disponibles cuando se utiliza la `/vbruntime-` o `vbruntime:``path` opciones.  
  
## <a name="embedding-visual-basic-runtime-core-functionality"></a>Incrustación de funcionalidad en tiempo de ejecución de Visual Basic  
 El `/vbruntime*` opción permite compilar sin una referencia a una biblioteca en tiempo de ejecución. En su lugar, la funcionalidad básica de la biblioteca en tiempo de ejecución de Visual Basic se incrusta en el ensamblado del usuario. Puede utilizar esta opción si la aplicación se ejecuta en plataformas que no contienen el tiempo de ejecución de Visual Basic.  
  
 Se incrustan los siguientes miembros en tiempo de ejecución:  
  
-   <xref:Microsoft.VisualBasic.CompilerServices.Conversions>(clase)</xref:Microsoft.VisualBasic.CompilerServices.Conversions>  
  
-   <xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29>(método)</xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29>  
  
-   <xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29>(método)</xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29>  
  
-   <xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29>(método)</xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbBack>(constante)</xref:Microsoft.VisualBasic.Constants.vbBack>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbCr>(constante)</xref:Microsoft.VisualBasic.Constants.vbCr>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbCrLf>(constante)</xref:Microsoft.VisualBasic.Constants.vbCrLf>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbFormFeed>(constante)</xref:Microsoft.VisualBasic.Constants.vbFormFeed>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbLf>(constante)</xref:Microsoft.VisualBasic.Constants.vbLf>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNewLine>(constante)</xref:Microsoft.VisualBasic.Constants.vbNewLine>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNullChar>(constante)</xref:Microsoft.VisualBasic.Constants.vbNullChar>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNullString>(constante)</xref:Microsoft.VisualBasic.Constants.vbNullString>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbTab>(constante)</xref:Microsoft.VisualBasic.Constants.vbTab>  
  
-   <xref:Microsoft.VisualBasic.Constants.vbVerticalTab>(constante)</xref:Microsoft.VisualBasic.Constants.vbVerticalTab>  
  
-   Algunos objetos de la `My` tipo  
  
 Si se compila utilizando el `/vbruntime*` opción y el código hace referencia a un miembro de la biblioteca de tiempo de ejecución de Visual Basic que no están integrados con la funcionalidad básica, el compilador devuelve un error que indica que el miembro no está disponible.  
  
## <a name="referencing-a-specified-library"></a>Hacer referencia a una biblioteca especificada  
 Puede usar el `path` argumento para compilar con una referencia a una biblioteca de tiempo de ejecución personalizado en lugar de la biblioteca en tiempo de ejecución de Visual Basic predeterminada.  
  
 Si el valor de la `path` argumento es una ruta de acceso completa a un archivo DLL, el compilador usará ese archivo como biblioteca en tiempo de ejecución. Si el valor de la `path` argumento no es una ruta de acceso completa a un archivo DLL, el compilador de Visual Basic buscará la DLL identificada en la carpeta actual en primer lugar. A continuación, buscará en la ruta de acceso que ha especificado mediante el uso de la [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) opción del compilador. Si el `/sdkpath` no se utiliza la opción del compilador, el compilador buscará la DLL identificada en la carpeta .NET Framework (`%systemroot%\Microsoft.NET\Framework\versionNumber`).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar el `/vbruntime` opción para compilar con una referencia a una biblioteca personalizada.  
  
```  
vbc /vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## <a name="see-also"></a>Vea también  
 [Núcleo de Visual Basic: nuevo modo de compilación en Visual Studio 2010 SP1](http://blogs.msdn.com/b/vbteam/archive/2011/01/10/vb-core-new-compilation-mode-in-visual-studio-2010-sp1.aspx)   
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)
