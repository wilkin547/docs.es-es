---
description: 'Más información acerca de: module <keyword> (Visual Basic)'
title: Destina <keyword>
ms.date: 07/20/2015
f1_keywords:
- vb.ModuleAttribute
helpviewer_keywords:
- Module keyword [Visual Basic]
- Module modifier
- attribute blocks, Module keyword
ms.assetid: d971b940-05ab-4d56-8485-e3b8a661906b
ms.openlocfilehash: 1bd25b00b41f5da4fca535220fe4e1694c81baca
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99640698"
---
# <a name="module-keyword-visual-basic"></a>Module \<keyword> (Visual Basic)

Especifica que un atributo al principio de un archivo de código fuente se aplica al módulo de ensamblado actual.  
  
## <a name="remarks"></a>Observaciones  

 Muchos atributos pertenecen a un elemento de programación individual, como una clase o una propiedad. Este atributo se aplica asociando el bloque de atributos, entre corchetes angulares ( `< >` ), directamente a la instrucción de declaración.  
  
 Si un atributo pertenece no solo al siguiente elemento, sino al módulo de ensamblado actual, coloca el bloque de atributos al principio del archivo de código fuente e identifica el atributo con la `Module` palabra clave. Si se aplica a todo el ensamblado, se utiliza la palabra clave [Assembly](assembly.md) .  
  
 El `Module` modificador no es lo mismo que la [instrucción del módulo](../statements/module-statement.md).  
  
## <a name="see-also"></a>Vea también

- [Ensamblaje](assembly.md)
- [Module (Instrucción)](../statements/module-statement.md)
- [Información general de atributos](../../programming-guide/concepts/attributes/index.md)
