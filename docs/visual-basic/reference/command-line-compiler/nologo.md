---
title: "/nologo (Visual Basic) | Microsoft Docs"
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
  - "/nologo (opción del compilador) [Visual Basic]"
  - "titulares, suprimir inicio"
  - "nologo (opción del compilador) [Visual Basic]"
  - "-nologo (opción del compilador) [Visual Basic]"
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# /nologo (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Suprime la presentación del aviso de copyright y los mensajes de información durante la compilación.  
  
## Sintaxis  
  
```  
/nologo  
```  
  
## Comentarios  
 Si especifica `/nologo`, el compilador no mostrará un aviso de copyright.  De forma predeterminada, `/nologo` se encuentra desactivado.  
  
> [!NOTE]
>  La opción `/nologo` no está disponible en el entorno de desarrollo de Visual Studio; sólo está disponible cuando se compila desde la línea de comandos.  
  
## Ejemplo  
 La siguiente línea compila `T2.vb` sin mostrar un aviso de copyright.  
  
```  
vbc /nologo t2.vb  
```  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)