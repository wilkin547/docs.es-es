---
title: Los métodos no compartidos no pueden controlar los eventos de variables WithEvents compartidas
ms.date: 07/20/2015
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
ms.openlocfilehash: f61f4cd17b1bb3088117e0a0d91b186fd40db3b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33585176"
---
# <a name="events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a>Los métodos no compartidos no pueden controlar los eventos de variables WithEvents compartidas
Una variable declarada con el `Shared` modificador es una variable compartida. Una variable compartida identifica exactamente una ubicación de almacenamiento. Una variable declarada con el `WithEvents` modificador afirma que el tipo al que pertenece la variable controla el conjunto de eventos que provoca la variable. Cuando se asigna un valor a la variable, la propiedad creado por el `WithEvents` declaración modo se desenlaza cualquier controlador de eventos existente y enlaza el nuevo controlador de eventos a través de la `Add` método.  
  
 **Id. de error:** BC30594  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Declare el controlador de eventos `Shared`.  
  
## <a name="see-also"></a>Vea también  
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)  
 [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)
