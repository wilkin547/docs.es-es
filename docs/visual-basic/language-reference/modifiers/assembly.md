---
title: Assembly (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Assembly
- vb.AssemblyAttribute
- Assembly
helpviewer_keywords:
- Assembly modifier
- Assembly keyword [Visual Basic]
- attribute blocks, Assembly keyword
ms.assetid: 925e7471-3bdf-4b51-bb93-cbcfc6efc52f
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ef4434f0bc520abfc621567fc68e0b8bcfd6e381
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="assembly-visual-basic"></a>Assembly (Visual Basic)
Especifica que un atributo al principio de un archivo de código fuente se aplica a todo el ensamblado.  
  
## <a name="remarks"></a>Comentarios  
 Muchos atributos pertenecen a un elemento de programación individual, como una clase o propiedad. Se aplica un atributo de este tipo si se adjunta el bloque de atributos, entre corchetes angulares (`< >`), directamente a la instrucción de declaración.  
  
 Si un atributo se aplica no solo para el siguiente elemento sino a todo el ensamblado, sitúa el bloque de atributos al principio del archivo de origen e identifique el atributo con el `Assembly` palabra clave. Si se aplica al módulo de ensamblado actual, utilice la [módulo](../../../visual-basic/language-reference/modifiers/module-keyword.md) palabra clave.  
  
 También puede aplicar un atributo a un ensamblado en el archivo AssemblyInfo.vb, en cuyo caso no es necesario usar un bloque de atributos en el archivo de código fuente principal.  
  
## <a name="see-also"></a>Vea también  
 [Module \<keyword>](../../../visual-basic/language-reference/modifiers/module-keyword.md)  
 [Información general de atributos](../../../visual-basic/programming-guide/concepts/attributes/index.md)

