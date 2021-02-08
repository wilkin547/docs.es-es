---
description: "Más información sobre: BC30043: ' <keyword> ' solo es válido dentro de un método de instancia"
title: "'<keyword>' sólo es válida en un método de instancia"
ms.date: 07/20/2015
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
ms.openlocfilehash: 0bca2df44e096da016c9cb0c2031a8ef6faeb2b0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795981"
---
# <a name="bc30043-keyword-is-valid-only-within-an-instance-method"></a>BC30043: ' \<keyword> ' solo es válido en un método de instancia

Las `Me` `MyClass` `MyBase` palabras clave, y hacen referencia a instancias de clase específicas. No se pueden usar dentro de un `Function` procedimiento compartido o `Sub` .

*Identificador de error:** BC30043

## <a name="to-correct-this-error"></a>Para corregir este error

- Quite la palabra clave del procedimiento o quite la `Shared` palabra clave de la declaración de procedimiento.

## <a name="see-also"></a>Vea también

- [Asignación de variables de objeto](../../programming-guide/language-features/variables/object-variable-assignment.md)
- [Me, My, MyBase y MyClass](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Fundamentos de la herencia](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
