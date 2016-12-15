---
title: "/nostdlib (Visual Basic) | Microsoft Docs"
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
  - "/nostdlib (opción del compilador) [Visual Basic]"
  - "nostdlib (opción del compilador) [Visual Basic]"
  - "-nostdlib (opción del compilador) [Visual Basic]"
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /nostdlib (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Provoca que el compilador no haga referencia automáticamente a las bibliotecas estándar.  
  
## Sintaxis  
  
```  
/nostdlib  
```  
  
## Comentarios  
 La opción `/nostdlib` quita la referencia automática al ensamblado System.dll y evita que el compilador lea el archivo Vbc.rsp.  El archivo Vbc.rsp file \(que se encuentra en el mismo directorio que el archivo Vbc.exe\) hace referencia a los ensamblados de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] que se usan habitualmente e importa los espacios de nombres `System` y `Microsoft.VisualBasic`.  
  
> [!NOTE]
>  Siempre se hace referencia a los ensamblados Mscorlib.dll y Microsoft.VisualBasic.dll.  
  
> [!NOTE]
>  La opción `/nostdlib` no está disponible en el entorno de desarrollo de Visual Studio; sólo está disponible cuando se compila desde la línea de comandos.  
  
## Ejemplo  
 En el código siguiente se compila `T2.vb` sin hacer referencia a las bibliotecas estándar.  Debe establecer la constante de compilación condicional `_MYTYPE` en la cadena "Empty" para quitar el objeto `My`.  
  
```  
vbc /nostdlib /define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## Vea también  
 [\/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)   
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Personalizar los objetos que están disponibles en My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)