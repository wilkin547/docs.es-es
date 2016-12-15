---
title: "El constructor &#39;&lt;nombre&gt;&#39; no se puede llamar a s&#237; mismo | Microsoft Docs"
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
  - "bc30298"
  - "vbc30298"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30298"
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# El constructor &#39;&lt;nombre&gt;&#39; no se puede llamar a s&#237; mismo
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Un procedimiento `Sub New` de una clase o estructura se llama a sí mismo.  
  
 El propósito de un constructor es inicializar una instancia de una clase o estructura cuando se crea por primera vez.  Una clase o estructura puede tener varios constructores, siempre que todos ellos tengan listas de parámetros diferentes.  Permiten a un constructor llamar a otro constructor para realizar su funcionalidad además de la suya propia.  Pero no tiene sentido que un constructor se llame a sí mismo, y de hecho provocaría una recursividad infinita si estuviera permitida.  
  
 **Identificador de error:** BC30298  
  
### Para corregir este error  
  
1.  Compruebe la lista de parámetros del constructor al que se está llamando.  Debería ser distinta de la del constructor que realiza la llamada.  
  
2.  Si no tiene previsto llamar a un constructor diferente, quite la llamada `Sub New` por completo.  
  
## Vea también  
 [Duración de los objetos: cómo se crean y destruyen](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)