---
title: "Error al cargar la biblioteca DLL (Visual Basic) | Microsoft Docs"
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
  - "vbrID48"
dev_langs: 
  - "VB"
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Error al cargar la biblioteca DLL (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Una biblioteca de vínculos dinámicos \(DLL\) es aquella especificada en la cláusula `Lib` de una instrucción `Declare`.  Las causas posibles de este error son:  
  
-   El archivo no es una DLL ejecutable.  
  
-   El archivo no es una DLL de Microsoft Windows.  
  
-   La DLL hace referencia a otra DLL que no está presente.  
  
-   La DLL o la DLL a la que se hace referencia no está en un directorio especificado en la ruta de acceso.  
  
### Para corregir este error  
  
-   Si el archivo es un texto de código fuente y, por lo tanto, no es una DLL ejecutable, debe compilarse y vincularse a una formato ejecutable de DLL.  
  
-   Si el archivo no es de tipo DLL de Microsoft Windows, obtenga el equivalente de Microsoft Windows.  
  
-   Si la DLL hace referencia a otra DLL que no está presente, obtenga la DLL a la que se hace referencia y póngala disponible.  
  
-   Si la DLL o la DLL a la que se hace referencia no está en el directorio especificado en la ruta de acceso, mueva la DLL al directorio al que se hace referencia.  
  
## Vea también  
 [Declare \(Instrucción\)](../../../visual-basic/language-reference/statements/declare-statement.md)