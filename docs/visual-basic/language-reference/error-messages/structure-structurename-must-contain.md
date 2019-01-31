---
title: La estructura '<structurename>' debe contener al menos una variable miembro de instancia o una declaración de evento de instancia que no esté marcada como 'Custom'
ms.date: 07/20/2015
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords:
- BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
ms.openlocfilehash: a8a85f4f089de9be6f2ecadac05256b30d3014b0
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55267461"
---
# <a name="structure-structurename-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-custom"></a>Estructura '\<structurename >' debe contener al menos una variable miembro de instancia o declaración de evento de al menos una instancia no esté marcada como 'Custom'
Una definición de estructura no incluye las variables no compartidas o eventos no personalizados no compartidos.  
  
 Cada estructura debe tener una variable o un evento que se aplica a cada instancia concreta (no compartida) en lugar de a todas las instancias colectivamente ([Shared](../../../visual-basic/language-reference/modifiers/shared.md)). Procedimientos, propiedades y constantes no compartidas no cumplen este requisito. Además, si no hay ninguna variable no compartida y un solo evento no compartido, ese evento no puede ser un `Custom` eventos.  
  
 **Identificador de error:** BC30941  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Definir al menos una variable o evento que no es `Shared`. Si define un solo evento, debe ser compartidas, así como no compartidos.  
  
## <a name="see-also"></a>Vea también
- [Estructuras](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Cómo: Declarar una estructura](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md)
