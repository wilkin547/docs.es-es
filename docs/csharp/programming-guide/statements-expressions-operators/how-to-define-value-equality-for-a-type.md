---
title: "C&#243;mo: Definir la igualdad de valores para un tipo (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Equals (método) [C#], reemplazar"
  - "equivalencia [C#]"
  - "equivalencia de objetos [C#]"
  - "reemplazar el método Equals [C#]"
  - "igualdad de valores [C#]"
ms.assetid: 4084581e-b931-498b-9534-cf7ef5b68690
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# C&#243;mo: Definir la igualdad de valores para un tipo (Gu&#237;a de programaci&#243;n de C#)
Cuando se define una clase o struct, debe decidirse si tiene sentido crear una definición personalizada de la igualdad \(o equivalencia\) de valores para el tipo.  Normalmente, una igualdad de valores se implementa cuando se espera que se agreguen a una colección determinada objetos del tipo concreto o cuando el propósito principal es almacenar un conjunto de campos o propiedades.  La definición de igualdad de valores se puede basar en una comparación de todos los campos y propiedades del tipo o bien en un subconjunto.  No obstante, en cualquiera de los casos y tanto en las clases como los structs, la implementación debe seguir las cinco garantías de equivalencia:  
  
1.  x.`Equals`\(x\) devuelve `true.` Esto se denomina propiedad reflexiva.  
  
2.  x.`Equals`\(y\) devuelve el mismo valor que y.`Equals`\(x\).  Esto se denomina propiedad simétrica.  
  
3.  si \(x.`Equals`\(y\) && y.`Equals`\(z\)\) devuelve `true`, x.`Equals`\(z\) devuelve `true`.  Esto se denomina propiedad transitiva.  
  
4.  Las invocaciones sucesivas de x.`Equals`\(y\) devuelven el mismo valor siempre que no se modifiquen los objetos a los que hacen referencia x e y.  
  
5.  x.`Equals`\(null\) devuelve `false`.  Sin embargo, null.Equals \(null\) produce una excepción; no obedece la regla número dos anterior.  
  
 Cualquier struct que se defina ya tiene una implementación predeterminada de igualdad de valores que hereda de la invalidación <xref:System.ValueType?displayProperty=fullName> del método <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName>.  Esta implementación usa la reflexión para examinar todas las propiedades y los campos públicos y no públicos del tipo.  Aunque esta implementación genera resultados correctos, es relativamente lenta en comparación con una implementación personalizada escrita por el usuario específicamente para el tipo.  
  
 Los detalles de implementación de la igualdad de valores son distintos para las clases y los structs.  Sin embargo, tanto las clases como los structs requieren los mismos pasos básicos para implementar la igualdad:  
  
1.  Invalide el método <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName> [virtual](../../../csharp/language-reference/keywords/virtual.md).  En la mayoría de los casos, la implementación de `bool Equals( object obj )` debería llamar simplemente al método `Equals` específico del tipo que es la implementación de la interfaz <xref:System.IEquatable%601?displayProperty=fullName>.  \(Ver el paso 2\).  
  
2.  Implemente la interfaz <xref:System.IEquatable%601?displayProperty=fullName> proporcionando un método `Equals` específico del tipo.  Aquí es donde se realiza la comparación de equivalencias en sí.  Por ejemplo, puede que decida definir la igualdad mediante la comparación de uno o dos campos del tipo solamente.  No inicie excepciones desde `Equals`.  Para las clases solamente: este método solo debe examinar los campos declarados en la clase.  Debe llamar a `base.Equals` para examinar los campos que están en la clase base.  \(No lleve a cabo esta acción si el tipo hereda directamente de <xref:System.Object>, ya que la implementación <xref:System.Object> de <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName> realiza una comprobación de igualdad de referencias\).  
  
3.  Opcional pero recomendado: sobrecargue los operadores [\=\=](../../../csharp/language-reference/operators/equality-comparison-operator.md) y [\!\=](../../../csharp/language-reference/operators/not-equal-operator.md).  
  
4.  Invalide <xref:System.Object.GetHashCode%2A?displayProperty=fullName> para que dos objetos que tengan igualdad de valores produzcan el mismo código hash.  
  
5.  Opcional: para admitir las definiciones de "mayor que" o "menor que", implemente la interfaz <xref:System.IComparable%601> para su tipo y sobrecargue también los operadores [\<\=](../../../csharp/language-reference/operators/less-than-equal-operator.md) y [\>\=](../../../csharp/language-reference/operators/greater-than-equal-operator.md).  
  
 El primer ejemplo que sigue las presentaciones una implementación de clase.  El segundo ejemplo muestra una implementación de struct.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo implementar la igualdad de valores en una clase \(tipo de referencia\).  
  
 [!code-cs[csProgGuideStatements#19](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-value-equality-for-a-type_1.cs)]  
  
 En las clases \(tipos de referencia\), la implementación predeterminada de ambos métodos <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName> realiza una comparación de igualdad de referencias, no una comprobación de la igualdad de valores.  Cuando un implementador invalida el método virtual, el propósito es asignarle semántica de igualdad de valores.  
  
 Los operadores `==` y `!=` se pueden usar con clases aun en el caso de que la clase no los sobrecargue.  Sin embargo, el comportamiento predeterminado consiste en realizar una comprobación de la igualdad de referencias.  En una clase, si se sobrecarga el método `Equals`, se deberían sobrecargar los operadores `==` y `!=`, pero no es estrictamente necesario.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo implementar la igualdad de valores en un struct \(tipo de valor\):  
  
 [!code-cs[csProgGuideStatements#20](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-value-equality-for-a-type_2.cs)]  
  
 En el caso de los structs, la implementación predeterminada de <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName> \(que es la versión invalidada en <xref:System.ValueType?displayProperty=fullName>\) realiza una comprobación de la igualdad de valores en la que usa la reflexión para comparar los valores de cada campo del tipo.  Cuando un implementador invalida el método `Equals` virtual en un struct, el propósito es proporcionar una forma más eficaz de realizar la comprobación de la igualdad de valores y, opcionalmente, basar la comparación en algún subconjunto del campo o las propiedades del struct.  
  
 Los operadores [\=\=](../../../csharp/language-reference/operators/equality-comparison-operator.md) y [\!\=](../../../csharp/language-reference/operators/not-equal-operator.md) no pueden funcionar en un struct a menos que este los sobrecargue explícitamente.  
  
## Vea también  
 [Comparaciones de igualdad](../../../csharp/programming-guide/statements-expressions-operators/equality-comparisons.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)