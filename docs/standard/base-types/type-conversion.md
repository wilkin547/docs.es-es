---
title: Conversión de tipos en .NET Framework
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- widening conversions
- explicit conversions
- narrowing conversions
- type conversion, about type conversion
- type conversion
- converting types
- narrowing coercion
- Explicit operator
- IConvertible interface
- base types, converting
- op_Implicit method
- widening coercion
- op_Explicit method
- Convert class
- implicit conversions
- Implicit operator
- data types [.NET Framework], converting
ms.assetid: ba36154f-064c-47d3-9f05-72f93a7ca96d
ms.openlocfilehash: 33b8c49033c901917e674879048558799f484194
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291661"
---
# <a name="type-conversion-in-the-net-framework"></a>Conversión de tipos en .NET Framework
Cada valor tiene un tipo asociado, que define atributos como la cantidad de espacio asignado al valor, el intervalo de valores posibles que puede tener y los miembros que ofrece. Muchos valores se pueden expresar como más de un tipo. Por ejemplo, el valor 4 se puede expresar como un entero o como un valor de punto flotante. La conversión de tipo crea un valor en un nuevo tipo que es equivalente al valor de un tipo antiguo, pero no conserva necesariamente la identidad (o valor exacto) del objeto original.  
  
 .NET Framework admite automáticamente las conversiones siguientes:  
  
- Conversión de una clase derivada a una clase base. Esto significa, por ejemplo, que una instancia de cualquier clase o estructura se puede convertir en una instancia de tipo <xref:System.Object>.  Esta conversión no requiere un operador de conversión.  
  
- Conversión de una clase base a la clase derivada original. En C#, esta conversión requiere un operador de conversión. En Visual Basic, requiere el operador `CType` si `Option Strict` está activado.  
  
- Conversión de un tipo que implementa una interfaz a un objeto de interfaz que representa esa interfaz. Esta conversión no requiere un operador de conversión.  
  
- Conversión de un objeto de interfaz al tipo original que implementa esa interfaz.  En C#, esta conversión requiere un operador de conversión. En Visual Basic, requiere el operador `CType` si `Option Strict` está activado.  
  
 Además de estas conversiones automáticas, .NET Framework proporciona varias características que admiten la conversión de tipos personalizada. Entre ellas se incluyen las siguientes:  
  
