---
title: Assembly (Visual Basic)
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
ms.openlocfilehash: 819fa9cf1bd25e9426fb1e75925a269fcf7a71cd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58819260"
---
# <a name="assembly-visual-basic"></a>Assembly (Visual Basic)
Especifica que un atributo al principio de un archivo de código fuente se aplica a todo el ensamblado.  
  
## <a name="remarks"></a>Comentarios  
 Muchos atributos pertenecen a un elemento de programación individual, como una clase o propiedad. Aplicar este atributo adjuntando el bloque de atributos dentro de corchetes angulares (`< >`), directamente a la instrucción de declaración.  
  
 Si un atributo se aplica no solo al siguiente elemento, sino a todo el ensamblado, coloque el bloque de atributos al principio del archivo de origen e identificar el atributo con el `Assembly` palabra clave. Si se aplica al módulo de ensamblado actual, usa el [módulo](../../../visual-basic/language-reference/modifiers/module-keyword.md) palabra clave.  
  
 También puede aplicar un atributo a un ensamblado en el archivo AssemblyInfo.vb, en cuyo caso no es necesario usar un bloque de atributos en el archivo de código fuente principal.  
  
## <a name="see-also"></a>Vea también

- [Module \<keyword>](../../../visual-basic/language-reference/modifiers/module-keyword.md)
- [Información general de atributos](../../../visual-basic/programming-guide/concepts/attributes/index.md)
