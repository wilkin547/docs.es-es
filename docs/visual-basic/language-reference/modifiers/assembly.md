---
title: Ensamblado (Visual Basic) | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Assembly
- vb.AssemblyAttribute
- Assembly
dev_langs:
- VB
helpviewer_keywords:
- Assembly modifier
- Assembly keyword
- attribute blocks, Assembly keyword
ms.assetid: 925e7471-3bdf-4b51-bb93-cbcfc6efc52f
caps.latest.revision: 15
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b496b96360ff891554ab71ba2b3227b2dabbc416
ms.lasthandoff: 03/13/2017

---
# <a name="assembly-visual-basic"></a>Assembly (Visual Basic)
Especifica que un atributo al principio de un archivo de código fuente se aplica a todo el ensamblado.  
  
## <a name="remarks"></a>Comentarios  
 Muchos atributos pertenecen a un elemento de programación individual, como una clase o propiedad. Aplicar dicho atributo adjuntando el bloque de atributos entre corchetes angulares (`< >`), directamente a la instrucción de declaración.  
  
 Si un atributo se aplica no sólo al siguiente elemento sino a todo el ensamblado, coloque el bloque de atributos al principio del archivo de origen e identifique el atributo con el `Assembly` (palabra clave). Si se aplica al módulo de ensamblado actual, utiliza la [módulo](../../../visual-basic/language-reference/modifiers/module-keyword.md) (palabra clave).  
  
 También puede aplicar un atributo a un ensamblado en el archivo AssemblyInfo.vb, en cuyo caso no es necesario utilizar un bloque de atributos en el archivo de código fuente principal.  
  
## <a name="see-also"></a>Vea también  
 [Módulo \<palabra clave >](../../../visual-basic/language-reference/modifiers/module-keyword.md)   
 [Información general de atributos](../../../visual-basic/programming-guide/concepts/attributes/index.md)


