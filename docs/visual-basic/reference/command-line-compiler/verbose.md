---
title: "/verbose | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "/verbose (opción del compilador) [Visual Basic]"
  - "verbose (opción del compilador) [Visual Basic]"
  - "-verbose (opción del compilador) [Visual Basic]"
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /verbose
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Hace que el compilador muestre información de estado y mensajes de error.  
  
## Sintaxis  
  
```  
/verbose[+ | -]  
```  
  
## Argumentos  
 `+` &#124; `-`  
 Opcional.  Especificar `/verbose` equivale a especificar `/verbose+`, que indica al compilador que emita mensajes detallados.  El valor predeterminado de esta opción es `/verbose-`.  
  
## Comentarios  
 La opción  `/verbose` muestra información sobre el número total de errores emitidos por el compilador, notifica qué ensamblados está cargando un módulo y muestra qué archivos se están compilando actualmente.  
  
> [!NOTE]
>  La opción `/verbose` no está disponible en el entorno de desarrollo de Visual Studio; sólo está disponible cuando se compila desde la línea de comandos.  
  
## Ejemplo  
 La siguiente línea compila `In.vb` y hace que el compilador muestre información de estado detallada.  
  
```  
vbc /verbose in.vb  
```  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)