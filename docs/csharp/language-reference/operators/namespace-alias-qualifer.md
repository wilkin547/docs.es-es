---
title: ':: (operador) (Referencia de C#) | Microsoft Docs'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ::_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- ':: operator [C#]'
- 'namespaces [C#], :: operator'
- namespace alias qualifier operator (::) [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
caps.latest.revision: 21
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 12a0265d430a5a110d8c73107a48b36e0ab15405
ms.contentlocale: es-es
ms.lasthandoff: 03/13/2017

---
# <a name="-operator-c-reference"></a>:: (operador) (Referencia de C#)
El calificador de alias de espacio de nombres (`::`) se usa para buscar identificadores. Siempre se coloca entre dos identificadores, como en este ejemplo:  
  
 [!code-cs[csRefOperators#27](../../../csharp/language-reference/operators/codesnippet/CSharp/namespace-alias-qualifer_1.cs)]  
  
## <a name="remarks"></a>Comentarios  
 El calificador de alias de espacio de nombres puede ser `global`. Este invoca una búsqueda del espacio de nombres global, en lugar de un espacio de nombres con alias.  
  
## <a name="for-more-information"></a>Para obtener más información  
 Para obtener un ejemplo de cómo usar el operador `::`, vea la siguiente sección:  
  
-   [Cómo: Utilizar el alias del espacio de nombres global](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)   
 [Palabras clave del espacio de nombres](../../../csharp/language-reference/keywords/namespace-keywords.md)   
 [. Operador](../../../csharp/language-reference/operators/member-access-operator.md)   
 [extern alias](../../../csharp/language-reference/keywords/extern-alias.md)
