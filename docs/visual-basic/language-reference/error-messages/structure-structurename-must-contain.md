---
title: Estructura &#39; &lt;structurename&gt; &#39; debe contener al menos una variable miembro de instancia o declaración de evento de al menos una instancia no esté marcada como &#39;personalizado&#39;
ms.date: 07/20/2015
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords:
- BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
ms.openlocfilehash: d8c654c212a459d40c6cf20cd62c3e0fcda8511b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54603786"
---
# <a name="structure-39ltstructurenamegt39-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-39custom39"></a>Estructura &#39; &lt;structurename&gt; &#39; debe contener al menos una variable miembro de instancia o declaración de evento de al menos una instancia no esté marcada como &#39;personalizado&#39;
Una definición de estructura no incluye las variables no compartidas o eventos no personalizados no compartidos.  
  
 Cada estructura debe tener una variable o un evento que se aplica a cada instancia concreta (no compartida) en lugar de a todas las instancias colectivamente ([Shared](../../../visual-basic/language-reference/modifiers/shared.md)). Procedimientos, propiedades y constantes no compartidas no cumplen este requisito. Además, si no hay ninguna variable no compartida y un solo evento no compartido, ese evento no puede ser un `Custom` eventos.  
  
 **Identificador de error:** BC30941  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Definir al menos una variable o evento que no es `Shared`. Si define un solo evento, debe ser compartidas, así como no compartidos.  
  
## <a name="see-also"></a>Vea también
- [Estructuras](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Cómo: Declarar una estructura](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md)