- El operador `Implicit`, que define las conversiones de ampliación disponibles entre los tipos. Para obtener más información, consulte la sección [Conversión implícita con el operador Implicit](#implicit-conversion-with-the-implicit-operator).  
  
- El operador `Explicit`, que define las conversiones de restricción disponibles entre los tipos. Para obtener más información, consulte la sección [Conversión explícita con el operador Explicit](#explicit-conversion-with-the-explicit-operator).  
  
- La interfaz <xref:System.IConvertible>, que define las conversiones en cada uno de los tipos de datos base de .NET Framework. Para obtener más información, vea [Interfaz IConvertible](#the-iconvertible-interface).  
  
- La clase <xref:System.Convert>, que proporciona un conjunto de métodos que implementan los métodos de la interfaz <xref:System.IConvertible>. Para obtener más información, vea la sección [Clase Convert](#the-convert-class).  
  
- La clase <xref:System.ComponentModel.TypeConverter>, que es una clase base que se puede extender para admitir la conversión de un tipo concreto en cualquier otro tipo. Para obtener más información, vea [Clase TypeConverter](#the-typeconverter-class).  

## <a name="implicit-conversion-with-the-implicit-operator"></a>Conversión implícita con el operador Implicit  
 Las conversiones de ampliación implican la creación de un nuevo valor a partir del valor de un tipo existente que tiene un intervalo más restrictivo o una lista de miembros más restringida que el tipo de destino. Las conversión de ampliación no pueden producir ninguna pérdida de datos (aunque pueden producir una pérdida de precisión). Puesto que no se pueden perder datos, los compiladores pueden administrar la conversión de manera implícita o transparente, sin que sea necesario el uso de un método de conversión explícito o de un operador de conversión.  
  
> [!NOTE]
> Aunque el código que realiza una conversión implícita puede llamar a un método de conversión o usar un operador de conversión, los compiladores que admiten las conversiones implícitas no necesitan usarlos.  
  
 Por ejemplo, el tipo <xref:System.Decimal> admite conversiones implícitas a partir de valores <xref:System.Byte>, <xref:System.Char>, <xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.SByte>, <xref:System.UInt16>, <xref:System.UInt32> y <xref:System.UInt64>. En el ejemplo siguiente se muestran algunas de estas conversiones implícitas al asignar valores a una variable <xref:System.Decimal>.  
  
 [!code-csharp[Conceptual.Conversion#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.conversion/cs/implicit1.cs#1)]
 [!code-vb[Conceptual.Conversion#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.conversion/vb/implicit1.vb#1)]  
  
 Si un compilador de un lenguaje determinado admite operadores personalizados, también puede definir conversiones implícitas en sus propios tipos personalizados. En el ejemplo siguiente se proporciona una implementación parcial de un tipo de datos de byte con signo denominado `ByteWithSign` que usa la representación de signo y magnitud. Admite la conversión implícita de valores <xref:System.Byte> y <xref:System.SByte> a valores `ByteWithSign`.  
  
 [!code-csharp[Conceptual.Conversion#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.conversion/cs/implicit1.cs#2)]
 [!code-vb[Conceptual.Conversion#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.conversion/vb/implicit1.vb#2)]  
  
 A continuación, el código de cliente puede declarar una variable `ByteWithSign` y asignarle valores <xref:System.Byte> y <xref:System.SByte> sin realizar ninguna conversión explícita ni emplear ningún operador de conversión, como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[Conceptual.Conversion#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.conversion/cs/implicit1.cs#3)]
 [!code-vb[Conceptual.Conversion#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.conversion/vb/implicit1.vb#3)]  

## <a name="explicit-conversion-with-the-explicit-operator"></a>Conversión explícita con el operador Explicit  
 Las conversiones de restricción implican la creación de un nuevo valor a partir del valor de un tipo existente que tiene un intervalo mayor o una lista de miembros mayor que el tipo de destino. Puesto que una conversión de restricción puede producir una pérdida de datos, los compiladores suelen necesitar que la conversión se haga explícita a través de una llamada a un método de conversión o a un operador de conversión. Es decir, la conversión se debe administrar explícitamente en el código de desarrollo.  
  
> [!NOTE]
> La finalidad principal de solicitar un método de conversión o un operador de conversión para las conversiones de restricción es que el desarrollador sea consciente de la posibilidad de que se pierdan datos o de que se produzca una excepción <xref:System.OverflowException>, para que se pueda administrar en el código. Sin embargo, algunos compiladores pueden ser menos exigentes con este requisito. Por ejemplo, en Visual Basic, si `Option Strict` está desactivado (la configuración predeterminada), el compilador de Visual Basic intenta realizar las conversiones de restricción implícitamente.  
  
 Por ejemplo, los tipos de datos <xref:System.UInt32>, <xref:System.Int64> y <xref:System.UInt64> tienen intervalos que superan el del tipo de datos <xref:System.Int32>, como se muestra en la tabla siguiente.  
  
|Tipo|Comparación con el intervalo de Int32|  
|----------|------------------------------------|  
|<xref:System.Int64>|<xref:System.Int64.MaxValue?displayProperty=nameWithType> es mayor que <xref:System.Int32.MaxValue?displayProperty=nameWithType>, y <xref:System.Int64.MinValue?displayProperty=nameWithType> es menor que (tiene un intervalo negativo mayor que) <xref:System.Int32.MinValue?displayProperty=nameWithType>.|  
|<xref:System.UInt32>|<xref:System.UInt32.MaxValue?displayProperty=nameWithType> es mayor que <xref:System.Int32.MaxValue?displayProperty=nameWithType>.|  
|<xref:System.UInt64>|<xref:System.UInt64.MaxValue?displayProperty=nameWithType> es mayor que <xref:System.Int32.MaxValue?displayProperty=nameWithType>.|  
  
 Para administrar estas conversiones de restricción, .NET Framework permite que los tipos definan un operador `Explicit`. A continuación, los compiladores de lenguaje individuales pueden implementar este operador usando su propia sintaxis o se puede llamar a un miembro de la clase <xref:System.Convert> para realizar la conversión. (Para obtener más información sobre la clase <xref:System.Convert>, vea [Clase Convert](#the-convert-class) más adelante en este tema). En el ejemplo siguiente se muestra el uso de las características de lenguaje para administrar la conversión explícita de estos valores enteros, que potencialmente están fuera del intervalo, a valores <xref:System.Int32>.  
  
 [!code-csharp[Conceptual.Conversion#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.conversion/cs/explicit1.cs#4)]
 [!code-vb[Conceptual.Conversion#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.conversion/vb/explicit1.vb#4)]  
  
 Las conversiones explícitas pueden producir resultados diferentes en los distintos lenguajes y estos resultados pueden diferir del valor devuelto por el método <xref:System.Convert> correspondiente. Por ejemplo, si el valor <xref:System.Double> 12.63251 se convierte en <xref:System.Int32>, el método `CInt` de Visual Basic y el método <xref:System.Convert.ToInt32%28System.Double%29?displayProperty=nameWithType> de .NET Framework redondean el valor <xref:System.Double> para devolver un valor de 13, pero el operador `(int)` de C# trunca <xref:System.Double> para devolver un valor de 12. De manera similar, el operador `(int)` de C# no admite la conversión de booleano a entero, pero el método `CInt` de Visual Basic convierte un valor de `true` en -1. Por otra parte, el método <xref:System.Convert.ToInt32%28System.Boolean%29?displayProperty=nameWithType> convierte un valor de `true` en 1.  
  
 La mayoría de los compiladores permiten realizar conversiones explícitas de manera comprobada o no comprobada. Cuando se realiza una conversión comprobada, se produce una excepción <xref:System.OverflowException> si el valor del tipo que se va a convertir está fuera del intervalo del tipo de destino. Si se realiza una conversión no comprobada en las mismas condiciones, es posible que la conversión no produzca una excepción, pero no se podrá determinar con exactitud cuál será el comportamiento y se puede obtener como resultado un valor incorrecto.  
  
> [!NOTE]
> En C#, las conversiones comprobadas se pueden realizar usando la palabra clave `checked` junto con un operador de conversión o especificando la opción del compilador `/checked+`. Por el contrario, las conversiones no comprobadas se pueden realizar utilizando la palabra clave `unchecked` junto con el operador de conversión de tipo o especificando la opción del compilador `/checked-`. De forma predeterminada, las conversiones explícitas no se comprueban. En Visual Basic, para realizar conversiones comprobadas, se puede desactivar la casilla **Quitar comprobaciones de desbordamiento con enteros** en el cuadro de diálogo **Configuración de compilador avanzada** del proyecto o especificando la opción de compilador `/removeintchecks-`. Por el contrario, para realizar conversiones no comprobadas, se puede activar la casilla **Quitar comprobaciones de desbordamiento con enteros** en el cuadro de diálogo **Configuración de compilador avanzada** del proyecto o especificando la opción de compilador `/removeintchecks+`. De forma predeterminada, las conversiones explícitas se comprueban.  
  
 En el siguiente ejemplo de C# se usan las palabras clave `checked` y `unchecked` para mostrar la diferencia de comportamiento cuando un valor que está fuera del intervalo de <xref:System.Byte> se convierte en <xref:System.Byte>. La conversión comprobada produce una excepción, pero la conversión no comprobada asigna <xref:System.Byte.MaxValue?displayProperty=nameWithType> a la variable <xref:System.Byte>.  
  
 [!code-csharp[Conceptual.Conversion#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.conversion/cs/explicit1.cs#12)]  
  
 Si un compilador de un lenguaje determinado admite operadores sobrecargados personalizados, también puede definir conversiones explícitas en sus propios tipos personalizados. En el ejemplo siguiente se proporciona una implementación parcial de un tipo de datos de byte con signo denominado `ByteWithSign` que usa la representación de signo y magnitud. Admite la conversión explícita de valores <xref:System.Int32> y <xref:System.UInt32> a valores `ByteWithSign`.  
  
 [!code-csharp[Conceptual.Conversion#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.conversion/cs/explicit1.cs#5)]
 [!code-vb[Conceptual.Conversion#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.conversion/vb/explicit1.vb#5)]  
  
 A continuación, el código de cliente puede declarar una variable `ByteWithSign` y asignarle valores de tipo <xref:System.Int32> y <xref:System.UInt32> si las asignaciones incluyen un operador de conversión o un método de conversión, como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[Conceptual.Conversion#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.conversion/cs/explicit1.cs#6)]
 [!code-vb[Conceptual.Conversion#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.conversion/vb/explicit1.vb#6)]  

## <a name="the-iconvertible-interface"></a>La interfaz IConvertible  
 Para admitir la conversión de cualquier tipo en un tipo base de Common Language Runtime, .NET Framework proporciona la interfaz <xref:System.IConvertible>. El tipo que se está implementando debe proporcionar lo siguiente:  
  
- Un método que devuelva el objeto <xref:System.TypeCode> del tipo que se está implementando.  
  
- Métodos para convertir el tipo que se está implementando en cada uno de los tipos base de Common Language Runtime (<xref:System.Boolean>, <xref:System.Byte>, <xref:System.DateTime>, <xref:System.Decimal>, <xref:System.Double>, etc.).  
  
- Un método de conversión generalizado para convertir una instancia del tipo que se está implementando en otro tipo concreto. Las conversiones que no se admiten deben iniciar una excepción <xref:System.InvalidCastException>.  
  
 Cada uno de los tipos base de Common Language Runtime (es decir, <xref:System.Boolean>, <xref:System.Byte>, <xref:System.Char>, <xref:System.DateTime>, <xref:System.Decimal>, <xref:System.Double>, <xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.SByte>, <xref:System.Single>, <xref:System.String>, <xref:System.UInt16>, <xref:System.UInt32>y <xref:System.UInt64>), así como los tipos <xref:System.DBNull> y <xref:System.Enum>, implementan la interfaz <xref:System.IConvertible>. Sin embargo, se trata de implementaciones de interfaz explícitas; solo se puede llamar al método de conversión mediante una variable de la interfaz <xref:System.IConvertible>, como se muestra en el ejemplo siguiente. Este ejemplo convierte un valor <xref:System.Int32> en su valor <xref:System.Char> equivalente.  
  
 [!code-csharp[Conceptual.Conversion#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.conversion/cs/iconvertible1.cs#7)]
 [!code-vb[Conceptual.Conversion#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.conversion/vb/iconvertible1.vb#7)]  
  
 El requisito de llamar al método de conversión en su interfaz, en lugar de en el tipo que se está implementando, hace que las implementaciones de interfaz explícitas resulten relativamente costosas. En su lugar, se recomienda llamar al miembro adecuado de la clase <xref:System.Convert> para convertir entre los tipos base de Common Language Runtime. Para obtener más información, consulte la próxima sección, [Clase Convert](#the-convert-class).  
  
> [!NOTE]
> Además de la interfaz <xref:System.IConvertible> y la clase <xref:System.Convert> proporcionadas por .NET Framework, cada lenguaje puede proporcionar también maneras de realizar conversiones. Por ejemplo, C# utiliza operadores de conversión, mientras que Visual Basic utiliza funciones de conversión implementadas por el compilador como `CType`, `CInt` y `DirectCast`.  
  
 En su mayor parte, la interfaz <xref:System.IConvertible> está diseñada para admitir la conversión entre los tipos base de .NET Framework. Sin embargo, la interfaz también puede implementarse por un tipo personalizado con el fin de admitir la conversión de ese tipo a otros tipos personalizados. Para obtener más información, consulte la sección [Conversiones personalizadas con el método ChangeType](#custom-conversions-with-the-changetype-method) más adelante en este tema.

## <a name="the-convert-class"></a>Clase Convert
 Aunque se puede llamar a la implementación de la interfaz <xref:System.IConvertible> de cada tipo base para realizar una conversión de tipo, llamar a los métodos de la clase <xref:System.Convert?displayProperty=nameWithType> es la manera recomendada de convertir de un tipo base en otro de una manera independiente del lenguaje. Además, se puede usar el método <xref:System.Convert.ChangeType%28System.Object%2CSystem.Type%2CSystem.IFormatProvider%29?displayProperty=nameWithType> para convertir de un tipo personalizado concreto a otro tipo.  
  
### <a name="conversions-between-base-types"></a>Conversiones entre los tipos base  
 La clase <xref:System.Convert> proporciona una manera independiente del lenguaje de realizar conversiones entre los tipos base y está disponible para todos los lenguajes cuyo destino es Common Language Runtime. Ofrece un conjunto completo de métodos tanto para conversiones de ampliación como de restricción e inicia una excepción <xref:System.InvalidCastException> para las conversiones que no se admiten (como la conversión de un valor <xref:System.DateTime> a un valor entero). Las conversiones de restricción se realizan en un contexto comprobado y se inicia una excepción <xref:System.OverflowException> si se produce un error en la conversión.  
  
> [!IMPORTANT]
> Puesto que la clase <xref:System.Convert> incluye métodos para efectuar la conversión directa e inversa de cada tipo base, elimina la necesidad de llamar a la implementación de interfaz explícita <xref:System.IConvertible> de cada tipo base.  
  
 En el ejemplo siguiente se muestra el uso de la clase <xref:System.Convert?displayProperty=nameWithType> para realizar varias conversiones de restricción y ampliación entre los tipos base de .NET Framework.  
  
 [!code-csharp[Conceptual.Conversion#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.conversion/cs/convert1.cs#8)]
 [!code-vb[Conceptual.Conversion#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.conversion/vb/convert1.vb#8)]  
  
 En algunos casos, en especial al efectuar conversiones directas e inversas de valores de punto flotante, una conversión puede conllevar una pérdida de precisión, aunque no se inicie una excepción <xref:System.OverflowException>. En el ejemplo siguiente se muestra esta pérdida de precisión. En el primer caso, un valor <xref:System.Decimal> tiene menos precisión (menos dígitos significativos) cuando se convierte en el tipo <xref:System.Double>. En el segundo caso, un valor <xref:System.Double> se redondea de 42,72 a 43 para completar la conversión.  
  
 [!code-csharp[Conceptual.Conversion#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.conversion/cs/convert1.cs#9)]
 [!code-vb[Conceptual.Conversion#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.conversion/vb/convert1.vb#9)]  
  
 Para obtener una tabla en la que se muestra una lista de conversiones de restricción y ampliación admitidas por la clase <xref:System.Convert>, vea [Tablas de conversiones de tipos](conversion-tables.md).  

### <a name="custom-conversions-with-the-changetype-method"></a>Conversiones personalizadas con el método ChangeType  
 Además de admitir las conversiones en cada uno de los tipos base, la clase <xref:System.Convert> se puede usar para convertir un tipo personalizado en uno o varios tipos predefinidos. El método <xref:System.Convert.ChangeType%28System.Object%2CSystem.Type%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, que a su vez contiene una llamada al método <xref:System.IConvertible.ToType%2A?displayProperty=nameWithType> del parámetro `value`, realiza esta conversión. Esto significa que el objeto representado por el parámetro `value` debe proporcionar una implementación de la interfaz <xref:System.IConvertible>.  
  
> [!NOTE]
> Dado que los métodos <xref:System.Convert.ChangeType%28System.Object%2CSystem.Type%29?displayProperty=nameWithType> y <xref:System.Convert.ChangeType%28System.Object%2CSystem.Type%2CSystem.IFormatProvider%29?displayProperty=nameWithType> utilizan un objeto <xref:System.Type> para especificar el tipo de destino al que se convierte `value`, se pueden utilizar para realizar una conversión dinámica a un objeto cuyo tipo se desconoce en tiempo de compilación. Sin embargo, observe que la implementación de <xref:System.IConvertible> de `value` aún debe admitir esta conversión.  
  
 En el ejemplo siguiente se muestra una posible implementación de la interfaz <xref:System.IConvertible> que permite convertir un objeto `TemperatureCelsius` en un objeto `TemperatureFahrenheit` y viceversa. En el ejemplo se define una clase base, `Temperature`, que implementa la interfaz <xref:System.IConvertible> e invalida el método <xref:System.Object.ToString%2A?displayProperty=nameWithType>. Cada una de las clases derivadas `TemperatureCelsius` y `TemperatureFahrenheit` invalida los métodos `ToType` y `ToString` de la clase base.  
  
 [!code-csharp[Conceptual.Conversion#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.conversion/cs/iconvertible2.cs#10)]
 [!code-vb[Conceptual.Conversion#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.conversion/vb/iconvertible2.vb#10)]  
  
 En el ejemplo siguiente se muestran varias llamadas a estas implementaciones de <xref:System.IConvertible> para convertir los objetos `TemperatureCelsius` en objetos `TemperatureFahrenheit` y viceversa.  
  
 [!code-csharp[Conceptual.Conversion#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.conversion/cs/iconvertible2.cs#11)]
 [!code-vb[Conceptual.Conversion#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.conversion/vb/iconvertible2.vb#11)]  

## <a name="the-typeconverter-class"></a>Clase TypeConverter  
 .NET Framework también permite definir un convertidor de tipos para un tipo personalizado extendiendo la clase <xref:System.ComponentModel.TypeConverter?displayProperty=nameWithType> y asociando el convertidor de tipos al tipo mediante un atributo <xref:System.ComponentModel.TypeConverterAttribute?displayProperty=nameWithType>. En la tabla siguiente se resaltan las diferencias entre este enfoque y la implementación de la interfaz <xref:System.IConvertible> para un tipo personalizado.  
  
> [!NOTE]
> Se puede proporcionar compatibilidad en tiempo de diseño para un tipo personalizado sólo si se ha definido un convertidor de tipos para éste.  
  
|Conversión mediante TypeConverter|Conversión mediante IConvertible|  
|------------------------------------|-----------------------------------|  
|Se implementa para un tipo personalizado derivando una clase independiente de <xref:System.ComponentModel.TypeConverter>. Esta clase derivada se asocia al tipo personalizado aplicando un atributo <xref:System.ComponentModel.TypeConverterAttribute>.|Se implementa mediante un tipo personalizado para realizar la conversión. Un usuario del tipo invoca un método de conversión de <xref:System.IConvertible> para el tipo.|  
|Se puede utilizar en tiempo de diseño y en tiempo de ejecución.|Sólo se puede utilizar en tiempo de ejecución.|  
|Usa la reflexión; por tanto, es más lenta que la conversión mediante <xref:System.IConvertible>.|No utiliza la reflexión.|  
|Permite realizar conversiones bidireccionales; es decir, convertir el tipo personalizado en otros tipos de datos y convertir otros tipos de datos en el tipo personalizado. Por ejemplo, un objeto <xref:System.ComponentModel.TypeConverter> definido para `MyType` permite conversiones de `MyType` a <xref:System.String> y de <xref:System.String> a `MyType`.|Permite convertir un tipo personalizado en otros tipos de datos, pero no otros tipos de datos en el tipo personalizado.|  
  
 Para obtener más información sobre cómo usar convertidores de tipos para realizar conversiones, vea <xref:System.ComponentModel.TypeConverter?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Convert?displayProperty=nameWithType>
- <xref:System.IConvertible>
- [Tablas de conversión de tipos](conversion-tables.md)
