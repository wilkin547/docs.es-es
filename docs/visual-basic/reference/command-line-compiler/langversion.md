---
title: "/langversion (Visual Basic) | Microsoft Docs"
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
  - "/langversion (opción del compilador) [Visual Basic]"
  - "langversion (opción del compilador) [Visual Basic]"
  - "-langversion (opción del compilador) [Visual Basic]"
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /langversion (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Hace que el compilador acepte solamente la sintaxis incluida en la versión de lenguaje especificada de Visual Basic.  
  
## Sintaxis  
  
```  
/langversion:version  
```  
  
## Argumentos  
 `version`  
 Obligatorio.  Versión de lenguaje que se va a usar durante la compilación.  Los valores aceptados son `9`, `9.0`, `10` y `10.0`.  
  
## Comentarios  
 La opción `/langversion` especifica la sintaxis que acepta el compilador.  Por ejemplo, si se especifica que la versión de lenguaje es 9.0, el compilador generará errores para la sintaxis que solo es válida en la versión 10.0 y posterior.  
  
 Puede usar esta opción al desarrollar aplicaciones destinadas a distintas versiones de .NET Framework.  Por ejemplo, si la aplicación de destino es .NET Framework 3.5, podría usar esta opción para asegurarse de que no se usa la sintaxis de la versión de lenguaje 10.0.  
  
 Solo puede establecer `/langversion` directamente mediante la línea de comandos.  Para obtener más información, vea [Elegir una versión específica de .NET Framework](/visual-studio/ide/targeting-a-specific-dotnet-framework-version).  
  
## Ejemplo  
 El código siguiente compila `sample.vb` para Visual Basic 9.0.  
  
```  
vbc /langversion:9.0 sample.vb  
```  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Elegir una versión específica de .NET Framework](/visual-studio/ide/targeting-a-specific-dotnet-framework-version)