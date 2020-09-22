---
title: Los métodos no compartidos no pueden controlar los eventos de variables WithEvents compartidas
ms.date: 07/20/2015
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
ms.openlocfilehash: d519463e036de215143efad5be3745484ac17d82
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874293"
---
# <a name="events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a>Los métodos no compartidos no pueden controlar los eventos de variables WithEvents compartidas

Una variable declarada con el `Shared` modificador es una variable compartida. Una variable compartida identifica exactamente una ubicación de almacenamiento. Una variable declarada con el `WithEvents` modificador valida que el tipo al que pertenece la variable controla el conjunto de eventos que genera la variable. Cuando se asigna un valor a la variable, la propiedad creada por la `WithEvents` declaración desenlaza cualquier controlador de eventos existente y enlaza el nuevo controlador de eventos a través del `Add` método.  
  
 **Identificador de error:** BC30594  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Declare el controlador de eventos `Shared` .  
  
## <a name="see-also"></a>Consulte también

- [Compartido](../modifiers/shared.md)
- [WithEvents](../modifiers/withevents.md)
