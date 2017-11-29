---
title: "Los métodos no compartidos no pueden controlar los eventos de variables WithEvents compartidas"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords: BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 53372927b88df3946583564492df42170f302739
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a>Los métodos no compartidos no pueden controlar los eventos de variables WithEvents compartidas
Una variable declarada con el `Shared` modificador es una variable compartida. Una variable compartida identifica exactamente una ubicación de almacenamiento. Una variable declarada con el `WithEvents` modificador afirma que el tipo al que pertenece la variable controla el conjunto de eventos que provoca la variable. Cuando se asigna un valor a la variable, la propiedad creado por el `WithEvents` declaración modo se desenlaza cualquier controlador de eventos existente y enlaza el nuevo controlador de eventos a través de la `Add` método.  
  
 **Id. de error:** BC30594  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Declare el controlador de eventos `Shared`.  
  
## <a name="see-also"></a>Vea también  
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)  
 [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)
