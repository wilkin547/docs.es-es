---
title: "/quiet | Microsoft Docs"
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
  - "/quiet"
  - "quiet"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/quiet (opción del compilador) [Visual Basic]"
  - "quiet (opción del compilador) [Visual Basic]"
  - "-quiet (opción del compilador) [Visual Basic]"
ms.assetid: 5d77fa23-4c50-4708-8535-649912b098e8
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /quiet
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Evita que el compilador muestre código de errores y advertencias relacionados con la sintaxis.  
  
## Sintaxis  
  
```  
/quiet  
```  
  
## Comentarios  
 De forma predeterminada, `/quiet` se encuentra desactivado.  Cuando el compilador notifica un error o una advertencia relacionados con la sintaxis, también muestra la línea de código fuente que lo originó.  Para las aplicaciones que analizan el resultado del compilador, puede ser más conveniente que el compilador sólo incluya en los resultados el texto del diagnóstico.  
  
 En el siguiente ejemplo, cuando se compila `Module1` sin la opción `/quiet`, se produce un error que incluye código fuente.  
  
```  
Module Module1  
    Sub Main()  
        x()  
    End Sub  
End Module  
```  
  
 Resultado:  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
 `x`  
  
 `~`  
  
 Si se compila con la opción `/quiet`, el compilador sólo muestra lo siguiente:  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
> [!NOTE]
>  La opción `/quiet` no está disponible en el entorno de desarrollo de Visual Studio; sólo está disponible cuando se compila desde la línea de comandos.  
  
## Ejemplo  
 La siguiente línea compila `T2.vb` sin mostrar el código de los diagnósticos de error relacionados con la sintaxis:  
  
```  
vbc /quiet t2.vb  
```  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)