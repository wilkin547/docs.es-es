---
title: "/nowin32manifest (Visual Basic) | Microsoft Docs"
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
  - "/nowin32manifest (opción del compilador) [Visual Basic]"
  - "nowin32manifest (opción del compilador) [Visual Basic]"
  - "-nowin32manifest (opción del compilador) [Visual Basic]"
ms.assetid: c0528aae-83b3-4425-99f0-19448e9843e3
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# /nowin32manifest (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Indica al compilador que no incruste ningún manifiesto de aplicación en el archivo ejecutable.  
  
## Sintaxis  
  
```  
/nowin32manifest  
```  
  
## Comentarios  
 Cuando se usa esta opción, la aplicación se someterá a la virtualización en Windows Vista, a menos que se proporcione un manifiesto de aplicación en un archivo de recursos Win32 o durante un paso de compilación posterior.  Para obtener más información sobre la virtualización, vea [Implementación de ClickOnce en Windows Vista](/visual-studio/deployment/clickonce-deployment-on-windows-vista).  
  
 Para obtener más información sobre la creación de manifiestos, vea [\/win32manifest](../../../visual-basic/reference/command-line-compiler/win32manifest.md).  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Aplicación \(Página, Diseñador de proyectos\) \(Visual Basic\)](/visual-studio/ide/reference/application-page-project-designer-visual-basic)