---
title: "C&#243;mo: Crear una colecci&#243;n usada por un inicializador de colecci&#243;n (Visual Basic) | Microsoft Docs"
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
  - "inicializadores de colección [Visual Basic]"
ms.assetid: c858db10-424d-47e0-92cd-e08087cc5ebc
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Crear una colecci&#243;n usada por un inicializador de colecci&#243;n (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Al usar un inicializador de colección para crear una colección, el compilador de Visual Basic busca un método `Add` del tipo de colección en el que los parámetros del método `Add` coinciden con los tipos de valores del inicializador de colección.  Este método `Add` se usa para rellenar la colección con los valores del inicializador de colección.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra una colección `OrderCollection` que contiene un método `Add` público que un inicializador de colección puede usar para agregar objetos de tipo `Order`.  El método `Add` permite usar la sintaxis del inicializador de colección abreviada.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#4](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_1.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#1](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_2.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#2](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_3.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo2#3](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/VisualBasic/how-to-create-a-collection-used-by-a-collection-initializer_4.vb)]  
  
## Vea también  
 [Inicializadores de colección](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)   
 [Cómo: Crear un método de extensión Add usado por un inicializador de colección](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-an-add-extension-method-used-by-a-collection-initializer.md)