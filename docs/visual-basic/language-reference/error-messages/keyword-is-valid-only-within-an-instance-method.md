---
title: '&#39;&lt;palabra clave&gt; &#39; es válido solo dentro de un método de instancia'
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: a464a059aa2d13e3472b9770960384b6be398092
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54595947"
---
# <a name="39ltkeywordgt39-is-valid-only-within-an-instance-method"></a>&#39;&lt;palabra clave&gt; &#39; es válido solo dentro de un método de instancia
El `Me`, `MyClass`, y `MyBase` palabras clave que hacen referencia a instancias de clase específica. No se pueden utilizar dentro de un compartido `Function` o `Sub` procedimiento.  
  
 **Identificador de error:** BC30043  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Quite la palabra clave del procedimiento o quite la `Shared` palabra clave de la declaración de procedimiento.  
  
## <a name="see-also"></a>Vea también
- [Asignación de variables de objeto](../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Me, My, MyBase y MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Fundamentos de la herencia](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
