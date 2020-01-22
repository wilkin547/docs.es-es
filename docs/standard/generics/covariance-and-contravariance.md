---
title: Covarianza y contravarianza en genéricos
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- generics, covariance and contravariance
- generics, variance
- covariance and contravariance in generics
- generic type parameters
ms.assetid: 2678dc63-c7f9-4590-9ddc-0a4df684d42e
ms.openlocfilehash: 909b03588d2a41f667bfa117a5cecb420b125088
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708402"
---
# <a name="covariance-and-contravariance-in-generics"></a>Covarianza y contravarianza en genéricos
Covarianza y contravarianza son términos que hacen referencia a la capacidad de usar un tipo más derivado (más específico) o menos derivado (menos específico) que el indicado originalmente. Los parámetros de tipo genérico admiten la covarianza y contravarianza para proporcionar mayor flexibilidad a la hora de asignar y usar tipos genéricos. Cuando se hace referencia a un sistema de tipos, la covarianza, contravarianza e invarianza tienen las siguientes definiciones. En el ejemplo se presupone una clase base denominada `Base` y una clase derivada denominada `Derived`.  
  
- `Covariance`  
  
     Permite usar un tipo más derivado que el especificado originalmente.  
  
     Puede asignar una instancia de `IEnumerable<Derived>` (`IEnumerable(Of Derived)` en Visual Basic) a una variable de tipo `IEnumerable<Base>`.  
  
- `Contravariance`  
  
     Permite usar un tipo más genérico (menos derivado) que el especificado originalmente.  
  
     Puede asignar una instancia de `Action<Base>` (`Action(Of Base)` en Visual Basic) a una variable de tipo `Action<Derived>`.  
  
