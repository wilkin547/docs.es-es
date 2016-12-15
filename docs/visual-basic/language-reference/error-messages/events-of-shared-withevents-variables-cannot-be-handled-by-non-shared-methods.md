---
title: "Los m&#233;todos no compartidos no pueden controlar los eventos de variables WithEvents compartidas | Microsoft Docs"
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
  - "bc30594"
  - "vbc30594"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30594"
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Los m&#233;todos no compartidos no pueden controlar los eventos de variables WithEvents compartidas
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Una variable declarada con el modificador `Shared` es una variable compartida.  Una variable compartida identifica exactamente una ubicación de almacenamiento.  Una variable declarada con el modificador `WithEvents` afirma que el tipo al que pertenece la variable controla el conjunto de eventos que provoca.  Cuando se asigna un valor a la variable, la propiedad creada mediante la declaración `WithEvents` elimina el enlace de cualquier controlador de eventos existente y establece un enlace con el nuevo controlador de eventos a través del método `Add`.  
  
 **Identificador de error:** BC30594  
  
### Para corregir este error  
  
-   Declare el controlador de eventos como `Shared`.  
  
## Vea también  
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)   
 [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)