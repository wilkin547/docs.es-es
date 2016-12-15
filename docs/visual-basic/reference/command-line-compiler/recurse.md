---
title: "/recurse | Microsoft Docs"
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
  - "/recurse (opción del compilador) [Visual Basic]"
  - "recurse (opción del compilador) [Visual Basic]"
  - "-recurse (opción del compilador) [Visual Basic]"
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /recurse
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Compila los archivos de código fuente de todos los subdirectorios del directorio especificado o del directorio del proyecto.  
  
## Sintaxis  
  
```  
/recurse:[dir\]file  
```  
  
## Argumentos  
 `dir`  
 Opcional.  Directorio en el que se desea iniciar la búsqueda.  Si no se especifica, la búsqueda empieza en el directorio del proyecto.  
  
 `file`  
 Obligatorio.  Los archivos que se van a buscar.  Se permiten caracteres comodín.  
  
## Comentarios  
 El nombre de archivo se puede especificar con caracteres comodín de modo que se compilen todos los archivos del directorio del proyecto que cumplan la especificación sin tener que utilizar `/recurse`.  Si no se especifica el nombre del archivo de salida, el compilador utilizará el nombre del primer archivo de entrada.  Éste será, normalmente, el primer archivo de la lista de archivos compilados ordenada alfabéticamente.  Por ello, es mejor especificar un archivo de salida mediante la opción `/out`.  
  
> [!NOTE]
>  La opción `/recurse` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.  
  
## Ejemplo  
 La siguiente línea compila todos los archivos de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] del directorio actual.  
  
```  
vbc *.vb  
```  
  
 La línea siguiente compila todos los archivos de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] del directorio `Test\ABC` y de cualquier subdirectorio, y después genera `Test.ABC.dll`.  
  
```  
vbc /target:library /out:Test.ABC.dll /recurse:Test\ABC\*.vb  
```  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/out](../../../visual-basic/reference/command-line-compiler/out.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)