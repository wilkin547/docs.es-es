---
title: Reflexión y tipos genéricos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- generics [.NET Framework], reflection emit
- reflection emit, generic types
- reflection, generic types
- type arguments
- generics [.NET Framework], reflection
- viewing type information
- type information, viewing
- types, generic
- type parameters
ms.assetid: f7180fc5-dd41-42d4-8a8e-1b34288e06de
ms.openlocfilehash: 4894b5cc64dca431c8d05b638847dd6cb7017bde
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180488"
---
# <a name="reflection-and-generic-types"></a>Reflexión y tipos genéricos
Desde el punto de vista de la reflexión, la diferencia entre un tipo genérico y un tipo normal es que un tipo genérico lleva asociado un conjunto de parámetros de tipo (si es una definición de tipo genérico) o de argumentos de tipo (si es un tipo construido). Un método genérico difiere de un método normal de la misma manera.  
  
 Hay dos claves para entender cómo controla la reflexión los tipos y métodos genéricos:  
  
- Los parámetros de tipo de definiciones de tipo genérico y definiciones de método genérico están representados por instancias de la clase <xref:System.Type> .  
  
    > [!NOTE]
    > Muchas propiedades y métodos de <xref:System.Type> tienen un comportamiento diferente cuando un objeto <xref:System.Type> representa un parámetro de tipo genérico. Estas diferencias se documentan en los temas sobre propiedades y métodos. Por ejemplo, vea <xref:System.Type.IsAutoClass%2A> y <xref:System.Type.DeclaringType%2A>. Además, algunos miembros son válidos solamente cuando un objeto <xref:System.Type> representa un parámetro de tipo genérico. Por ejemplo, vea <xref:System.Type.GetGenericTypeDefinition%2A>.  
  
- Si una instancia de <xref:System.Type> representa un tipo genérico, incluye una matriz de tipos que representan los parámetros de tipo (para definiciones de tipo genérico) o argumentos de tipo (para tipos construidos). Lo mismo puede decirse de una instancia de la clase <xref:System.Reflection.MethodInfo> que representa un método genérico.  
  
 La reflexión proporciona métodos de <xref:System.Type> y <xref:System.Reflection.MethodInfo> que le permiten acceder a la matriz de parámetros de tipo y determinar si una instancia de <xref:System.Type> representa un parámetro de tipo o un tipo real.  
  
 Para obtener código de ejemplo en donde se muestran los métodos tratados aquí, vea [Procedimiento: Examinar y crear instancias de tipos genéricos mediante la reflexión](how-to-examine-and-instantiate-generic-types-with-reflection.md).  
  
 El siguiente análisis supone que está familiarizado con la terminología de los genéricos, como la diferencia entre los parámetros y argumentos de tipo y los tipos construidos abiertos o cerrados. Para más información, vea [Genéricos](../../standard/generics/index.md).  

## <a name="is-this-a-generic-type-or-method"></a>¿Es un tipo o método genérico?  
 Cuando se usa la reflexión para examinar un tipo desconocido, representado por una instancia de <xref:System.Type>, use la propiedad <xref:System.Type.IsGenericType%2A> para determinar si el tipo desconocido es genérico. Devuelve `true` si el tipo es genérico. De forma similar, cuando examine un método desconocido, representado por una instancia de la clase <xref:System.Reflection.MethodInfo> , use la propiedad <xref:System.Reflection.MethodBase.IsGenericMethod%2A> para determinar si el método es genérico.  
  
### <a name="is-this-a-generic-type-or-method-definition"></a>¿Es una definición de tipo o método genérico?  
 Use la propiedad <xref:System.Type.IsGenericTypeDefinition%2A> para determinar si un objeto <xref:System.Type> representa una definición de tipo genérico y use el método <xref:System.Reflection.MethodBase.IsGenericMethodDefinition%2A> para determinar si <xref:System.Reflection.MethodInfo> representa una definición de método genérico.  
  
 Las definiciones de tipos y métodos genéricos son las plantillas a partir de las que se crean los tipos instanciables. Los tipos genéricos de la biblioteca de clases de .NET Framework, como <xref:System.Collections.Generic.Dictionary%602>, son definiciones de tipos genéricos.  
  
### <a name="is-the-type-or-method-open-or-closed"></a>¿Es el tipo o método abierto o cerrado?  
 Un tipo o método genérico es cerrado si los tipos instanciables se sustituyeron por todos sus parámetros de tipo, incluidos todos los parámetros de tipo de todos los tipos envolventes. Solo se puede crear una instancia de un tipo genérico si es cerrado. La propiedad <xref:System.Type.ContainsGenericParameters%2A?displayProperty=nameWithType> devuelve `true` si un tipo es abierto. En el caso de los métodos, el método <xref:System.Reflection.MethodBase.ContainsGenericParameters%2A?displayProperty=nameWithType> realiza la misma función.

