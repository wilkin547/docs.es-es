---
title: ?? Operador (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: ??_CSharpKeyword
helpviewer_keywords:
- coalesce operator [C#]
- ?? operator [C#]
- conditional-AND operator (&&) [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6c2372380d8162d3e7760bba4a43cdb1c568bf5b
ms.sourcegitcommit: 401c4427a3ec0d1263543033b3084039278509dc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2017
---
# <a name="-operator-c-reference"></a>?? Operador (Referencia de C#)
Al operador `??` se le llama el operador de uso combinado de NULL.  Dicho operador devuelve el operando izquierdo si no es NULL; de lo contrario, devuelve el operando derecho.  
  
## <a name="remarks"></a>Comentarios  
 Un tipo que acepta valores NULL puede representar un valor del dominio del tipo, o el valor puede no estar definido (en cuyo caso el valor es NULL). Se puede usar la expresividad sintáctica del operador `??` para devolver un valor apropiado (el operando derecho) cuando el operando izquierdo tenga un tipo que acepta valores NULL cuyo valor sea NULL. Si se intenta asignar un tipo de valor que acepta valores NULL a otro que no sin usar el operador `??`, se generará un error en tiempo de compilación. Si se usa una conversión y el tipo de valor que acepta valores NULL no está definido actualmente, se producirá una excepción `InvalidOperationException`.  
  
 Para más información, vea [Tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md).  
  
 El resultado de un operador ?? no se considera una constante, incluso si sus dos argumentos son constantes.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csRefOperators#53](../../../csharp/language-reference/operators/codesnippet/CSharp/null-conditional-operator_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)  
 [Tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md)  
 [¿Qué significa exactamente "elevado"?](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/)
