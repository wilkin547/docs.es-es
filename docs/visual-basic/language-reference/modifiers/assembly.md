---
description: 'Más información acerca de: Assembly (Visual Basic)'
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
ms.openlocfilehash: 60b8ce4ed2b8b5cb7deeabb702c33d1e561d765f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99701188"
---
# <a name="assembly-visual-basic"></a>Assembly (Visual Basic)

Especifica que un atributo al principio de un archivo de código fuente se aplica a todo el ensamblado.  
  
## <a name="remarks"></a>Observaciones  

 Muchos atributos pertenecen a un elemento de programación individual, como una clase o una propiedad. Este atributo se aplica asociando el bloque de atributos, entre corchetes angulares ( `< >` ), directamente a la instrucción de declaración.  
  
 Si un atributo pertenece no solo al elemento siguiente, sino a todo el ensamblado, coloca el bloque de atributos al principio del archivo de código fuente e identifica el atributo con la `Assembly` palabra clave. Si se aplica al módulo de ensamblado actual, se usa la palabra clave [Module](module-keyword.md) .  
  
 También puede aplicar un atributo a un ensamblado en el archivo AssemblyInfo. VB, en cuyo caso no es necesario usar un bloque de atributos en el archivo de código fuente principal.  
  
## <a name="see-also"></a>Vea también

- [Destina \<keyword>](module-keyword.md)
- [Información general de atributos](../../programming-guide/concepts/attributes/index.md)
