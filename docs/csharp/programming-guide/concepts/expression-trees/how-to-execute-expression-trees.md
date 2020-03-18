---
title: Procedimiento para ejecutar árboles de expresión (C#)
ms.date: 07/20/2015
ms.assetid: b8c40db5-2464-4bb9-9001-8c2bc7f006c5
ms.openlocfilehash: e7d408ea154572dc8b45d2e67bca3f05837868d2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "73969888"
---
# <a name="how-to-execute-expression-trees-c"></a>Procedimiento para ejecutar árboles de expresión (C#)
En este tema se muestra cómo ejecutar un árbol de expresión. La ejecución de un árbol de expresión puede devolver un valor o simplemente realizar una acción, como llamar a un método.  
  
 Solo se pueden ejecutar los árboles de expresiones que representan expresiones lambda. Los árboles de expresiones que representan expresiones lambda son de tipo <xref:System.Linq.Expressions.LambdaExpression> o <xref:System.Linq.Expressions.Expression%601>. Para ejecutar estos árboles de expresiones, llame al método <xref:System.Linq.Expressions.LambdaExpression.Compile%2A> para crear un delegado ejecutable y, después, invoque el delegado.  
  
> [!NOTE]
> Si el tipo del delegado es desconocido, es decir, la expresión lambda es de tipo <xref:System.Linq.Expressions.LambdaExpression> y no <xref:System.Linq.Expressions.Expression%601>, debe llamar al método <xref:System.Delegate.DynamicInvoke%2A> en el delegado en lugar de invocarlo directamente.  
  
 Si un árbol de expresión no representa una expresión lambda, puede crear una nueva expresión lambda que tenga el árbol de expresión original como su cuerpo llamando al método <xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29>. Luego puede ejecutar la expresión lambda tal y como se ha descrito anteriormente en esta sección.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se muestra cómo ejecutar un árbol de expresión que representa la elevación de un número a una potencia mediante la creación de una expresión lambda y su posterior ejecución. Se muestra el resultado, que representa el número elevado a la potencia.  
  
```csharp  
// The expression tree to execute.  
BinaryExpression be = Expression.Power(Expression.Constant(2D), Expression.Constant(3D));  
  
// Create a lambda expression.  
Expression<Func<double>> le = Expression.Lambda<Func<double>>(be);  
  
// Compile the lambda expression.  
Func<double> compiledExpression = le.Compile();  
  
// Execute the lambda expression.  
double result = compiledExpression();  
  
// Display the result.  
Console.WriteLine(result);  
  
// This code produces the following output:  
// 8  
```  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
- Incluya el espacio de nombres System.Linq.Expressions.  
  
## <a name="see-also"></a>Vea también

- [Árboles de expresión (C#)](./index.md)
- [Procedimiento para modificar árboles de expresión (C#)](./how-to-modify-expression-trees.md)
