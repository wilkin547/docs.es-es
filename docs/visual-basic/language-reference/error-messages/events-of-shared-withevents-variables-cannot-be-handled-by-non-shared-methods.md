---
description: 'Más información sobre: BC30594: los eventos de variables WithEvents compartidas no se pueden controlar mediante métodos no compartidos'
title: Los métodos no compartidos no pueden controlar los eventos de variables WithEvents compartidas
ms.date: 07/20/2015
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
ms.openlocfilehash: f9e8bf6e0d365c4ee747deb6be0e809904d87117
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796423"
---
# <a name="bc30594-events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a>BC30594: los métodos no compartidos no pueden controlar los eventos de variables WithEvents compartidas

Una variable declarada con el `Shared` modificador es una variable compartida. Una variable compartida identifica exactamente una ubicación de almacenamiento. Una variable declarada con el `WithEvents` modificador valida que el tipo al que pertenece la variable controla el conjunto de eventos que genera la variable. Cuando se asigna un valor a la variable, la propiedad creada por la `WithEvents` declaración desenlaza cualquier controlador de eventos existente y enlaza el nuevo controlador de eventos a través del `Add` método.

 **Identificador de error:** BC30594

## <a name="to-correct-this-error"></a>Para corregir este error

- Declare el controlador de eventos `Shared` .

## <a name="see-also"></a>Vea también

- [Compartido](../modifiers/shared.md)
- [WithEvents](../modifiers/withevents.md)
