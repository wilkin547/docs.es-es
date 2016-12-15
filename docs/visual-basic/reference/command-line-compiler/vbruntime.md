---
title: "/vbruntime | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbruntime"
  - "/vbruntime"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/vbruntime (opción del compilador) [Visual Basic]"
  - "vbruntime (opción del compilador) [Visual Basic]"
  - "-vbruntime (opción del compilador) [Visual Basic]"
ms.assetid: 1aa0239e-511a-4c29-957d-fd72877b350a
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /vbruntime
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Especifica que el compilador debe compilar sin una referencia a la biblioteca en tiempo de ejecución de Visual Basic o con una referencia a una biblioteca en tiempo de ejecución concreta.  
  
## Sintaxis  
  
```  
/vbruntime:{ - | + | * | path }  
```  
  
## Argumentos  
 \-  
 Compilar sin una referencia a la biblioteca en tiempo de ejecución de Visual Basic.  
  
 \+  
 Compilar con una referencia a la biblioteca en tiempo de ejecución de Visual Basic predeterminada.  
  
 \*  
 Compile sin una referencia a la biblioteca de tiempo de ejecución de Visual Basic, e inserte la funcionalidad principal de la biblioteca de tiempo de ejecución de Visual Basic en el ensamblado.  
  
 `path`  
 Compilar con una referencia a la biblioteca \(DLL\) especificada.  
  
## Comentarios  
 La opción del compilador `/vbruntime` permite especificar que el compilador debería compilar sin una referencia a la biblioteca en tiempo de ejecución de Visual Basic.  Si compila sin una referencia a la biblioteca en tiempo de ejecución de Visual Basic, los errores o advertencias se registran en construcciones de código o lenguaje que generan una llamada a una aplicación auxiliar de Visual Basic en tiempo de ejecución.  \(Una *aplicación auxiliar de Visual Basic en tiempo de ejecución* es una función definida en Microsoft.VisualBasic.dll a la que se llama en tiempo de ejecución para ejecutar una semántica concreta del lenguaje.\)  
  
 La opción `/vbruntime+` genera el mismo comportamiento que se produce si no se especifica ningún modificador de `/vbruntime`.  Puede utilizar la opción `/vbruntime+` para invalidar los modificadores de `/vbruntime` anteriores.  
  
 La mayoría de los objetos de tipo de `My` no están disponibles cuando se utiliza `/vbruntime-` o las opciones de `vbruntime:``path` .  
  
## Incrustar la funcionalidad básica de tiempo de ejecución de Visual Basic  
 La opción `/vbruntime*` permite compilar sin ninguna referencia a una biblioteca en tiempo de ejecución.  En cambio, la funcionalidad principal de la biblioteca de tiempo de ejecución de Visual Basic está incrustada en el ensamblado de usuario.  Puede utilizar esta opción si la aplicación se ejecuta en plataformas que no contengan el Visual Basic.  
  
 Los siguientes miembros de runtime están incrustados:  
  
-   Clase <xref:Microsoft.VisualBasic.CompilerServices.Conversions>  
  
-   Método <xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29>  
  
-   Método <xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29>  
  
-   Método <xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29>  
  
-   Constante de <xref:Microsoft.VisualBasic.Constants.vbBack>  
  
-   Constante de <xref:Microsoft.VisualBasic.Constants.vbCr>  
  
-   Constante de <xref:Microsoft.VisualBasic.Constants.vbCrLf>  
  
-   Constante de <xref:Microsoft.VisualBasic.Constants.vbFormFeed>  
  
-   Constante de <xref:Microsoft.VisualBasic.Constants.vbLf>  
  
-   Constante de <xref:Microsoft.VisualBasic.Constants.vbNewLine>  
  
-   Constante de <xref:Microsoft.VisualBasic.Constants.vbNullChar>  
  
-   Constante de <xref:Microsoft.VisualBasic.Constants.vbNullString>  
  
-   Constante de <xref:Microsoft.VisualBasic.Constants.vbTab>  
  
-   Constante de <xref:Microsoft.VisualBasic.Constants.vbVerticalTab>  
  
-   Algunos objetos de tipo de `My`  
  
 Si se compila con la opción `/vbruntime*` y el código hace referencia a un miembro de la biblioteca de tiempo de ejecución de Visual Basic que no está insertado con la funcionalidad básica, el compilador devuelve un error que indica que el miembro no está disponible.  
  
## Hacer referencia a una biblioteca especificada  
 También puede utilizar el argumento `path` para compilar con una referencia a una biblioteca en tiempo de ejecución personalizada, no a la biblioteca en tiempo de ejecución de Visual Basic predeterminada.  
  
 Si el valor para el argumento `path` es una ruta de acceso completa a una DLL, el compilador usará ese archivo como biblioteca en tiempo de ejecución.  Si el valor para el argumento `path` no es una ruta de acceso completa a una DLL, el compilador de Visual Basic buscará primero la DLL identificada en la carpeta actual.  A continuación, buscará en la ruta de acceso especificada mediante la opción del compilador [\/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md).  Si no se utiliza la opción del compilador `/sdkpath`, el compilador buscará la DLL identificada en la carpeta .NET Framework \(`%systemroot%\Microsoft.NET\Framework\versionNumber`\).  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo usar la opción `/vbruntime` para compilar con una referencia a una biblioteca personalizada.  
  
```  
vbc /vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## Vea también  
 [Visual Basic Core – New compilation mode in Visual Studio 2010 SP1](http://blogs.msdn.com/b/vbteam/archive/2011/01/10/vb-core-new-compilation-mode-in-visual-studio-2010-sp1.aspx)   
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [\/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)