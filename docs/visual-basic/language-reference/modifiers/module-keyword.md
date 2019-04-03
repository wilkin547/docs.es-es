---
title: Module <keyword> (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ModuleAttribute
helpviewer_keywords:
- Module keyword [Visual Basic]
- Module modifier
- attribute blocks, Module keyword
ms.assetid: d971b940-05ab-4d56-8485-e3b8a661906b
ms.openlocfilehash: f6ded1184aedf1702f4b6e5eebb85709cf8e39f4
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814281"
---
# <a name="module-keyword-visual-basic"></a>Módulo \<palabra clave > (Visual Basic)
Especifica que un atributo al principio de un archivo de código fuente se aplica al módulo de ensamblado actual.  
  
## <a name="remarks"></a>Comentarios  
 Muchos atributos pertenecen a un elemento de programación individual, como una clase o propiedad. Aplicar este atributo adjuntando el bloque de atributos dentro de corchetes angulares (`< >`), directamente a la instrucción de declaración.  
  
 Si un atributo se aplica no solo para el elemento siguiente pero al módulo de ensamblado actual, coloque el bloque de atributos al principio del archivo de origen e identificar el atributo con el `Module` palabra clave. Si se aplica a todo el ensamblado, usa el [ensamblado](../../../visual-basic/language-reference/modifiers/assembly.md) palabra clave.  
  
 El `Module` modificador no es igual que el [Module (instrucción)](../../../visual-basic/language-reference/statements/module-statement.md).  
  
## <a name="see-also"></a>Vea también

- [Ensamblado](../../../visual-basic/language-reference/modifiers/assembly.md)
- [Module (instrucción)](../../../visual-basic/language-reference/statements/module-statement.md)
- [Información general de atributos](../../../visual-basic/programming-guide/concepts/attributes/index.md)
