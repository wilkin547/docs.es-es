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
ms.openlocfilehash: 34d6b94f31336e3e99b8ca981a9c4899e5a3d912
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875527"
---
# <a name="assembly-visual-basic"></a>Assembly (Visual Basic)

Especifica que un atributo al principio de un archivo de código fuente se aplica a todo el ensamblado.  
  
## <a name="remarks"></a>Comentarios  

 Muchos atributos pertenecen a un elemento de programación individual, como una clase o una propiedad. Este atributo se aplica asociando el bloque de atributos, entre corchetes angulares ( `< >` ), directamente a la instrucción de declaración.  
  
 Si un atributo pertenece no solo al elemento siguiente, sino a todo el ensamblado, coloca el bloque de atributos al principio del archivo de código fuente e identifica el atributo con la `Assembly` palabra clave. Si se aplica al módulo de ensamblado actual, se usa la palabra clave [Module](module-keyword.md) .  
  
 También puede aplicar un atributo a un ensamblado en el archivo AssemblyInfo. VB, en cuyo caso no es necesario usar un bloque de atributos en el archivo de código fuente principal.  
  
## <a name="see-also"></a>Consulte también

- [Destina \<keyword>](module-keyword.md)
- [Información general de atributos](../../programming-guide/concepts/attributes/index.md)
