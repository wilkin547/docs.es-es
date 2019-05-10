---
title: No se pudieron inferir los argumentos de tipo a partir del delegado
ms.date: 07/20/2015
f1_keywords:
- bc36564
- vbc36564
helpviewer_keywords:
- BC36564
ms.assetid: 21312807-e1cd-4ac1-ae1c-c28a9c25164d
ms.openlocfilehash: 3e2902da7fe9d8fa2194db681df098f0148cbbaf
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64584258"
---
# <a name="type-arguments-could-not-be-inferred-from-the-delegate"></a>No se pudieron inferir los argumentos de tipo a partir del delegado
Una instrucción de asignación usa `AddressOf` para asignar la dirección de un procedimiento genérico a un delegado, pero no proporciona ningún argumento de tipo al procedimiento genérico.  
  
 Normalmente, cuando se invoca un tipo genérico, se facilita un argumento de tipo para cada parámetro de tipo definido por el tipo genérico. Si no se facilita ningún argumento de tipo, el compilador intenta inferir los tipos que se deben pasar a los parámetros de tipo. Si el contexto no proporciona suficiente información para que el compilador infiera los tipos, se genera un error.  
  
 **Identificador de error:** BC36564  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Especifique los argumentos de tipo para el procedimiento genérico en la expresión `AddressOf` .  
  
## <a name="see-also"></a>Vea también

- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [AddressOf (operador)](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Generic Procedures in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)
- [Lista de tipos](../../../visual-basic/language-reference/statements/type-list.md)
- [Métodos de extensión](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
