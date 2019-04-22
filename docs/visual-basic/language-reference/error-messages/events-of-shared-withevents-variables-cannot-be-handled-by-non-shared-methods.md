---
title: Los métodos no compartidos no pueden controlar los eventos de variables WithEvents compartidas
ms.date: 07/20/2015
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
ms.openlocfilehash: 2b32043898986b3e3e68fab18c5f907843d7691c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58838656"
---
# <a name="events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a>Los métodos no compartidos no pueden controlar los eventos de variables WithEvents compartidas
Una variable declarada con el `Shared` modificador es una variable compartida. Una variable compartida identifica exactamente una ubicación de almacenamiento. Una variable declarada con el `WithEvents` modificador afirma que el tipo al que pertenece la variable controla el conjunto de eventos que provoca la variable. Cuando se asigna un valor a la variable, la propiedad creada por el `WithEvents` declaración modo se desenlaza cualquier controlador de eventos existente y enlaza el nuevo controlador de eventos a través de la `Add` método.  
  
 **Identificador de error:** BC30594  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Declare el controlador de eventos `Shared`.  
  
## <a name="see-also"></a>Vea también

- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
- [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md)
