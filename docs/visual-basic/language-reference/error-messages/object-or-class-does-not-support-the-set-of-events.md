---
title: El objeto o la clase no admite el conjunto de eventos
ms.date: 07/20/2015
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
ms.openlocfilehash: c5e8b8de3477147fc3174cdbee401c89753004ad
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159955"
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a>El objeto o la clase no admite el conjunto de eventos

Ha intentado usar una `WithEvents` variable con un componente que no puede funcionar como un origen de eventos para el conjunto de eventos especificado. Por ejemplo, desea recibir los eventos de un objeto y, a continuación, crear otro objeto que sea `Implements` el primer objeto. Aunque podría pensar que podría recibir los eventos del objeto implementado, este no es siempre el caso. `Implements` solo implementa una interfaz para los métodos y las propiedades. `WithEvents` no se admite para Private `UserControls` , porque la información de tipo necesaria para generar `ObjectEvent` no está disponible en tiempo de ejecución.

## <a name="to-correct-this-error"></a>Para corregir este error

- No se pueden recibir eventos para un componente que no tiene eventos de origen.

## <a name="see-also"></a>Vea también

- [WithEvents](../modifiers/withevents.md)
- [Implements (Instrucción)](../statements/implements-statement.md)
