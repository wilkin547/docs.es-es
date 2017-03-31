---
title: alias externo (Referencia de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- alias_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- extern alias keyword [C#]
- aliases [C#], extern keyword
- aliases, extern keyword
ms.assetid: f487bf4f-c943-4fca-851b-e540c83d9027
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2bda6b652b56c50883700fe5a2a81189dbcb0d2d
ms.lasthandoff: 03/13/2017

---
# <a name="extern-alias-c-reference"></a>alias externo (Referencia de C#)
Es posible que deba hacer referencia a dos versiones de ensamblados que tienen los mismos nombres de tipo completos. Por ejemplo, es posible que tenga que usar dos o más versiones de un ensamblado en la misma aplicación. Mediante el uso de un alias de ensamblado externo, los espacios de nombres de cada ensamblado pueden ajustarse en espacios de nombres de nivel de raíz denominados por el alias, lo que permite que se usen en el mismo archivo.  
  
> [!NOTE]
>  La palabra clave [extern](../../../csharp/language-reference/keywords/extern.md) también se usa como un modificador de método, y declara un método escrito en código no administrado.  
  
 Para hacer referencia a dos ensamblados con los mismos nombres de tipo completos, debe especificarse un alias en un símbolo del sistema, como sigue:  
  
 `/r:GridV1=grid.dll`  
  
 `/r:GridV2=grid20.dll`  
  
 Esto crea los alias externos `GridV1` y `GridV2`. Para usar estos alias desde dentro de un programa, se hace referencia a ellos mediante la palabra clave `extern`. Por ejemplo:  
  
 `extern alias GridV1;`  
  
 `extern alias GridV2;`  
  
 Cada declaración de alias externo introduce un espacio de nombres de nivel de raíz adicional que es semejante al espacio de nombres global (pero que no se encuentra en su interior). Por tanto, se puede hacer referencia a los tipos de cada ensamblado sin ambigüedad mediante su nombre completo, con raíz en el alias de espacio de nombres adecuado.  
  
 En el ejemplo anterior, `GridV1::Grid` sería el control de cuadrícula de `grid.dll`, y `GridV2::Grid` sería el control de cuadrícula de `grid20.dll`.  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [Palabras clave del espacio de nombres](../../../csharp/language-reference/keywords/namespace-keywords.md)   
 [Operador ::](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)   
 [/reference (Opciones del compilador de C#)](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)
