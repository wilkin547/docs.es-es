---
description: "Más información sobre: BC30941: la estructura ' <structurename> ' debe contener al menos una variable miembro de instancia o una declaración de evento de instancia que no esté marcada como ' Custom '"
title: La estructura '<structurename>' debe contener al menos una variable miembro de instancia o una declaración de evento de instancia que no esté marcada como 'Custom'
ms.date: 07/20/2015
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords:
- BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
ms.openlocfilehash: 08596997decd9d739ac95ad3e4191cb126b3efb3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99641452"
---
# <a name="bc30941-structure-structurename-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-custom"></a>BC30941: la estructura ' \<structurename> ' debe contener al menos una variable miembro de instancia o una declaración de evento de instancia que no esté marcada como ' Custom '

Una definición de estructura no incluye variables no compartidas ni eventos no personalizados no compartidos.

 Cada estructura debe tener una variable o un evento que se aplique a cada instancia específica (no compartida) en lugar de a todas las instancias colectivas ([compartidas](../modifiers/shared.md)). Las constantes, propiedades y procedimientos no compartidos no satisfacen este requisito. Además, si no hay ninguna variable no compartida y solo un evento no compartido, ese evento no puede ser un `Custom` evento.

 **Identificador de error:** BC30941

## <a name="to-correct-this-error"></a>Para corregir este error

- Defina al menos una variable o un evento que no sea `Shared` . Si solo se define un evento, debe ser no personalizado, así como no compartido.

## <a name="see-also"></a>Vea también

- [Estructuras](../../programming-guide/language-features/data-types/structures.md)
- [Procedimiento Declaración de estructuras](../../programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Structure (Instrucción)](../statements/structure-statement.md)
