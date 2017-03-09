---
title: "/noconfig | Microsoft Docs"
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
  - "/noconfig (opción del compilador) [Visual Basic]"
  - "noconfig (opción del compilador) [Visual Basic]"
  - "-noconfig (opción del compilador) [Visual Basic]"
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# /noconfig
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica que el compilador no debe hacer referencia automáticamente a los ensamblados de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] de uso habitual ni importar los espacios de nombres `System` y `Microsoft.VisualBasic`.  
  
## Sintaxis  
  
```  
/noconfig  
```  
  
## Comentarios  
 La opción `/noconfig` indica al compilador que no compile con el archivo Vbc.rsp, que está ubicado en el mismo directorio que el archivo Vbc.exe.  El archivo Vbc.rsp hace referencia a los ensamblados de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] de uso habitual e importa los espacios de nombres `System` y `Microsoft.VisualBasic`.  El compilador hace referencia implícitamente al ensamblado de System.dll a menos que se especifique la opción `/nostdlib`.  Esta opción indica al compilador que no compile con Vbc.rsp ni que haga referencias automáticas al ensamblado de System.dll.  
  
> [!NOTE]
>  Siempre se hace referencia a los ensamblados Mscorlib.dll y Microsoft.VisualBasic.dll.  
  
 Puede modificar el archivo Vbc.rsp para especificar opciones adicionales de compilador que deben incluirse en todas las compilaciones de Vbc.exe \(excepto cuando especifica la opción `/noconfig`\).  Para obtener más información, vea [@ \(especificar archivo de respuesta\)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).  
  
 El compilador procesa en último lugar las opciones que se pasan al comando `vbc`.  Por lo tanto, cualquier opción de la línea de comandos reemplaza la configuración de la misma opción en el archivo Vbc.rsp.  
  
> [!NOTE]
>  La opción `/noconfig` no está disponible en el entorno de desarrollo de Visual Studio; sólo está disponible cuando se compila desde la línea de comandos.  
  
## Vea también  
 [\/nostdlib](../../../visual-basic/reference/command-line-compiler/nostdlib.md)   
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [@ \(especificar archivo de respuesta\)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)   
 [\/reference](../../../visual-basic/reference/command-line-compiler/reference.md)