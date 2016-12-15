---
title: "&#39;&lt;nombreDeM&#233;todo&gt;&#39; tiene varias definiciones con firmas id&#233;nticas | Microsoft Docs"
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
  - "vbc30269"
  - "bc30269"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30269"
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;nombreDeM&#233;todo&gt;&#39; tiene varias definiciones con firmas id&#233;nticas
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Una declaración de procedimiento `Function` o `Sub` usa el mismo nombre de procedimiento y lista de argumentos que una declaración anterior.  Una posible causa es el intento de sobrecargar el procedimiento original.  Los procedimientos sobrecargados deben tener listas de argumentos diferentes.  
  
 **Identificador de error:** BC30269  
  
### Para corregir este error  
  
-   Cambie el nombre de procedimiento o la lista de argumentos, o quite la declaración duplicada.  
  
## Vea también  
 [Referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Consideraciones sobre la sobrecarga de procedimientos](../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)