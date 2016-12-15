---
title: "La estructura &#39;&lt;nombreDeEstructura&gt;&#39; debe contener al menos una variable miembro de instancia o una declaraci&#243;n de evento de instancia que no est&#233; marcada como &#39;Custom&#39; | Microsoft Docs"
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
  - "bc30941"
  - "vbc30941"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30941"
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# La estructura &#39;&lt;nombreDeEstructura&gt;&#39; debe contener al menos una variable miembro de instancia o una declaraci&#243;n de evento de instancia que no est&#233; marcada como &#39;Custom&#39;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Una definición de estructura no incluye ninguna variable no compartida o eventos no personalizados y no compartidos.  
  
 Cada estructura debe tener una variable o un evento que se aplica a cada instancia concreta \(no compartida\) en lugar de a todas las instancias colectivamente \([Shared](../../../visual-basic/language-reference/modifiers/shared.md)\).  Las constantes, propiedades y procedimientos no compartidos no satisfacen este requisito.  Además, si no hay ninguna variable no compartida y hay sólo un evento no compartido, este evento no puede ser un evento `Custom`.  
  
 **Identificador de error:** BC30941  
  
### Para corregir este error  
  
-   Defina al menos una variable o evento que no sea `Shared`.  Si define sólo un evento, debe ser no personalizado así como no compartido.  
  
## Vea también  
 [Estructuras](../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Cómo: Declarar una estructura](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)   
 [Structure \(Instrucción\)](../../../visual-basic/language-reference/statements/structure-statement.md)