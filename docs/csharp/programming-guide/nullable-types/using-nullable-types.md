---
title: "Uso de tipos que aceptan valores NULL (Guía de programación de C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- nullable types [C#], about nullable types
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
caps.latest.revision: 31
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
ms.sourcegitcommit: a780a11d8dd238187eb82933359bbb151bb3c333
ms.openlocfilehash: 88397167b12a00bf5e99a0537148a2957b9f0bd8
ms.contentlocale: es-es
ms.lasthandoff: 05/22/2017

---
# <a name="using-nullable-types-c-programming-guide"></a>Uso de tipos que aceptan valores NULL (Guía de programación de C#)
Los tipos que aceptan valores NULL pueden representar todos los valores de un tipo subyacente y un valor [NULL](../../../csharp/language-reference/keywords/null.md) adicional. Los tipos que aceptan valores NULL se declaran de una de las siguientes dos maneras:  
  
 `System.Nullable<T> variable`  
  
 O bien  
  
 `T? variable`  
  
 `T` es el tipo subyacente del tipo que acepta valores NULL. `T` puede ser cualquier tipo de valor, incluido `struct`; no puede ser un tipo de referencia.  
  
 Para tener un ejemplo de cuándo conviene usar un tipo que acepta valores NULL, piense en cómo una variable booleana común puede tener dos valores: true y false. No hay ningún valor que signifique "indefinido". En muchas aplicaciones de programación, especialmente en las interacciones de bases de datos, puede haber variables con un estado indefinido. Por ejemplo, un campo de una base de datos puede contener los valores true o false, pero también puede no contener ningún valor. De igual modo, los tipos de referencia se pueden establecer en `null` para indicar que no se inicializan.  
  
 Esta disparidad puede conllevar un esfuerzo extra de programación, con variables adicionales que sirven para almacenar información de estado, el uso de valores especiales, etc. El modificador de tipos que aceptan valores NULL permite a C# crear variables de tipo de valor que indican un valor indefinido.  
  
## <a name="examples-of-nullable-types"></a>Ejemplos de tipos que aceptan valores NULL  
 Cualquier tipo de valor puede servir de base de un tipo que acepta valores NULL. Por ejemplo:  
  
 [!code-cs[csProgGuideTypes#4](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_1.cs)]  
  
## <a name="the-members-of-nullable-types"></a>Miembros de los tipos que aceptan valores NULL  
 Cada instancia de un tipo que acepta valores NULL tiene dos propiedades públicas de solo lectura:  
  
-   `HasValue`  
  
     `HasValue` es de tipo `bool`. Se establece en `true` cuando la variable contiene un valor distinto de NULL.  
  
-   `Value`  
  
     `Value` es del mismo tipo que el tipo subyacente. Si `HasValue` es `true`, `Value` contiene un valor significativo. Si `HasValue` es `false`, al acceder a `Value` se generará <xref:System.InvalidOperationException>.  
  
 En este ejemplo, el miembro `HasValue` se usa para probar si la variable contiene un valor antes de que intente mostrarlo.  
  
 [!code-cs[csProgGuideTypes#5](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_2.cs)]  
  
 La comprobación de un valor también se puede realizar como en el siguiente ejemplo:  
  
 [!code-cs[csProgGuideTypes#6](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_3.cs)]  
  
## <a name="explicit-conversions"></a>Conversiones explícitas  
 Un tipo que acepta valores NULL se puede convertir a un tipo regular, ya sea expresamente con una conversión o por medio de la propiedad `Value`. Por ejemplo:  
  
 [!code-cs[csProgGuideTypes#7](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_4.cs)]  
  
 Si se establece una conversión definida por el usuario entre dos tipos de datos, esa misma conversión también se puede usar con las versiones que aceptan valores NULL de dichos tipos de datos.  
  
## <a name="implicit-conversions"></a>Conversiones implícitas  
 Una variable de tipo que acepta valores NULL se puede establecer como NULL con la palabra clave `null`, como se muestra en el siguiente ejemplo:  
  
 [!code-cs[csProgGuideTypes#8](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_5.cs)]  
  
 La conversión de un tipo ordinario a un tipo que acepta valores NULL es implícita.  
  
 [!code-cs[csProgGuideTypes#9](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_6.cs)]  
  
## <a name="operators"></a>Operadores  
 Los tipos que aceptan valores NULL también pueden hacer uso de los operadores predefinidos unario y binario, así como de cualquier operador definido por el usuario que exista para los tipos de valor. Estos operadores generan un valor NULL si los operandos son NULL; si no, el operador usará el valor contenido para calcular el resultado. Por ejemplo:  
  
 [!code-cs[csProgGuideTypes#10](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_7.cs)]  
  
 Cuando realice comparaciones con tipos que aceptan valores NULL, si el valor de uno de los tipos que aceptan valores NULL es NULL y el otro no lo es, todas las comparaciones se evalúan como `false` excepto `!=` (no igual a). Es importante no dar por supuesto que, como una determinada comparación devuelve `false`, el caso contrario devolverá `true`. En el siguiente ejemplo, 10 no es mayor, menor ni igual que NULL. Solo `num1 != num2` evalúa como `true`.  
  
 [!code-cs[csProgGuideTypes#11](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_8.cs)]  
  
 Una comparación de igualdad entre dos tipos que aceptan valores NULL donde ambos son NULL se evalúa como `true`.  
  
## <a name="the--operator"></a>Operador "??"  
 El operador `??` define un valor predeterminado que se devuelve cuando un tipo que acepta valores NULL se asigna a un tipo distinto de NULL.  
  
 [!code-cs[csProgGuideTypes#12](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_9.cs)]  
  
 Este operador se puede usar también con varios tipos que aceptan valores NULL. Por ejemplo:  
  
 [!code-cs[csProgGuideTypes#13](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_10.cs)]  
  
## <a name="the-bool-type"></a>Tipo bool?  
 El tipo que acepta valores NULL `bool?` puede contener tres valores distintos: [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md) y [NULL](../../../csharp/language-reference/keywords/null.md). Para obtener más información sobre cómo convertir un tipo bool? a un tipo bool, vea [Cómo: Convertir con seguridad de bool? a bool](../../../csharp/programming-guide/nullable-types/how-to-safely-cast-from-bool-to-bool.md).  
  
 Los valores booleanos que aceptan valores NULL son como el tipo de variable booleano que se usa en SQL. Para asegurarse de que los resultados generados por los operadores `&` y `|` sean coherentes con el tipo booleano de tres valores en SQL, se proporcionan los siguientes operadores predefinidos:  
  
 `bool? operator &(bool? x, bool? y)`  
  
 `bool? operator |(bool? x, bool? y)`  
  
 Los resultados de estos operadores se muestran en la siguiente tabla:  
  
|X|y|x e y|x | y|  
|-------|-------|---------|--------------|  
|true|true|true|true|  
|true|false|false|true|  
|true|nulo|nulo|true|  
|false|true|false|true|  
|false|false|false|false|  
|false|nulo|false|nulo|  
|nulo|true|nulo|true|  
|nulo|false|false|nulo|  
|nulo|nulo|nulo|nulo|  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md)   
 [Aplicar la conversión boxing a tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)   
 [Tipos de valor que aceptan valores NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
