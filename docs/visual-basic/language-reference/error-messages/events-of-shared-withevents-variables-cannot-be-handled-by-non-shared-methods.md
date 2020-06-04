---
title: Los métodos no compartidos no pueden controlar los eventos de variables WithEvents compartidas
ms.date: 07/20/2015
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
ms.openlocfilehash: fc163c1069aa6f41766664e0fa5f5a9c34a1f73d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409574"
---
# <a name="events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a>Los métodos no compartidos no pueden controlar los eventos de variables WithEvents compartidas
Una variable declarada con el `Shared` modificador es una variable compartida. Una variable compartida identifica exactamente una ubicación de almacenamiento. Una variable declarada con el `WithEvents` modificador valida que el tipo al que pertenece la variable controla el conjunto de eventos que genera la variable. Cuando se asigna un valor a la variable, la propiedad creada por la `WithEvents` declaración desenlaza cualquier controlador de eventos existente y enlaza el nuevo controlador de eventos a través del `Add` método.  
  
 **Identificador de error:** BC30594  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Declare el controlador de eventos `Shared` .  
  
## <a name="see-also"></a>Consulte también

- [Compartido](../modifiers/shared.md)
- [WithEvents](../modifiers/withevents.md)
