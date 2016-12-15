---
title: "El objeto o la clase no admite el conjunto de eventos | Microsoft Docs"
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
  - "vbrID459"
dev_langs: 
  - "VB"
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# El objeto o la clase no admite el conjunto de eventos
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Ha intentado utilizar una variable `WithEvents` con un componente que no puede funcionar como origen de eventos del conjunto de eventos especificado.  Por ejemplo, deseaba recibir eventos de un objeto y luego crear otro objeto que implementase con `Implements` el primer objeto.  Aunque crea que puede recibir los eventos del objeto implementado, esto no siempre es así.  `Implements` solo implementa una interfaz para los métodos y propiedades.  `WithEvents` no se admite en`UserControls` privados porque el tipo de información necesaria para generar `ObjectEvent` no está disponible en tiempo de ejecución.  
  
### Para corregir este error  
  
1.  No puede recibir eventos para un componente que no origina eventos.  
  
## Vea también  
 [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)   
 [Implements \(Instrucción\)](../../../visual-basic/language-reference/statements/implements-statement.md)