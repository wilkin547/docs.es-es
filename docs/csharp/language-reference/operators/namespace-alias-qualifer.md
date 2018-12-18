---
title: ':: Operador: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ::_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- 'namespaces [C#], :: operator'
- namespace alias qualifier operator (::) [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
ms.openlocfilehash: 2e456be075f3487676228244e0119ff46ed9a538
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243483"
---
# <a name="-operator-c-reference"></a>:: Operador (Referencia de C#)
El calificador de alias de espacio de nombres (`::`) se usa para buscar identificadores. Siempre se coloca entre dos identificadores, como en este ejemplo:  
  
 [!code-csharp[csRefOperators#27](../../../csharp/language-reference/operators/codesnippet/CSharp/namespace-alias-qualifer_1.cs)]  

El operador `::` también puede utilizarse con una *directiva de alias using*:

```csharp
// using Col=System.Collections.Generic;
var numbers = new Col::List<int> { 1, 2, 3 };
```

## <a name="remarks"></a>Comentarios  
 El calificador de alias de espacio de nombres puede ser `global`. Este invoca una búsqueda del espacio de nombres global, en lugar de un espacio de nombres con alias.  
  
## <a name="for-more-information"></a>Para obtener más información  
 Para obtener un ejemplo de cómo usar el operador `::`, vea la siguiente sección:  
  
-   [Cómo: Utilizar el alias del espacio de nombres global](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [Operadores de C#](../../../csharp/language-reference/operators/index.md)  
- [Palabras clave del espacio de nombres](../../../csharp/language-reference/keywords/namespace-keywords.md)  
- [. !](../../../csharp/language-reference/operators/member-access-operator.md)  
- [extern alias](../../../csharp/language-reference/keywords/extern-alias.md)
