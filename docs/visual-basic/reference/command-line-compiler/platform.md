---
title: "/platform (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/platform (opción del compilador) [Visual Basic]"
  - "platform (opción del compilador) [Visual Basic]"
  - "-platform (opción del compilador) [Visual Basic]"
ms.assetid: f9bc61e6-e854-4ae1-87b9-d6244de23fd1
caps.latest.revision: 34
caps.handback.revision: 34
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /platform (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Especifica qué versión de la plataforma de Common Language Runtime \(CLR\) puede ejecutar el archivo de salida.  
  
## Sintaxis  
  
```  
/platform:{ x86 | x64 | Itanium | arm | anycpu | anycpu32bitpreferred }  
```  
  
## Argumentos  
  
|||  
|-|-|  
|Término|Definición|  
|`x86`|Compila el ensamblado de forma que el CLR de 32 bits compatible con x86 pueda ejecutarlo.|  
|`x64`|Compila el ensamblado de forma que el CLR de 64 bits pueda ejecutarlo en equipos compatibles con el conjunto de instrucciones AMD64 o EM64T.|  
|`Itanium`|Compila el ensamblado de forma que el CLR de 64 bits pueda ejecutarlo en un equipo con un procesador Itanium.|  
|`arm`|Compila el ensamblado de forma que pueda ejecutarse en un equipo con un procesador ARM \(Advanced RISC Machine\).|  
|`anycpu`|Compila el ensamblado de forma que pueda ejecutarse en cualquier plataforma.  La aplicación se ejecutará como una aplicación de 32 bits en versiones de 32 bits de Windows, y como una aplicación de 64 bits en versiones de 64 bits de Windows.  Esta marca es el valor predeterminado.|  
|`anycpu32bitpreferred`|Compila el ensamblado de forma que pueda ejecutarse en cualquier plataforma.  La aplicación se ejecutará como una aplicación de 32 bits en versiones de 32 bits y de 64 bits de Windows.  Esta marca solo es válida para ejecutables \(.EXE\) y requiere [!INCLUDE[net_v45](../../../csharp/language-reference/compiler-options/includes/net_v45_md.md)].|  
  
## Comentarios  
 Use la opción `/platform` para especificar el tipo de procesador de destino del archivo de salida.  
  
 En general, los ensamblados de .NET Framework escritos en Visual Basic se ejecutarán de la misma manera independientemente de la plataforma.  Sin embargo, en algunos casos se comportan de forma diferente en distintas plataformas.  Estos casos comunes son:  
  
-   Estructuras que contengan miembros cuyo tamaño varía según la plataforma, como cualquier tipo de puntero.  
  
-   Aritmética de punteros que incluya tamaños constantes.  
  
-   Invocación incorrecta de la plataforma o declaraciones COM que utilicen `Integer` para los controladores en lugar de <xref:System.IntPtr>.  
  
-   Conversión de <xref:System.IntPtr> a `Integer`.  
  
-   Uso de invocación de plataforma o interoperabilidad COM con componentes que no existen en todas las plataformas.  
  
 La opción **\/platform** mitigará algunos problemas si ha realizado suposiciones acerca de la arquitectura en la que se ejecutará el código.  De manera específica:  
  
-   Si decide que el destino sea una plataforma de 64 bits pero la aplicación se ejecuta en un equipo de 32 bits, el mensaje de error aparece mucho antes y se centra más bien en el problema que en el error que aparece sin utilizar este modificador.  
  
-   Si establece la marca `x86` en la opción y posteriormente la aplicación se ejecuta en un equipo de 64 bits, la aplicación se ejecutará en el subsistema WOW, en lugar de ejecutarse de forma nativa.  
  
 En un sistema operativo de Windows de 64 bits:  
  
-   Los ensamblados compilados con `/platform:x86` se ejecutarán en el CLR de 32 bits que se ejecuta en WOW64.  
  
-   Los ejecutables compilados con `/platform:anycpu` se ejecutarán en el CLR de 64 bits.  
  
-   Un archivo DLL compilado con `/platform:anycpu` se ejecutará en el mismo CLR que el proceso en el que se cargó.  
  
-   Los archivos ejecutables que se compilan con `/platform:anycpu32bitpreferred` se ejecutarán en el CLR de 32 bits.  
  
 Para obtener más información sobre cómo desarrollar una aplicación para que se ejecute en una versión de 64 bits de Windows, consulte [Aplicaciones de 64 bits](../Topic/64-bit%20Applications.md).  
  
### Cómo establecer \/platform en el IDE de Visual Studio  
  
1.  En el **Explorador de soluciones**, elija el proyecto, abra el menú **Proyecto** y, a continuación, haga clic en **Propiedades**.  
  
     Para obtener más información, vea [NIB: Managing Project Properties with the Project Designer](http://msdn.microsoft.com/es-es/983f3c18-832f-4666-afec-74b716ff3e0e).  
  
2.  En la ficha **Compilar**, active o desactive la casilla **Preferencia de 32 bits**, o bien elija un valor en la lista **CPU de destino**.  
  
     Para obtener más información, vea [Página Compilación, Diseñador de proyectos \(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic).  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar la opción `/platform` del compilador.  
  
```  
vbc /platform:x86 myFile.vb  
```  
  
## Vea también  
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)   
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)