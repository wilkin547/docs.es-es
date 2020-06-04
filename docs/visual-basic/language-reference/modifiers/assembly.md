---
title: Ensamblado
ms.date: 07/20/2015
f1_keywords:
- vb.Assembly
- vb.AssemblyAttribute
- Assembly
helpviewer_keywords:
- Assembly modifier
- Assembly keyword [Visual Basic]
- attribute blocks, Assembly keyword
ms.assetid: 925e7471-3bdf-4b51-bb93-cbcfc6efc52f
ms.openlocfilehash: 7d313dee1015362bd0215ed98ab7e898312cfbcd
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84373165"
---
# <a name="assembly-visual-basic"></a>Assembly (Visual Basic)
Especifica que un atributo al principio de un archivo de código fuente se aplica a todo el ensamblado.  
  
## <a name="remarks"></a>Observaciones  
 Muchos atributos pertenecen a un elemento de programación individual, como una clase o una propiedad. Este atributo se aplica asociando el bloque de atributos, entre corchetes angulares ( `< >` ), directamente a la instrucción de declaración.  
  
 Si un atributo pertenece no solo al elemento siguiente, sino a todo el ensamblado, coloca el bloque de atributos al principio del archivo de código fuente e identifica el atributo con la `Assembly` palabra clave. Si se aplica al módulo de ensamblado actual, se usa la palabra clave [Module](module-keyword.md) .  
  
 También puede aplicar un atributo a un ensamblado en el archivo AssemblyInfo. VB, en cuyo caso no es necesario usar un bloque de atributos en el archivo de código fuente principal.  
  
## <a name="see-also"></a>Consulte también

- [Destina\<keyword>](module-keyword.md)
- [Información general de atributos](../../programming-guide/concepts/attributes/index.md)