- `Invariance`  
  
     Significa que solo se puede usar el tipo especificado originalmente. Así, un parámetro de tipo genérico invariable no es covariante ni contravariante.  
  
     No se puede asignar una instancia de `List<Base>` (`List(Of Base)` en Visual Basic) a una variable de tipo `List<Derived>` o viceversa.  
  
 Los parámetros de tipo covariante permiten realizar asignaciones muy similares al [polimorfismo](../../csharp/programming-guide/classes-and-structs/polymorphism.md), como se muestra en el código siguiente.  
  
 [!code-csharp[CoContraSimpleIEnum#1](../../../samples/snippets/csharp/VS_Snippets_CLR/cocontrasimpleienum/cs/example.cs#1)]
 [!code-vb[CoContraSimpleIEnum#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/cocontrasimpleienum/vb/example.vb#1)]  
  
 La clase <xref:System.Collections.Generic.List%601> implementa la interfaz <xref:System.Collections.Generic.IEnumerable%601> , por lo que `List<Derived>` (`List(Of Derived)` en Visual Basic) implementa `IEnumerable<Derived>`. El parámetro de tipo covariante se encarga del resto.  
  
 La contravarianza, sin embargo, parece poco intuitiva. En el siguiente ejemplo, se crea un delegado de tipo `Action<Base>` (`Action(Of Base)` en Visual Basic) y, a continuación, se asigna ese delegado a una variable de tipo `Action<Derived>`.  
  
 [!code-csharp[CoContraSimpleAction#1](../../../samples/snippets/csharp/VS_Snippets_CLR/cocontrasimpleaction/cs/example.cs#1)]
 [!code-vb[CoContraSimpleAction#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/cocontrasimpleaction/vb/example.vb#1)]  
  
 Parece un paso hacia atrás, pero lo que se compila y se ejecuta es código con seguridad de tipos. La expresión lambda se corresponde con el delegado que tiene asignado, por lo que define un método que toma un parámetro de tipo `Base` y no tiene ningún valor devuelto. El delegado resultante puede asignarse a una variable de tipo `Action<Derived>` porque el parámetro de tipo `T` del delegado <xref:System.Action%601> es contravariante. El código tiene seguridad de tipos porque `T` especifica un tipo de parámetro. Cuando se invoca el delegado de tipo `Action<Base>` como si fuera un delegado de tipo `Action<Derived>`, su argumento debe ser de tipo `Derived`. Este argumento siempre se puede pasar de manera segura al método subyacente porque el parámetro del método es de tipo `Base`.  
  
 En general, los parámetros de tipo covariante se pueden utilizar como tipos de valor devuelto de un delegado, y los parámetros de tipo contravariante se pueden usar como tipos de parámetro. En el caso de una interfaz, los parámetros de tipo covariante se pueden utilizar como tipos de valor devuelto de los métodos de la interfaz, y los parámetros de tipo contravariante se pueden usar como tipos de parámetro de los métodos de la interfaz.  
  
 La covarianza y la contravarianza se denominan colectivamente *varianza*. Un parámetro de tipo genérico que no está marcado como covariante ni contravariante se denomina *invariable*. Un breve resumen de hechos relacionados con la varianza en Common Language Runtime:  
  
- En .NET Framework 4, los parámetros de tipo variante están restringidos a los tipos de interfaz genérica y delegado genérico.  
  
- Un tipo de interfaz genérica o de delegado genérico puede tener parámetros de tipo covariante y contravariante.  
  
- La varianza se aplica únicamente a los tipos de referencia; si se especifica un tipo de valor para un parámetro de tipo variante, ese parámetro de tipo es invariable para el tipo construido resultante.  
  
- La varianza no se aplica a la combinación de delegados. Es decir, si hay dos delegados de tipo `Action<Derived>` y de tipo `Action<Base>` (`Action(Of Derived)` y `Action(Of Base)` en Visual Basic), no se puede combinar el segundo delegado con el primero aunque el resultado tuviese seguridad de tipos. La varianza permite la asignación del segundo delegado a una variable de tipo `Action<Derived>`, pero los delegados solo se pueden combinar si tienen exactamente el mismo tipo.

<a name="InterfaceCovariantTypeParameters"></a>
## <a name="generic-interfaces-with-covariant-type-parameters"></a>Interfaces genéricas con parámetros de tipo covariante  
 A partir de .NET Framework 4, varias interfaces genéricas tienen parámetros de tipo covariante; por ejemplo, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.Generic.IEnumerator%601>, <xref:System.Linq.IQueryable%601> y <xref:System.Linq.IGrouping%602>. Todos los parámetros de tipo de estas interfaces son covariantes, por lo que los parámetros de tipo se usan únicamente para los tipos de valor devuelto de los miembros.  
  
 En el ejemplo siguiente, se muestran los parámetros de tipo covariante. Se definen dos tipos: `Base` tiene un método estático denominado `PrintBases` que toma una interfaz `IEnumerable<Base>` (`IEnumerable(Of Base)` en Visual Basic) e imprime los elementos. `Derived` hereda de `Base`. En el ejemplo, se crea un tipo `List<Derived>` (`List(Of Derived)` en Visual Basic) vacío y se muestra que este tipo se puede pasar a `PrintBases` y asignar a una variable de tipo `IEnumerable<Base>` sin conversión alguna. <xref:System.Collections.Generic.List%601> implementa <xref:System.Collections.Generic.IEnumerable%601>, que tiene un solo parámetro de tipo covariante. El parámetro de tipo covariante es el motivo por el cual se puede usar una instancia de `IEnumerable<Derived>` en lugar de `IEnumerable<Base>`.  
  
 [!code-csharp[CoContravarianceInClrGenericI#1](../../../samples/snippets/csharp/VS_Snippets_CLR/cocontravarianceinclrgenerici/cs/example.cs#1)]
 [!code-vb[CoContravarianceInClrGenericI#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/cocontravarianceinclrgenerici/vb/example.vb#1)]  
  
## <a name="generic-interfaces-with-contravariant-generic-type-parameters"></a>Interfaces genéricas con parámetros de tipo genérico contravariante  
 A partir de .NET Framework 4, varias interfaces genéricas tienen parámetros de tipo contravariante; por ejemplo, <xref:System.Collections.Generic.IComparer%601>, <xref:System.IComparable%601> y <xref:System.Collections.Generic.IEqualityComparer%601>. Estas interfaces tienen únicamente parámetros de tipo contravariante, por lo que los parámetros de tipo se utilizan solamente como tipos de parámetro en los miembros de las interfaces.  
  
 En el ejemplo siguiente se muestran los parámetros de tipo contravariante. En el ejemplo se define clase abstracta`MustInherit` ( `Shape` en Visual Basic) con una propiedad `Area` . En el ejemplo también se define una clase `ShapeAreaComparer` que implementa `IComparer<Shape>` (`IComparer(Of Shape)` en Visual Basic). La implementación del método <xref:System.Collections.Generic.IComparer%601.Compare%2A?displayProperty=nameWithType> se basa en el valor de la propiedad `Area` , por lo que `ShapeAreaComparer` se puede usar para ordenar los objetos `Shape` por área.  
  
 La clase `Circle` hereda `Shape` e invalida `Area`. En el ejemplo se crea una colección <xref:System.Collections.Generic.SortedSet%601> de objetos `Circle` , usando un constructor que toma `IComparer<Circle>` (`IComparer(Of Circle)` en Visual Basic). Sin embargo, en lugar de pasar `IComparer<Circle>`, en el ejemplo se pasa un objeto `ShapeAreaComparer` , que implementa `IComparer<Shape>`. En el ejemplo se puede pasar un comparador de un tipo menos derivado (`Shape`) cuando el código llama a un comparador de un tipo más derivado (`Circle`), ya que el parámetro de tipo de la interfaz genérica <xref:System.Collections.Generic.IComparer%601> es contravariante.  
  
 Cuando se agrega un nuevo objeto `Circle` a `SortedSet<Circle>`, se llama al método `IComparer<Shape>.Compare` (`IComparer(Of Shape).Compare` en Visual Basic) del objeto `ShapeAreaComparer` cada vez que el nuevo elemento se compara con un elemento existente. El tipo de parámetro del método (`Shape`) es menos derivado que el tipo que se pasa (`Circle`), por lo que la llamada tiene seguridad de tipos. La contravarianza permite a `ShapeAreaComparer` ordenar una colección de cualquier tipo único, así como a una colección mixta de tipos, que derivan de `Shape`.  
  
 [!code-csharp[CoContravarianceInClrGenericI2#1](../../../samples/snippets/csharp/VS_Snippets_CLR/cocontravarianceinclrgenerici2/cs/example.cs#1)]
 [!code-vb[CoContravarianceInClrGenericI2#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/cocontravarianceinclrgenerici2/vb/example.vb#1)]  

## <a name="generic-delegates-with-variant-type-parameters"></a>Delegados genéricos con parámetros de tipo variante  
 En .NET Framework 4, los delegados genéricos `Func`, como <xref:System.Func%602>, tienen tipos de valor devuelto covariante y tipos de parámetro contravariante. Los delegados genéricos `Action` , como <xref:System.Action%602>, tienen tipos de parámetro contravariante. Esto significa que los delegados se pueden asignar a variables que tengan tipos de parámetro más derivados y (en el caso de los delegados genéricos `Func` ) tipos de valor devuelto menos derivados.  
  
> [!NOTE]
> El último parámetro de tipo genérico de los delegados genéricos `Func` especifica el tipo del valor devuelto en la firma de delegado. Es covariante (palabra clave`out` ), mientras que los otros parámetros de tipo genérico son contravariante (palabra clave`in` ).  
  
 Esto se ilustra en el código siguiente: En el primer fragmento de código, se definen una clase denominada `Base`, una clase denominada `Derived` que hereda de `Base`y otra clase con un método `static` (`Shared` en Visual Basic) denominado `MyMethod`. El método toma una instancia de `Base` y devuelve una instancia de `Derived`. (Si el argumento es una instancia de `Derived`, `MyMethod` la devuelve; si el argumento es una instancia de `Base`, `MyMethod` devuelve una nueva instancia de `Derived`.) En `Main()`, se crea en el ejemplo una instancia de `Func<Base, Derived>` (`Func(Of Base, Derived)` en Visual Basic) que representa `MyMethod`, y la almacena en la variable `f1`.  
  
 [!code-csharp[CoContravarianceDelegates#2](../../../samples/snippets/csharp/VS_Snippets_CLR/cocontravariancedelegates/cs/example.cs#2)]
 [!code-vb[CoContravarianceDelegates#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/cocontravariancedelegates/vb/example.vb#2)]  
  
 En el segundo fragmento de código, se muestra que el delegado puede asignarse a una variable de tipo `Func<Base, Base>` (`Func(Of Base, Base)` en Visual Basic) ya que el tipo de valor devuelto es covariante.  
  
 [!code-csharp[CoContravarianceDelegates#3](../../../samples/snippets/csharp/VS_Snippets_CLR/cocontravariancedelegates/cs/example.cs#3)]
 [!code-vb[CoContravarianceDelegates#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/cocontravariancedelegates/vb/example.vb#3)]  
  
 En el tercer fragmento de código, se muestra que el delegado puede asignarse a una variable de tipo `Func<Derived, Derived>` (`Func(Of Derived, Derived)` en Visual Basic) ya que el tipo de parámetro es contravariante.  
  
 [!code-csharp[CoContravarianceDelegates#4](../../../samples/snippets/csharp/VS_Snippets_CLR/cocontravariancedelegates/cs/example.cs#4)]
 [!code-vb[CoContravarianceDelegates#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/cocontravariancedelegates/vb/example.vb#4)]  
  
 En el último fragmento de código, se muestra que el delegado puede asignarse a una variable de tipo `Func<Derived, Base>` (`Func(Of Derived, Base)` en Visual Basic), combinando los efectos del tipo de parámetro contravariante y el tipo de valor devuelto covariante.  
  
 [!code-csharp[CoContravarianceDelegates#5](../../../samples/snippets/csharp/VS_Snippets_CLR/cocontravariancedelegates/cs/example.cs#5)]
 [!code-vb[CoContravarianceDelegates#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/cocontravariancedelegates/vb/example.vb#5)]  
  
### <a name="variance-in-generic-and-non-generic-delegates"></a>La varianza en delegados genéricos y no genéricos  
 En el código anterior, la signatura de `MyMethod` coincide exactamente con la signatura del delegado genérico construido: `Func<Base, Derived>` (`Func(Of Base, Derived)` en Visual Basic). En el ejemplo, se muestra que este delegado genérico se puede almacenar en variables o en parámetros de método que tengan tipos de parámetro más derivados y tipos de valor devuelto menos derivados, siempre y cuando todos los tipos de delegado se construyan a partir del tipo de delegado genérico <xref:System.Func%602>.  
  
 Este es un aspecto importante. Los efectos de la covarianza y la contravarianza en los parámetros de tipo de los delegados genéricos son similares a los efectos de la covarianza y la contravarianza en el enlace a delegados normal; vea [Varianza en delegados (C#)](../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) y [Varianza en delegados (Visual Basic)](../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md). Sin embargo, la varianza en el enlace a delegados funciona con todos los tipos de delegado, no solo con tipos de delegado genérico que tienen parámetros de tipo variante. Además, la varianza en el enlace a delegados permite enlazar un método a cualquier delegado que tenga tipos de parámetro más restrictivos y un tipo de valor devuelto menos restrictivo, mientras que la asignación de delegados genéricos solo funciona si ambos tipos de delegado se construyen a partir de la misma definición de tipo genérico.  
  
 En el ejemplo siguiente se muestran los efectos combinados de la varianza en el enlace a delegados y la varianza en los parámetros de tipo genérico. En el ejemplo se define una jerarquía de tipos que incluye tres tipos, de menos derivado (`Type1`) a más derivado (`Type3`). La varianza en el enlace a delegados normal se usa para enlazar un método con un tipo de parámetro de `Type1` y un tipo de valor devuelto de `Type3` a un delegado genérico con un tipo de parámetro de `Type2` y un tipo de valor devuelto de `Type2`. A continuación, el delegado genérico resultante se asigna a otra variable cuyo tipo de delegado genérico tiene un parámetro de tipo `Type3` y un tipo de valor devuelto de `Type1`, usando la covarianza y contravarianza de parámetros de tipo genérico. La segunda asignación requiere que tanto el tipo de variable como el tipo de delegado se construyan a partir de la misma definición de tipo genérico, en este caso <xref:System.Func%602>.  
  
 [!code-csharp[CoContravarianceDelegatesGenRelaxed#1](../../../samples/snippets/csharp/VS_Snippets_CLR/cocontravariancedelegatesgenrelaxed/cs/example.cs#1)]
 [!code-vb[CoContravarianceDelegatesGenRelaxed#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/cocontravariancedelegatesgenrelaxed/vb/example.vb#1)]  

## <a name="defining-variant-generic-interfaces-and-delegates"></a>Definir interfaces y delegados genéricos variantes
 A partir de .NET Framework 4, Visual Basic y C# tienen palabras clave que permiten marcar como covariante o contravariante los parámetros de tipo genérico de las interfaces y los delegados.  
  
> [!NOTE]
> A partir de .NET Framework versión 2.0, Common Language Runtime admite anotaciones de varianza en parámetros de tipo genérico. Antes de .NET Framework 4, la única manera de definir una clase genérica que tuviera estas anotaciones era usar el lenguaje intermedio de Microsoft (MSIL), ya fuera mediante la compilación de la clase con [Ilasm.exe (Ensamblador de IL)](../../../docs/framework/tools/ilasm-exe-il-assembler.md) o con la emisión en un ensamblado dinámico.  
  
 Un parámetro de tipo covariante se marca con la palabra clave `out` (palabra clave`Out` en Visual Basic, `+` para el [Ensamblador de MSIL](../../../docs/framework/tools/ilasm-exe-il-assembler.md)). Puede usar un parámetro de tipo covariante como el valor devuelto de un método que pertenece a una interfaz o como el tipo de valor devuelto de un delegado. No puede usar un parámetro de tipo covariante como una restricción de tipo genérico para los métodos de interfaz.  
  
> [!NOTE]
> Si un método de una interfaz tiene un parámetro que es un tipo de delegado genérico, se puede usar un parámetro de tipo covariante del tipo de interfaz para especificar un parámetro de tipo contravariante del tipo de delegado.  
  
 Un parámetro de tipo contravariante se marca con la palabra clave `in` (palabra clave`In` en Visual Basic, `-` para el [Ensamblador de MSIL](../../../docs/framework/tools/ilasm-exe-il-assembler.md)). Puede usar un parámetro de tipo contravariante como el tipo de un parámetro de un método que pertenece a una interfaz o como el tipo de un parámetro de un delegado. Puede usar un parámetro de tipo contravariante como una restricción de tipo genérico para un método de interfaz.  
  
 Solo los tipos de interfaz y los tipos de delegado pueden tener parámetros de tipo variante. Un tipo de interfaz o un tipo de delegado puede tener parámetros de tipo covariante y contravariante.  
  
 Visual Basic y C# no le permiten infringir las reglas de uso de parámetros de tipo covariante y contravariante ni agregar anotaciones de covarianza y contravarianza a los parámetros de tipo de tipos distintos de interfaces y delegados. El [Ensamblador de MSIL](../../../docs/framework/tools/ilasm-exe-il-assembler.md) no realiza esas comprobaciones, pero se produce <xref:System.TypeLoadException> si intenta cargar un tipo que infringe las reglas.  
  
 Para obtener información y código de ejemplo, vea [Varianza en interfaces genéricas (C#)](../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md) y [Varianza en interfaces genéricas (Visual Basic)](../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).  

## <a name="list-of-variant-generic-interface-and-delegate-types"></a>Lista de tipos de interfaces y delegados genéricos variantes
 En .NET Framework 4, los siguientes tipos de interfaz y delegado tienen parámetros de tipo covariante y/o contravariante.  
  
|Tipo|Parámetros de tipo covariante|Parámetros de tipo contravariante|  
|----------|-------------------------------|-----------------------------------|  
|<xref:System.Action%601> a <xref:System.Action%6016>||Sí|  
|<xref:System.Comparison%601>||Sí|  
|<xref:System.Converter%602>|Sí|Sí|  
|<xref:System.Func%601>|Sí||  
|<xref:System.Func%602> a <xref:System.Func%6017>|Sí|Sí|  
|<xref:System.IComparable%601>||Sí|  
|<xref:System.Predicate%601>||Sí|  
|<xref:System.Collections.Generic.IComparer%601>||Sí|  
|<xref:System.Collections.Generic.IEnumerable%601>|Sí||  
|<xref:System.Collections.Generic.IEnumerator%601>|Sí||  
|<xref:System.Collections.Generic.IEqualityComparer%601>||Sí|  
|<xref:System.Linq.IGrouping%602>|Sí||  
|<xref:System.Linq.IOrderedEnumerable%601>|Sí||  
|<xref:System.Linq.IOrderedQueryable%601>|Sí||  
|<xref:System.Linq.IQueryable%601>|Sí||  
  
## <a name="see-also"></a>Vea también

- [Covarianza y contravarianza (C#)](../../csharp/programming-guide/concepts/covariance-contravariance/index.md)
- [Covarianza y contravarianza (Visual Basic)](../../visual-basic/programming-guide/concepts/covariance-contravariance/index.md)
- [Varianza en delegados (C#)](../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)
- [Varianza en delegados (Visual Basic)](../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)
