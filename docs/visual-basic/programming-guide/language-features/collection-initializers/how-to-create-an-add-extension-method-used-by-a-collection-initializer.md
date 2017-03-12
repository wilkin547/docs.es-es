---
title: "C&#243;mo: Crear un m&#233;todo de extensi&#243;n Add usado por un inicializador de colecci&#243;n (Visual Basic) | Microsoft Docs"
ms.custom: ""
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
  - "inicializadores de colección [Visual Basic]"
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# C&#243;mo: Crear un m&#233;todo de extensi&#243;n Add usado por un inicializador de colecci&#243;n (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Al usar un inicializador de colección para crear una colección, el compilador de Visual Basic busca un método `Add` del tipo de colección en el que los parámetros del método `Add` coinciden con los tipos de valores del inicializador de colección.  Este método `Add` se usa para rellenar la colección con los valores del inicializador de colección.  
  
 Si no existe ningún método `Add` coincidente y no puede modificar el código de la colección, puede agregar un método de extensión denominado `Add` que toma los parámetros requeridos por el inicializador de colección.  Esta es la operación que debe realizar normalmente al usar inicializadores de colección para las colecciones genéricas.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo agregar un método de extensión al tipo <xref:System.Collections.Generic.List%601> genérico a fin de poder usar un inicializador de colección para agregar objetos del tipo `Employee`.  El método de extensión permite usar la sintaxis del inicializador de colección abreviada.  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/visualbasic/how-to-create-an-add-ext_1.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/visualbasic/how-to-create-an-add-ext_2.vb)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](../../../../visual-basic/programming-guide/language-features/collection-initializers/codesnippet/visualbasic/how-to-create-an-add-ext_3.vb)]  
  
## Vea también  
 [Inicializadores de colección](../../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)   
 [Cómo: Crear una colección usada por un inicializador de colección](../../../../visual-basic/programming-guide/language-features/collection-initializers/how-to-create-a-collection-used-by-a-collection-initializer.md)