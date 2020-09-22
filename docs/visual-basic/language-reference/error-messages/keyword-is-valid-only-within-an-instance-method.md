---
title: "'<keyword>' sólo es válida en un método de instancia"
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: af436b8fd57ff0d2747c766a64af175760931009
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873905"
---
# <a name="keyword-is-valid-only-within-an-instance-method"></a>'\<keyword>' sólo es válida en un método de instancia

Las `Me` `MyClass` `MyBase` palabras clave, y hacen referencia a instancias de clase específicas. No se pueden usar dentro de un `Function` procedimiento compartido o `Sub` .  
  
 **Identificador de error:** BC30043  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Quite la palabra clave del procedimiento o quite la `Shared` palabra clave de la declaración de procedimiento.  
  
## <a name="see-also"></a>Consulte también

- [Asignación de variables de objeto](../../programming-guide/language-features/variables/object-variable-assignment.md)
- [Me, My, MyBase y MyClass](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Fundamentos de la herencia](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
