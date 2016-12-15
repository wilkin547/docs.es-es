---
title: "&lt;tipo1&gt;&#39;&lt;nombreDeTipo&gt;&#39; debe implementar &#39;&lt;nombreDeMiembro&gt;&#39; para la interfaz &#39;&lt;nombreDeInterfaz&gt;&#39; | Microsoft Docs"
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
  - "vbc30154"
  - "bc30154"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30154"
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;tipo1&gt;&#39;&lt;nombreDeTipo&gt;&#39; debe implementar &#39;&lt;nombreDeMiembro&gt;&#39; para la interfaz &#39;&lt;nombreDeInterfaz&gt;&#39;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

'\<nombreDeTipo\>' debe implementar '\<nombreDeMiembro\>' para la interfaz '\<nombreDeInterfaz\>'.La propiedad de implementación debe tener especificadores 'ReadOnly'\/'WriteOnly' que coincidan.  
  
 Una clase o estructura intenta implementar una interfaz, pero no implementa un procedimiento, propiedad o evento definido por la interfaz.  Deben implementarse todos los miembros de la interfaz.  
  
 **Identificador de error:** BC30154  
  
### Para corregir este error  
  
1.  Declare un miembro con el mismo nombre y firma que los definidos en la interfaz.  Asegúrese de incluir al menos la instrucción `End Function`, `End Sub`, o `End Property`.  
  
2.  Agregue una cláusula `Implements` al final de la instrucción `Function`, `Sub`, `Property` o `Event`.  Por ejemplo:  
  
    ```  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3.  Al implementar una propiedad, asegúrese de que se utiliza `ReadOnly` o `WriteOnly` de la misma forma que en la definición de interfaz.  
  
4.  Al implementar una propiedad, declare los procedimientos `Get` y `Set` según corresponda.  
  
## Vea también  
 [Implements \(Instrucción\)](../../../visual-basic/language-reference/statements/implements-statement.md)   
 [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)