## <a name="generating-closed-generic-types"></a>Generar tipos genéricos cerrados  
 Cuando tenga una definición de tipo o método genérico, use el método <xref:System.Type.MakeGenericType%2A> para crear un tipo genérico cerrado o el método <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A> para crear <xref:System.Reflection.MethodInfo> para un método genérico cerrado.  
  
### <a name="getting-the-generic-type-or-method-definition"></a>Obtener la definición de tipo o método genérico  
 Si tiene un tipo o método genérico abierto que no es una definición de tipo o método genérico, no puede crear instancias de dicho tipo o método y no puede suministrar los parámetros de tipo que faltan. Debe tener una definición de tipo o método genérico. Use el método <xref:System.Type.GetGenericTypeDefinition%2A> para obtener la definición de tipo genérico o el método <xref:System.Reflection.MethodInfo.GetGenericMethodDefinition%2A> para obtener la definición de método genérico.  
  
 Por ejemplo, si tiene un objeto <xref:System.Type> que representa `Dictionary<int, string>` (`Dictionary(Of Integer, String)` en Visual Basic) y desea crear el tipo `Dictionary<string, MyClass>`, puede usar el método <xref:System.Type.GetGenericTypeDefinition%2A> para obtener <xref:System.Type> que representa `Dictionary<TKey, TValue>` y, a continuación, usar el método <xref:System.Type.MakeGenericType%2A> para generar un objeto <xref:System.Type> que representa `Dictionary<int, MyClass>`.  
  
 Para obtener un ejemplo de un tipo genérico abierto que no es un tipo genérico, vea “Parámetro de tipo o argumento de tipo” más adelante en este tema.

## <a name="examining-type-arguments-and-type-parameters"></a>Examinar argumentos de tipo y parámetros de tipo  
 Use el método <xref:System.Type.GetGenericArguments%2A?displayProperty=nameWithType> para obtener una matriz de objetos <xref:System.Type> que representan los parámetros de tipo o argumentos de tipo de un tipo genérico, y use el método <xref:System.Reflection.MethodInfo.GetGenericArguments%2A?displayProperty=nameWithType> para hacer lo mismo para un método genérico.  
  
 Una vez que sepa que un objeto <xref:System.Type> representa un parámetro de tipo, se plantean muchas otras preguntas que puede responder la reflexión. Puede determinar el origen del parámetro de tipo, su posición y sus restricciones.  
  
### <a name="type-parameter-or-type-argument"></a>Parámetro de tipo o argumento de tipo  
 Para determinar si un elemento determinado de la matriz es un parámetro de tipo o un argumento de tipo, use la propiedad <xref:System.Type.IsGenericParameter%2A> . La propiedad <xref:System.Type.IsGenericParameter%2A> es `true` si el elemento es un parámetro de tipo.  
  
 Un tipo genérico puede ser abierto sin necesidad de ser una definición de tipo genérico, en cuyo caso tiene una mezcla de argumentos de tipo y parámetros de tipo. Por ejemplo, en el código siguiente, la clase `D` deriva de un tipo creado sustituyendo el primer parámetro de tipo de `D` por el segundo parámetro de tipo de `B`.  
  
```csharp  
class B<T, U> {}  
class D<V, W> : B<int, V> {}  
```  
  
```vb  
Class B(Of T, U)  
End Class  
Class D(Of V, W)  
    Inherits B(Of Integer, V)  
End Class  
```  
  
```cpp  
generic<typename T, typename U> ref class B {};  
generic<typename V, typename W> ref class D : B<int, V> {};  
```  
  
 Si obtiene un objeto <xref:System.Type> que representa `D<V, W>` y usa la propiedad <xref:System.Type.BaseType%2A> para obtener su tipo base, el `type B<int, V>` resultante será abierto, pero no es una definición de tipo genérico.  
  
### <a name="source-of-a-generic-parameter"></a>Origen de un parámetro genérico  
 Un parámetro de tipo genérico puede proceder del tipo que se está examinando, de un tipo envolvente o de un método genérico. Puede determinar el origen del parámetro de tipo genérico tal como se indica a continuación:  
  
- En primer lugar, use la propiedad <xref:System.Type.DeclaringMethod%2A> para determinar si el parámetro de tipo procede de un método genérico. Si el valor de propiedad no es una referencia nula (`Nothing` en Visual Basic), el origen es un método genérico.  
  
