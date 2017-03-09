---
title: "/utf8output (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/utf8output (opción del compilador) [Visual Basic]"
  - "utf8output (opción del compilador) [Visual Basic]"
  - "-utf8output (opción del compilador) [Visual Basic]"
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# /utf8output (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Muestra los resultados del compilador mediante la codificación UTF\-8.  
  
## Sintaxis  
  
```  
/utf8output[+ | -]  
```  
  
## Argumentos  
 `+` &#124; `-`  
 Opcional.  El valor predeterminado de esta opción es `/utf8output-`, que significa que el resultado del compilador no utiliza la codificación UTF\-8.  Especificar sólo `/utf8output` equivale a especificar `/utf8output+`.  
  
## Comentarios  
 En algunas configuraciones internacionales, los resultados del compilador no se pueden mostrar correctamente en la consola.  En estas situaciones, utilice `/utf8output` y redirija los resultados del compilador a un archivo.  
  
> [!NOTE]
>  La opción `/utf8output` no está disponible en el entorno de desarrollo de Visual Studio; sólo está disponible cuando se compila desde la línea de comandos.  
  
## Ejemplo  
 La línea siguiente compila `In.vb` y hace que el compilador muestre los resultados con la codificación UTF\-8.  
  
```  
vbc /utf8output in.vb  
```  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)