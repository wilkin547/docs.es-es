---
description: 'Más información acerca de: ParamArray (Visual Basic)'
title: ParamArray
ms.date: 07/20/2015
f1_keywords:
- vb.ParamArray
- ParamArray
helpviewer_keywords:
- ParamArray keyword [Visual Basic]
- ParamArray keyword [Visual Basic], syntax
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
ms.openlocfilehash: 064bad8a558308ee3361c11d07020e0e3bf40c13
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99730400"
---
# <a name="paramarray-visual-basic"></a>ParamArray (Visual Basic)

Especifica que un parámetro de procedimiento toma una matriz opcional de elementos del tipo especificado. `ParamArray` solo se puede usar en el último parámetro de una lista de parámetros.  
  
## <a name="remarks"></a>Observaciones  

 `ParamArray` permite pasar un número arbitrario de argumentos al procedimiento. Un `ParamArray` parámetro siempre se declara mediante [ByVal](byval.md).  
  
 Puede proporcionar uno o varios argumentos a un `ParamArray` parámetro pasando una matriz del tipo de datos adecuado, una lista separada por comas de valores o nada en absoluto. Para obtener más información, vea "llamar a ParamArray" en [matrices de parámetros](../../programming-guide/language-features/procedures/parameter-arrays.md).  
  
> [!IMPORTANT]
> Siempre que se trata de una matriz que puede ser indefinidamente grande, existe el riesgo de que se produzca una gran cantidad de capacidad interna de la aplicación. Si acepta una matriz de parámetros del código de llamada, debe probar su longitud y tomar las medidas adecuadas si es demasiado grande para la aplicación.  
  
 El modificador `ParamArray` se puede utilizar en los contextos siguientes:  
  
 [Declare Statement](../statements/declare-statement.md)  
  
 [Instrucción Function](../statements/function-statement.md)  
  
 [Property Statement](../statements/property-statement.md)  
  
 [Instrucción Sub](../statements/sub-statement.md)  
  
## <a name="see-also"></a>Vea también

- [Palabras clave](../keywords/index.md)
- [Matrices de parámetros](../../programming-guide/language-features/procedures/parameter-arrays.md)