- Si el origen no es un método genérico, use la propiedad <xref:System.Type.DeclaringType%2A> para determinar a qué tipo genérico pertenece el parámetro de tipo genérico.  
  
 Si el parámetro de tipo pertenece a un método genérico, la propiedad <xref:System.Type.DeclaringType%2A> devuelve el tipo que declaró el método genérico, que es irrelevante.  
  
### <a name="position-of-a-generic-parameter"></a>Posición de un parámetro genérico  
 En raras ocasiones, es necesario determinar la posición de un parámetro de tipo en la lista de parámetros de tipo de su clase de declaración. Por ejemplo, suponga que tiene un objeto <xref:System.Type> que representa el tipo `B<int, V>` del ejemplo anterior. El método <xref:System.Type.GetGenericArguments%2A> proporciona una lista de argumentos de tipo, así que cuando examine `V` puede usar las propiedades <xref:System.Type.DeclaringMethod%2A> y <xref:System.Type.DeclaringType%2A> para descubrir su procedencia. A continuación, puede usar la propiedad <xref:System.Type.GenericParameterPosition%2A> para determinar su posición en la lista de parámetros de tipo donde se definió. En este ejemplo, `V` está en la posición 0 (cero) en la lista de parámetros de tipo donde se definió.  
  
### <a name="base-type-and-interface-constraints"></a>Restricciones de tipo base y de interfaz  
 Use el método <xref:System.Type.GetGenericParameterConstraints%2A> para obtener la restricción de tipo base y las restricciones de interfaz de un parámetro de tipo. El orden de los elementos de la matriz no es significativo. Un elemento representa una restricción de interfaz si se trata de un tipo de interfaz.  
  
### <a name="generic-parameter-attributes"></a>Atributos de parámetro genérico  
 La propiedad <xref:System.Type.GenericParameterAttributes%2A> obtiene un valor <xref:System.Reflection.GenericParameterAttributes> que indica la varianza (covarianza o contravarianza) y las restricciones especiales de un parámetro de tipo.  
  
#### <a name="covariance-and-contravariance"></a>Covarianza y contravarianza  
 Para determinar si un parámetro de tipo es covariante o contravariante, aplique la máscara <xref:System.Reflection.GenericParameterAttributes.VarianceMask?displayProperty=nameWithType> al valor <xref:System.Reflection.GenericParameterAttributes> devuelto por la propiedad <xref:System.Type.GenericParameterAttributes%2A> . Si el resultado es <xref:System.Reflection.GenericParameterAttributes.None?displayProperty=nameWithType>, el parámetro de tipo es invariable. Vea [Covarianza y contravarianza](../../standard/generics/covariance-and-contravariance.md).  
  
#### <a name="special-constraints"></a>Restricciones especiales  
 Para determinar las restricciones especiales de un parámetro de tipo, aplique la máscara <xref:System.Reflection.GenericParameterAttributes.SpecialConstraintMask?displayProperty=nameWithType> al valor <xref:System.Reflection.GenericParameterAttributes> devuelto por la propiedad <xref:System.Type.GenericParameterAttributes%2A> . Si el resultado es <xref:System.Reflection.GenericParameterAttributes.None?displayProperty=nameWithType>, no hay ninguna restricción especial. Un parámetro de tipo puede restringirse para que sea un tipo de referencia, para que sea un tipo de valor que no acepta valores NULL y para que tenga un constructor sin parámetros.

## <a name="invariants"></a>Invariables  
 Para consultar una tabla con las condiciones invariables de los términos comunes usados en la reflexión para tipos genéricos, vea <xref:System.Type.IsGenericType%2A?displayProperty=nameWithType>. Para obtener términos adicionales relativos a los métodos genéricos, vea <xref:System.Reflection.MethodBase.IsGenericMethod%2A?displayProperty=nameWithType>.  

## <a name="related-topics"></a>Temas relacionados  
  
|Title|Descripción|  
|-----------|-----------------|  
|[Cómo: Estudio y creación de instancias de tipos genéricos mediante reflexión](how-to-examine-and-instantiate-generic-types-with-reflection.md)|Muestra cómo usar las propiedades y los métodos de <xref:System.Type> y <xref:System.Reflection.MethodInfo> para examinar los tipos genéricos.|  
|[Genéricos](../../standard/generics/index.md)|Describe la característica de genéricos y cómo se admite en .NET Framework.|  
|[Cómo: Definir un tipo genérico con emisión de reflexión](how-to-define-a-generic-type-with-reflection-emit.md)|Muestra cómo usar la emisión de reflexión para generar tipos genéricos en ensamblados dinámicos.|  
|[Ver información tipos](viewing-type-information.md)|Describe la clase <xref:System.Type> y proporciona ejemplos de código que muestran cómo usar <xref:System.Type> con varias clases de reflexión para obtener información sobre constructores, métodos, campos, propiedades y eventos.|
