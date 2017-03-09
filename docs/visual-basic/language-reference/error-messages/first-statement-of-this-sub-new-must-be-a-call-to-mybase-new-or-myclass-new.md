---
title: "La primera instrucci&#243;n de este &#39;Sub New&#39; debe ser una llamada a &#39;MyBase.New&#39; o &#39;MyClass.New&#39; (constructor no accesible sin par&#225;metros) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30148"
  - "vbc30148"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30148"
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# La primera instrucci&#243;n de este &#39;Sub New&#39; debe ser una llamada a &#39;MyBase.New&#39; o &#39;MyClass.New&#39; (constructor no accesible sin par&#225;metros)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

La primera instrucción de este 'Sub New' debe ser una llamada a 'MyBase.New' o 'MyClass.New', porque la clase base '\<nombreBase\>' de '\<nombreDerivado\>' no tiene un 'Sub New' accesible que se pueda llamar sin argumentos.  
  
 En una clase derivada, cada constructor debe llamar a un constructor de la clase base \(`MyBase.New`\).  Si la clase base tiene un constructor sin parámetros que está accesible a todas las clases derivadas, se puede llamar automáticamente a `MyBase.New`.  En caso contrario, se debe llamar a un constructor de clase base sin parámetros, y esta operación no se puede realizar automáticamente.  En este caso, la primera instrucción de cada constructor de clase derivada debe llamar a un constructor con parámetros en la clase base, o llamar a otro constructor en la clase derivada que realice una llamada al constructor de clase base.  
  
 **Identificador de error:** BC30148  
  
### Para corregir este error  
  
-   Llame a `MyBase.New` indicando los parámetros requeridos o llame a un constructor del mismo nivel que realice esa llamada.  
  
     Por ejemplo, si la clase base tiene un constructor que se declara como `Public Sub New(ByVal index as Integer)`, la primera instrucción del constructor de la clase derivada puede ser `MyBase.New(100)`.  
  
## Vea también  
 [Fundamentos de la herencia](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)