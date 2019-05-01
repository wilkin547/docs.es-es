---
title: "'<keyword>' sólo es válida en un método de instancia"
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: 5ff82b932f9bea4c7fd087651e34277ef94bc27c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946645"
---
# <a name="keyword-is-valid-only-within-an-instance-method"></a>'\<palabra clave >' es válido solo dentro de un método de instancia
El `Me`, `MyClass`, y `MyBase` palabras clave que hacen referencia a instancias de clase específica. No se pueden utilizar dentro de un compartido `Function` o `Sub` procedimiento.  
  
 **Identificador de error:** BC30043  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Quite la palabra clave del procedimiento o quite la `Shared` palabra clave de la declaración de procedimiento.  
  
## <a name="see-also"></a>Vea también

- [Asignación de variables de objeto](../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Me, My, MyBase y MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Fundamentos de la herencia](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
