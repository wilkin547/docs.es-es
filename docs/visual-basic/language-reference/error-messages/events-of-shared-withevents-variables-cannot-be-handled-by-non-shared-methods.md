---
title: Los métodos no compartidos no pueden controlar los eventos de variables WithEvents compartidas
ms.date: 07/20/2015
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
ms.openlocfilehash: d6067c75835ecd14f1dd796c20ae3f29f456e541
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64642939"
---
# <a name="events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a>Los métodos no compartidos no pueden controlar los eventos de variables WithEvents compartidas
Una variable declarada con el `Shared` modificador es una variable compartida. Una variable compartida identifica exactamente una ubicación de almacenamiento. Una variable declarada con el `WithEvents` modificador afirma que el tipo al que pertenece la variable controla el conjunto de eventos que provoca la variable. Cuando se asigna un valor a la variable, la propiedad creada por el `WithEvents` declaración modo se desenlaza cualquier controlador de eventos existente y enlaza el nuevo controlador de eventos a través de la `Add` método.  
  
 **Identificador de error:** BC30594  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Declare el controlador de eventos `Shared`.  
  
## <a name="see-also"></a>Vea también

- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
- [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)
