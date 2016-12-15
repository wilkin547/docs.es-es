---
title: "&#39;&lt;nombreDeFunci&#243;n&gt;&#39; no se declar&#243; (Error del compilador de Smart Device/Visual Basic) | Microsoft Docs"
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
  - "bc30766"
  - "vbc30766"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30766"
ms.assetid: 13918600-6087-40d7-8134-32aa9d3bfda4
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;nombreDeFunci&#243;n&gt;&#39; no se declar&#243; (Error del compilador de Smart Device/Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

\<`functionname`\> no se ha declarado.  La funcionalidad de E\/S de archivos está disponible normalmente en el espacio de nombres `Microsoft.VisualBasic`, pero la versión de destino de .NET Compact Framework no lo admite.  
  
 **Identificador de error:** BC30766  
  
### Para corregir este error  
  
-   Realice operaciones de archivo con funciones definidas en el espacio de nombres `System.IO`.  
  
## Vea también  
 <xref:System.IO>   
 [Acceso a archivos con Visual Basic](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)