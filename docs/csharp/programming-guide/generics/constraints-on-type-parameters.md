---
title: "Restricciones de tipos de parámetros (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- generics [C#], type constraints
- type constraints [C#]
- type parameters [C#], constraints
- unbound type parameter [C#]
ms.assetid: 141b003e-1ddb-4e1c-bcb2-e1c3870e6a51
caps.latest.revision: "41"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f5382b0050b81ed3bb1a075a042bdc4034a3975d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="constraints-on-type-parameters-c-programming-guide"></a>Restricciones de tipos de parámetros (Guía de programación de C#)
Cuando define una clase genérica, puede aplicar restricciones a las clases de tipos que el código cliente puede usar para los argumentos de tipo cuando se crea una instancia de la clase. Si el código de cliente intenta crear una instancia de su clase mediante un tipo que no se permite por una restricción, el resultado es un error en tiempo de compilación. Estas limitaciones se denominan restricciones. Las restricciones se especifican con la palabra clave contextual `where`. En la tabla siguiente se muestran los seis tipos de restricciones:  
  
|Restricción|Descripción|  
|----------------|-----------------|  
|where T: struct|El argumento de tipo debe ser un tipo de valor. Cualquier tipo de valor excepto <xref:System.Nullable> puede especificarse. Para obtener más información, vea [Usar tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/using-nullable-types.md).|  
|where T : class|El argumento de tipo debe ser un tipo de referencia; esto se aplica también a cualquier tipo de clase, interfaz, delegado o matriz.|  
|where T : new()|El argumento de tipo debe tener un constructor sin parámetros público. Cuando se usa conjuntamente con otras restricciones, la restricción `new()` debe especificarse en último lugar.|  
|where T : \<nombre de la clase base>|El argumento de tipo debe ser o derivarse de la clase base especificada.|  
|where T : \<nombre de la interfaz>|El argumento de tipo debe ser o implementar la interfaz especificada. Pueden especificarse varias restricciones de interfaz. La interfaz de restricciones también puede ser genérica.|  
|where T : U|El argumento de tipo proporcionado por T debe ser o derivarse del argumento proporcionado para U.|  
  
## <a name="why-use-constraints"></a>Por qué usar restricciones  
 Si quiere examinar un elemento de una lista genérica para determinar si es válido o para compararlo con otro elemento, el compilador debe tener alguna garantía de que el operador o el método que tiene que llamar se admitirá mediante cualquier argumento de tipo que pueda especificar el código cliente. Esta garantía se obtiene aplicando una o más restricciones a su definición de clase genérica. Por ejemplo, la restricción de clase base indica al compilador que solo los objetos de este tipo o derivados de este tipo se usarán como argumentos de tipo. Una vez que el compilador tenga esta garantía, puede permitir que los métodos de ese tipo se llamen en la clase genérica. Las restricciones se aplican con la palabra clave contextual `where`. En el ejemplo de código siguiente se muestran las funciones que podemos agregar a la clase `GenericList<T>` (en [Introducción a los genéricos](../../../csharp/programming-guide/generics/introduction-to-generics.md)) aplicando una restricción de clase base.  
  
 [!code-csharp[csProgGuideGenerics#11](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_1.cs)]  
  
 La restricción permite que la clase genérica use la propiedad `Employee.Name` porque se garantiza que todos los elementos de tipo T son un objeto `Employee` o un objeto que se hereda de `Employee`.  
  
 Pueden aplicarse varias restricciones en el mismo parámetro de tipo, y las propias restricciones pueden ser tipos genéricos, de la manera siguiente:  
  
 [!code-csharp[csProgGuideGenerics#12](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_2.cs)]  
  
 Al restringir el parámetro de tipo, aumenta el número de operaciones y llamadas al método permitidas a las que se admiten mediante el tipo de restricción y todos los tipos en su jerarquía de herencia. Por lo tanto, cuando diseña métodos o clases genéricas, si va a realizar cualquier operación en los miembros genéricos más allá de una asignación simple o una llamada a cualquier método que no admita `System.Object`, tendrá que aplicar restricciones al parámetro de tipo.  
  
 Al aplicar la restricción `where T : class`, evite los operadores `==` y `!=` en el parámetro de tipo porque estos operadores se probarán solo para la identidad de referencia, no para la igualdad de valor. Esto sucede incluso si estos operadores están sobrecargados en un tipo que se usa como un argumento. En el código siguiente se ilustra este punto; el resultado es False incluso cuando la clase <xref:System.String> sobrecarga al operador `==`.  
  
 [!code-csharp[csProgGuideGenerics#13](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_3.cs)]  
  
 La razón de este comportamiento es que, en tiempo de compilación, el compilador solo conoce que T es un tipo de referencia y, por lo tanto, debe usar los operadores predeterminados que son válidos para todos los tipos de referencia. Si debe probar la igualdad de valor, la manera recomendada también es aplicar la restricción `where T : IComparable<T>` e implementar esa interfaz en cualquier clase que se usará para construir la clase genérica.  
  
## <a name="constraining-multiple-parameters"></a>Restringir varios parámetros  
 Puede aplicar restricciones a varios parámetros, y varias restricciones a un solo parámetro, como se muestra en el siguiente ejemplo:  
  
 [!code-csharp[csProgGuideGenerics#64](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_4.cs)]  
  
## <a name="unbounded-type-parameters"></a>Parámetros de tipo sin enlazar  
 Los parámetros de tipo que no tienen restricciones, como T en la clase pública `SampleClass<T>{}`, se denominan parámetros de tipo sin enlazar. Los parámetros de tipo sin enlazar tienen las reglas siguientes:  
  
-   Los operadores `!=` y `==` no pueden usarse porque no existe ninguna garantía de que el argumento de tipo concreto admitirá estos operadores.  
  
-   Pueden convertirse a y desde `System.Object` o convertirse explícitamente en cualquier tipo de interfaz.  
  
-   Puede comparar con [NULL](../../../csharp/language-reference/keywords/null.md). Si un parámetro sin enlazar se compara con `null`, la comparación siempre devolverá False si el argumento de tipo es un tipo de valor.  
  
## <a name="type-parameters-as-constraints"></a>Parámetros de tipo como restricciones  
 El uso de un parámetro de tipo genérico como una restricción es útil cuando una función de miembro con su propio parámetro de tipo tiene que restringir ese parámetro al parámetro de tipo del tipo contenedor, como se muestra en el ejemplo siguiente:  
  
 [!code-csharp[csProgGuideGenerics#14](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_5.cs)]  
  
 En el ejemplo anterior, `T` es una restricción de tipo en el contexto del método `Add`, y un parámetro de tipo sin enlazar en el contexto de la clase `List`.  
  
 Los parámetros de tipo también pueden usarse como restricciones en definiciones de clase genéricas. Tenga en cuenta que el parámetro de tipo debe declararse dentro de los corchetes angulares junto con cualquier otro parámetro de tipo:  
  
 [!code-csharp[csProgGuideGenerics#15](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_6.cs)]  
  
 La utilidad de los parámetros de tipo como restricciones con clases genéricas es muy limitada porque el compilador no puede asumir nada sobre el parámetro de tipo excepto que deriva de `System.Object`. Use parámetros de tipo como restricciones en clases genéricas en escenarios en los que quiere aplicar una relación de herencia entre dos parámetros de tipo.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Collections.Generic>  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Introducción a los genéricos](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
 [Clases genéricas](../../../csharp/programming-guide/generics/generic-classes.md)  
 [new (restricción)](../../../csharp/language-reference/keywords/new-constraint.md)
