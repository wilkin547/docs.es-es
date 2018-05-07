---
title: Estructura &#39; &lt;structurename&gt; &#39; debe contener al menos una variable miembro de instancia o declaración de evento de al menos una instancia no esté marcada como &#39;personalizada&#39;
ms.date: 07/20/2015
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords:
- BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
ms.openlocfilehash: 85a4babc808e274a99f2c9faf08a02abf8aa4e93
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="structure-39ltstructurenamegt39-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-39custom39"></a>Estructura &#39; &lt;structurename&gt; &#39; debe contener al menos una variable miembro de instancia o declaración de evento de al menos una instancia no esté marcada como &#39;personalizada&#39;
Una definición de estructura no incluye las variables no compartidas o eventos no personalizados no compartidos.  
  
 Cada estructura debe tener una variable o un evento que se aplica a cada instancia concreta (no compartida) en lugar de a todas las instancias colectivamente ([Shared](../../../visual-basic/language-reference/modifiers/shared.md)). Procedimientos, propiedades y constantes no compartidos no cumplen este requisito. Además, si no hay ninguna variable no compartida y un solo evento no compartido, ese evento no puede ser un `Custom` eventos.  
  
 **Id. de error:** BC30941  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Definir al menos una variable o evento que no es `Shared`. Si define un solo evento, debe ser no personalizados, así como no compartido.  
  
## <a name="see-also"></a>Vea también  
 [Estructuras](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Declarar una estructura](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md)
