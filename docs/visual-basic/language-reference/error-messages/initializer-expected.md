---
title: "Se esperaba un inicializador | Microsoft Docs"
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
  - "vbc30996"
  - "bc30996"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30996"
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Se esperaba un inicializador
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Ha intentado declarar una instancia de una clase utilizando un inicializador de objeto en el que la lista de inicializaciones está vacía, como se muestra en el ejemplo siguiente.  
  
 `' Not valid.`  
  
 `' Dim aStudent As New Student With {}`  
  
 Se debe inicializar al menos un campo o propiedad en la lista de inicializadores, como se muestra en el ejemplo siguiente.  
  
 `Dim aStudent As New Student With {.year = "Senior"}`  
  
 **Id. de error:** BC30996  
  
### Para corregir este error  
  
1.  Inicialice al menos un campo o propiedad en el inicializador o no utilice un inicializador de objeto.  
  
## Vea también  
 [Inicializadores de objeto: Tipos con nombre y anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)   
 [Cómo: Declarar un objeto usando un inicializador de objeto](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)