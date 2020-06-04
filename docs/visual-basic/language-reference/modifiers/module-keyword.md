---
title: Destina<keyword>
ms.date: 07/20/2015
f1_keywords:
- vb.ModuleAttribute
helpviewer_keywords:
- Module keyword [Visual Basic]
- Module modifier
- attribute blocks, Module keyword
ms.assetid: d971b940-05ab-4d56-8485-e3b8a661906b
ms.openlocfilehash: 0cb009c22dada7b92956e113d33505923a92f2b3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84362429"
---
# <a name="module-keyword-visual-basic"></a>Module \<keyword> (Visual Basic)
Especifica que un atributo al principio de un archivo de código fuente se aplica al módulo de ensamblado actual.  
  
## <a name="remarks"></a>Observaciones  
 Muchos atributos pertenecen a un elemento de programación individual, como una clase o una propiedad. Este atributo se aplica asociando el bloque de atributos, entre corchetes angulares ( `< >` ), directamente a la instrucción de declaración.  
  
 Si un atributo pertenece no solo al siguiente elemento, sino al módulo de ensamblado actual, coloca el bloque de atributos al principio del archivo de código fuente e identifica el atributo con la `Module` palabra clave. Si se aplica a todo el ensamblado, se utiliza la palabra clave [Assembly](assembly.md) .  
  
 El `Module` modificador no es lo mismo que la [instrucción del módulo](../statements/module-statement.md).  
  
## <a name="see-also"></a>Consulte también

- [Ensamblado](assembly.md)
- [Module (Instrucción)](../statements/module-statement.md)
- [Información general de atributos](../../programming-guide/concepts/attributes/index.md)
