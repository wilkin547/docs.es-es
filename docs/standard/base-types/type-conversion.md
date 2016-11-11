---
title: "Conversión de tipos"
description: "Conversión de tipos"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 07/22/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: c9a53222-89cb-47e5-983d-4f0f204e31ba
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: ba4a356921cb43b88d3ad8e6ef7487699f442385

---

# <a name="type-conversion"></a>Conversión de tipos

Cada valor tiene un tipo asociado, que define atributos como la cantidad de espacio asignado al valor, el intervalo de valores posibles que puede tener y los miembros que ofrece. Muchos valores se pueden expresar como más de un tipo. Por ejemplo, el valor `4` se puede expresar como un entero o como un valor de punto flotante. La conversión de tipo crea un valor en un nuevo tipo que es equivalente al valor de un tipo antiguo, pero no conserva necesariamente la identidad (o valor exacto) del objeto original.

.NET admite automáticamente las conversiones siguientes:

* Conversión de una clase derivada a una clase base. Esto significa, por ejemplo, que una instancia de cualquier clase o estructura se puede convertir en una instancia de tipo [Object](xref:System.Object). Esta conversión no requiere un operador de conversión.

* Conversión de una clase base a la clase derivada original. En C#, esta conversión requiere un operador de conversión. En Visual Basic, requiere el operador `CType` si `Option Strict` está activado. 

* Conversión de un tipo que implementa una interfaz a un objeto de interfaz que representa esa interfaz. Esta conversión no requiere un operador de conversión.

* Conversión de un objeto de interfaz al tipo original que implementa esa interfaz. En C#, esta conversión requiere un operador de conversión. En Visual Basic, requiere el operador `CType` si `Option Strict` está activado. 

Además de estas conversiones automáticas, .NET proporciona varias características que admiten la conversión de tipos personalizada. Entre ellas se incluyen las siguientes: 

* El operador `Implicit`, que define las conversiones de ampliación disponibles entre los tipos. Para obtener más información, consulte la sección [Conversión implícita con el operador Implicit](#implicit-conversion-with-the-implicit-operator).

* El operador `Explicit`, que define las conversiones de restricción disponibles entre los tipos. Para obtener más información, consulte la sección [Conversión explícita con el operador Explicit](#explicit-conversion-with-the-explicit-operator).

* La interfaz [IConvertible](xref:System.IConvertible), que define las conversiones en cada uno de los tipos de datos base de .NET. Para obtener más información, consulte la sección [Interfaz IConvertible](#the-iconvertible-interface).

* La clase [Convert](xref:System.Convert), que proporciona un conjunto de métodos que implementan los métodos de la interfaz `IConvertible`. Para obtener más información, consulte la sección [Clase Convert](#the-convert-class).

* La clase [TypeConverter](xref:System.ComponentModel.TypeConverter), que es una clase base que se puede extender para admitir la conversión de un tipo concreto en cualquier otro tipo. Para obtener más información, consulte la sección [Clase TypeConverter](#the-typeconverter-class).

## <a name="implicit-conversion-with-the-implicit-operator"></a>Conversión implícita con el operador Implicit

Las conversiones de ampliación implican la creación de un nuevo valor a partir del valor de un tipo existente que tiene un intervalo más restrictivo o una lista de miembros más restringida que el tipo de destino. Las conversión de ampliación no pueden producir ninguna pérdida de datos (aunque pueden producir una pérdida de precisión). Puesto que no se pueden perder datos, los compiladores pueden administrar la conversión de manera implícita o transparente, sin que sea necesario el uso de un método de conversión explícito o de un operador de conversión.

> [!NOTE]
> Aunque el código que realiza una conversión implícita puede llamar a un método de conversión o usar un operador de conversión, los compiladores que admiten las conversiones implícitas no necesitan usarlos.

Por ejemplo, el tipo [Decimal](xref:System.Decimal) admite conversiones implícitas de valores [Byte](xref:System.Byte), [Char](xref:System.Char), [Int16](xref:System.Int16), [Int32](xref:System.Int32), [Int64](xref:System.Int64), [SByte](xref:System.SByte), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32) y [UInt64](xref:System.UInt64). En el ejemplo siguiente se muestran algunas de estas conversiones implícitas al asignar valores a una variable `Decimal`.

```csharp
byte byteValue = 16;
short shortValue = -1024;
int intValue = -1034000;
long longValue = 1152921504606846976;
ulong ulongValue = UInt64.MaxValue;

decimal decimalValue;

decimalValue = byteValue;
Console.WriteLine("After assigning a {0} value, the Decimal value is {1}.", 
                  byteValue.GetType().Name, decimalValue); 

decimalValue = shortValue;
Console.WriteLine("After assigning a {0} value, the Decimal value is {1}.", 
                  shortValue.GetType().Name, decimalValue); 

decimalValue = intValue;
Console.WriteLine("After assigning a {0} value, the Decimal value is {1}.", 
                  intValue.GetType().Name, decimalValue); 

decimalValue = longValue;
Console.WriteLine("After assigning a {0} value, the Decimal value is {1}.", 
                  longValue.GetType().Name, decimalValue); 

decimalValue = ulongValue;
Console.WriteLine("After assigning a {0} value, the Decimal value is {1}.", 
                  longValue.GetType().Name, decimalValue); 
// The example displays the following output:
//    After assigning a Byte value, the Decimal value is 16.
//    After assigning a Int16 value, the Decimal value is -1024.
//    After assigning a Int32 value, the Decimal value is -1034000.
//    After assigning a Int64 value, the Decimal value is 1152921504606846976.
//    After assigning a Int64 value, the Decimal value is 18446744073709551615.
```

```vb
Dim byteValue As Byte = 16
Dim shortValue As Short = -1024
Dim intValue As Integer = -1034000
Dim longValue As Long = CLng(1024^6)
Dim ulongValue As ULong = ULong.MaxValue

Dim decimalValue As Decimal

decimalValue = byteValue
Console.WriteLine("After assigning a {0} value, the Decimal value is {1}.",
                  byteValue.GetType().Name, decimalValue) 

decimalValue = shortValue
Console.WriteLine("After assigning a {0} value, the Decimal value is {1}.",
                  shortValue.GetType().Name, decimalValue) 

decimalValue = intValue
Console.WriteLine("After assigning a {0} value, the Decimal value is {1}.",
                  intValue.GetType().Name, decimalValue) 

decimalValue = longValue
Console.WriteLine("After assigning a {0} value, the Decimal value is {1}.",
                  longValue.GetType().Name, decimalValue) 

decimalValue = ulongValue
Console.WriteLine("After assigning a {0} value, the Decimal value is {1}.",
                  longValue.GetType().Name, decimalValue) 
' The example displays the following output:
'    After assigning a Byte value, the Decimal value is 16.
'    After assigning a Int16 value, the Decimal value is -1024.
'    After assigning a Int32 value, the Decimal value is -1034000.
'    After assigning a Int64 value, the Decimal value is 1152921504606846976.
'    After assigning a Int64 value, the Decimal value is 18446744073709551615.
```

Si un compilador de un lenguaje determinado admite operadores personalizados, también puede definir conversiones implícitas en sus propios tipos personalizados. En el ejemplo siguiente se proporciona una implementación parcial de un tipo de datos de byte con signo denominado `ByteWithSign` que usa la representación de signo y magnitud. Admite la conversión implícita de valores [Byte](xref:System.Byte) y [SByte](xref:System.SByte) a valores `ByteWithSign`.

```csharp
public struct ByteWithSign
{
   private SByte signValue; 
   private Byte value;

   public static implicit operator ByteWithSign(SByte value) 
   {
      ByteWithSign newValue;
      newValue.signValue = (SByte) Math.Sign(value);
      newValue.value = (byte) Math.Abs(value);
      return newValue;
   }  

   public static implicit operator ByteWithSign(Byte value)
   {
      ByteWithSign  newValue;
      newValue.signValue = 1;
      newValue.value = value;
      return newValue;
   }

   public override string ToString()
   { 
      return (signValue * value).ToString();
   }
}
```

```vb
Public Structure ByteWithSign
   Private signValue As SByte 
   Private value As Byte

   Public Overloads Shared Widening Operator CType(value As SByte) As ByteWithSign
      Dim newValue As ByteWithSign
      newValue.signValue = CSByte(Math.Sign(value))
      newValue.value = CByte(Math.Abs(value))
      Return newValue
   End Operator  

   Public Overloads Shared Widening Operator CType(value As Byte) As ByteWithSign
      Dim NewValue As ByteWithSign
      newValue.signValue = 1
      newValue.value = value
      Return newValue
   End Operator

   Public Overrides Function ToString() As String 
      Return (signValue * value).ToString()
   End Function
End Structure
```

Después, el código de cliente puede declarar una variable `ByteWithSign` y asignarle valores [Byte](xref:System.Byte) y [SByte](xref:System.SByte) sin realizar ninguna conversión explícita ni emplear ningún operador de conversión, como se muestra en el ejemplo siguiente.

```csharp
SByte sbyteValue = -120;
ByteWithSign value = sbyteValue;
Console.WriteLine(value);
value = Byte.MaxValue;
Console.WriteLine(value);
// The example displays the following output:
//       -120
//       255
```

```vb
Dim sbyteValue As SByte = -120
Dim value As ByteWithSign = sbyteValue
Console.WriteLine(value.ToString()) 
value = Byte.MaxValue
Console.WriteLine(value.ToString()) 
' The example displays the following output:
'       -120
'       255
```

## <a name="explicit-conversion-with-the-explicit-operator"></a>Conversión explícita con el operador Explicit

Las conversiones de restricción implican la creación de un nuevo valor a partir del valor de un tipo existente que tiene un intervalo mayor o una lista de miembros mayor que el tipo de destino. Puesto que una conversión de restricción puede producir una pérdida de datos, los compiladores suelen necesitar que la conversión se haga explícita a través de una llamada a un método de conversión o a un operador de conversión. Es decir, la conversión se debe administrar explícitamente en el código de desarrollo. 

> [!NOTE]
> La finalidad principal de solicitar un método de conversión o un operador de conversión para las conversiones de restricción es que el desarrollador sea consciente de la posibilidad de que se pierdan datos o de que se produzca una excepción [OverflowException](xref:System.OverflowException), para que se pueda administrar en el código. Sin embargo, algunos compiladores pueden ser menos exigentes con este requisito. Por ejemplo, en Visual Basic, si `Option Strict` está desactivado (la configuración predeterminada), el compilador de Visual Basic intenta realizar las conversiones de restricción implícitamente.

Por ejemplo, los tipos de datos [UInt32](xref:System.UInt32), [Int64](xref:System.Int64) y [UInt64](xref:System.UInt64) tienen intervalos que superan el del tipo de datos [Int32](xref:System.Int32), como se muestra en la tabla siguiente.

Tipo | Comparación con el intervalo de Int32
---- | ------------------------------
[Int64](xref:System.Int64) | [Int64.MaxValue](xref:System.Int64.MaxValue) es mayor que [Int32.MaxValue](xref:System.Int32#System_Int32_MaxValue) e [Int64.MinValue](xref:System.Int64.MinValue) es menor (tiene un intervalo negativo mayor) que [Int32.MinValue](xref:System.Int32#System_Int32_MinValue).
[UInt32](xref:System.UInt32) | [UInt32.MaxValue](xref:System.UInt32.MaxValue) es mayor que [Int32.MaxValue](xref:System.Int32.MaxValue).
[UInt64](xref:System.UInt64) | [UInt64.MaxValue](xref:System.UInt64.MaxValue) es mayor que [Int32.MaxValue](xref:System.Int32.MaxValue).

Para administrar estas conversiones de restricción, .NET permite que los tipos definan un operador `Explicit`. Después, los compiladores de lenguaje individuales pueden implementar este operador usando su propia sintaxis o se puede llamar a un miembro de la clase [Convert](xref:System.Convert) para realizar la conversión. (Para obtener más información acerca de la clase `Convert`, consulte [Clase Convert](#the-convert-class) más adelante en este tema). En el ejemplo siguiente, se muestra el uso de las características de lenguaje para administrar la conversión explícita de estos valores enteros, que potencialmente están fuera del intervalo, a valores de tipo [Int32](xref:System.Int32). 

```csharp
long number1 = int.MaxValue + 20L;
uint number2 = int.MaxValue - 1000;
ulong number3 = int.MaxValue;

int intNumber;

try {
   intNumber = checked((int) number1);
   Console.WriteLine("After assigning a {0} value, the Integer value is {1}.", 
                     number1.GetType().Name, intNumber); 
}
catch (OverflowException) {
   if (number1 > int.MaxValue)
      Console.WriteLine("Conversion failed: {0} exceeds {1}.", 
                        number1, int.MaxValue);
   else
      Console.WriteLine("Conversion failed: {0} is less than {1}.", 
                        number1, int.MinValue);
}

try {
   intNumber = checked((int) number2);
   Console.WriteLine("After assigning a {0} value, the Integer value is {1}.", 
                     number2.GetType().Name, intNumber); 
}
catch (OverflowException) {
   Console.WriteLine("Conversion failed: {0} exceeds {1}.", 
                     number2, int.MaxValue);
}

try {
   intNumber = checked((int) number3);
   Console.WriteLine("After assigning a {0} value, the Integer value is {1}.", 
                     number3.GetType().Name, intNumber); 
}
catch (OverflowException) {
   Console.WriteLine("Conversion failed: {0} exceeds {1}.", 
                     number1, int.MaxValue);
}

// The example displays the following output:
//    Conversion failed: 2147483667 exceeds 2147483647.
//    After assigning a UInt32 value, the Integer value is 2147482647.
//    After assigning a UInt64 value, the Integer value is 2147483647.
```

```vb
Dim number1 As Long = Integer.MaxValue + 20L
Dim number2 As UInteger = Integer.MaxValue - 1000
Dim number3 As ULong = Integer.MaxValue

Dim intNumber As Integer

Try
   intNumber = CInt(number1)
   Console.WriteLine("After assigning a {0} value, the Integer value is {1}.", 
                       number1.GetType().Name, intNumber)
Catch e As OverflowException
   If number1 > Integer.MaxValue Then
      Console.WriteLine("Conversion failed: {0} exceeds {1}.", 
                                        number1, Integer.MaxValue)
   Else
      Console.WriteLine("Conversion failed: {0} is less than {1}.\n", 
                                        number1, Integer.MinValue)
   End If
End Try

Try
   intNumber = CInt(number2)
   Console.WriteLine("After assigning a {0} value, the Integer value is {1}.", 
                       number2.GetType().Name, intNumber)
Catch e As OverflowException
   Console.WriteLine("Conversion failed: {0} exceeds {1}.", 
                                     number2, Integer.MaxValue)
End Try

Try
   intNumber = CInt(number3)
   Console.WriteLine("After assigning a {0} value, the Integer value is {1}.", 
                       number3.GetType().Name, intNumber)
Catch e As OverflowException
   Console.WriteLine("Conversion failed: {0} exceeds {1}.",
                                     number1, Integer.MaxValue)
End Try
' The example displays the following output:
'    Conversion failed: 2147483667 exceeds 2147483647.
'    After assigning a UInt32 value, the Integer value is 2147482647.
'    After assigning a UInt64 value, the Integer value is 2147483647.
```

Las conversiones explícitas pueden producir resultados diferentes en los distintos lenguajes y estos resultados pueden diferir del valor devuelto por el método [Convert](xref:System.Convert) correspondiente. Por ejemplo, si el valor [Double](xref:System.Double) **12.63251** se convierte en [Int32](xref:System.Int32), tanto el método [Convert.ToInt32(Double)](xref:System.Convert.ToInt32(System.Double)) de .NET como el método `CInt` de Visual Basic redondean [Double](xref:System.Double) para devolver un valor de **13**, pero el operador `(int)` de C# trunca [Double](xref:System.Double) para devolver un valor de **12**. De manera similar, el operador `(int)` de C# no admite la conversión de booleano a entero, pero el método `CInt` de Visual Basic convierte un valor de `true` en **-1**. Por otro lado, el método [Convert.ToInt32(Boolean)](xref:System.Convert.ToInt32(System.Boolean)) convierte un valor de `true` en **1**.

La mayoría de los compiladores permiten realizar conversiones explícitas de manera comprobada o no comprobada. Cuando se realiza una conversión comprobada, se produce una excepción [OverflowException](xref:System.OverflowException) si el valor del tipo que se va a convertir está fuera del intervalo del tipo de destino. Si se realiza una conversión no comprobada en las mismas condiciones, es posible que la conversión no produzca una excepción, pero no se podrá determinar con exactitud cuál será el comportamiento y se puede obtener como resultado un valor incorrecto.

> [!NOTE]
> En C#, las conversiones comprobadas se pueden realizar usando la palabra clave `checked` junto con un operador de conversión o especificando la opción del compilador `/checked+`. Por el contrario, las conversiones no comprobadas se pueden realizar utilizando la palabra clave `unchecked` junto con el operador de conversión de tipo o especificando la opción del compilador `/checked-`. De forma predeterminada, las conversiones explícitas no se comprueban. En Visual Basic, se pueden realizar las conversiones comprobadas especificando la opción `/removeintchecks-` del compilador. Por el contrario, las conversiones no comprobadas se pueden realizar especificando la opción `/removeintchecks+` del compilador. De forma predeterminada, las conversiones explícitas se comprueban.

En el siguiente ejemplo de C# se usan las palabras clave `checked` y `unchecked` para mostrar la diferencia de comportamiento cuando un valor que está fuera del intervalo de [Byte](xref:System.Byte) se convierte en `Byte`. La conversión comprobada produce una excepción, pero la conversión no comprobada asigna [Byte.MaxValue](xref:System.Byte.MaxValue) a la variable `Byte`.

```csharp
int largeValue = Int32.MaxValue;
byte newValue;

try {
   newValue = unchecked((byte) largeValue);
   Console.WriteLine("Converted the {0} value {1} to the {2} value {3}.", 
                     largeValue.GetType().Name, largeValue,
                     newValue.GetType().Name, newValue);
}
catch (OverflowException) {
   Console.WriteLine("{0} is outside the range of the Byte data type.", 
                     largeValue);
}

try {
   newValue = checked((byte) largeValue);
   Console.WriteLine("Converted the {0} value {1} to the {2} value {3}.", 
                     largeValue.GetType().Name, largeValue,
                     newValue.GetType().Name, newValue);
}
catch (OverflowException) {
   Console.WriteLine("{0} is outside the range of the Byte data type.", 
                     largeValue);
}
// The example displays the following output:
//    Converted the Int32 value 2147483647 to the Byte value 255.
//    2147483647 is outside the range of the Byte data type.
```

Si un compilador de un lenguaje determinado admite operadores sobrecargados personalizados, también puede definir conversiones explícitas en sus propios tipos personalizados. En el ejemplo siguiente se proporciona una implementación parcial de un tipo de datos de byte con signo denominado `ByteWithSign` que usa la representación de signo y magnitud. Admite la conversión explícita de valores [Int32](xref:System.Int32) y [UInt32](xref:System.UInt32) en valores `ByteWithSign`.

```csharp
public struct ByteWithSign
{
   private SByte signValue; 
   private Byte value;

   private const byte MaxValue = byte.MaxValue;
   private const int MinValue = -1 * byte.MaxValue;

   public static explicit operator ByteWithSign(int value) 
   {
      // Check for overflow.
      if (value > ByteWithSign.MaxValue || value < ByteWithSign.MinValue)
         throw new OverflowException(String.Format("'{0}' is out of range of the ByteWithSign 
                                                   data type.", 
                                                   value));

      ByteWithSign newValue;
      newValue.signValue = (SByte) Math.Sign(value);
      newValue.value = (byte) Math.Abs(value);
      return newValue;
   }  

   public static explicit operator ByteWithSign(uint value)
   {
      if (value > ByteWithSign.MaxValue) 
         throw new OverflowException(String.Format("'{0}' is out of range of the ByteWithSign 
                                                   data type.", 
                                                   value));

      ByteWithSign newValue;
      newValue.signValue = 1;
      newValue.value = (byte) value;
      return newValue;
   }

   public override string ToString()
   { 
      return (signValue * value).ToString();
   }
}
```

```vb
Public Structure ByteWithSign
   Private signValue As SByte 
   Private value As Byte

   Private Const MaxValue As Byte = Byte.MaxValue
   Private Const MinValue As Integer = -1 * Byte.MaxValue

   Public Overloads Shared Narrowing Operator CType(value As Integer) As ByteWithSign
      ' Check for overflow.
      If value > ByteWithSign.MaxValue Or value < ByteWithSign.MinValue Then
         Throw New OverflowException(String.Format("'{0}' is out of range of the ByteWithSign 
                                                   data type.", value))
      End If

      Dim newValue As ByteWithSign

      newValue.signValue = CSByte(Math.Sign(value))
      newValue.value = CByte(Math.Abs(value))
      Return newValue
   End Operator

   Public Overloads Shared Narrowing Operator CType(value As UInteger) As ByteWithSign
      If value > ByteWithSign.MaxValue Then 
         Throw New OverflowException(String.Format("'{0}' is out of range of the ByteWithSign 
                                                   data type.", value))
      End If

      Dim NewValue As ByteWithSign

      newValue.signValue = 1
      newValue.value = CByte(value)
      Return newValue
   End Operator

   Public Overrides Function ToString() As String 
      Return (signValue * value).ToString()
   End Function
End Structure
```

Después, el código de cliente puede declarar una variable `ByteWithSign` y asignarle valores de tipo [Int32](xref:System.Int32) y [UInt32](xref:System.UInt32) si las asignaciones incluyen un operador de conversión, como se muestra en el ejemplo siguiente.

```csharp
ByteWithSign value;

try {
   int intValue = -120;
   value = (ByteWithSign) intValue;
   Console.WriteLine(value);
}
catch (OverflowException e) {
   Console.WriteLine(e.Message);
}

try {
   uint uintValue = 1024;
   value = (ByteWithSign) uintValue;
   Console.WriteLine(value);
}
catch (OverflowException e) {
    Console.WriteLine(e.Message);
}
// The example displays the following output:
//       -120
//       '1024' is out of range of the ByteWithSign data type.
```

```vb
Dim value As ByteWithSign

Try  
   Dim intValue As Integer = -120
   value = CType(intValue, ByteWithSign)
   Console.WriteLine(value) 
Catch e As OverflowException
   Console.WriteLine(e.Message)
End Try

Try
   Dim uintValue As UInteger = 1024
   value = CType(uintValue, ByteWithSign)
   Console.WriteLine(value) 
Catch e As OverflowException
   Console.WriteLine(e.Message)
End Try
' The example displays the following output:
'       -120
'       '1024' is out of range of the ByteWithSign data type.
```

## <a name="the-iconvertible-interface"></a>Interfaz IConvertible

Para admitir la conversión de cualquier tipo en un tipo base de Common Language Runtime, .NET proporciona la interfaz [IConvertible](xref:System.IConvertible). El tipo que se está implementando debe proporcionar lo siguiente:

* Un método que devuelva el objeto [TypeCode](xref:System.TypeCode) del tipo que se está implementando.

* Métodos para convertir el tipo que se está implementando en cada uno de los tipos base de Common Language Runtime ([Boolean](xref:System.Boolean), [Byte](xref:System.Byte), [DateTime](xref:System.DateTime), [Decimal](xref:System.Decimal), [Double](xref:System.Double), etc.).

* Un método de conversión generalizado para convertir una instancia del tipo que se está implementando en otro tipo concreto. Las conversiones que no se admiten deben iniciar una excepción [InvalidCastException](xref:System.InvalidCastException).

Cada tipo base de common language runtime (es decir, [Boolean](xref:System.Boolean), [Byte](xref:System.Byte), [Char](xref:System.Char), [DateTime](xref:System.DateTime), [Decimal](xref:System.Decimal), [Double](xref:System.Double), [Int16](xref:System.Int16), [Int32](xref:System.Int32), [Int64](xref:System.Int64), [SByte](xref:System.SByte), [Single](xref:System.Single), [String](xref:System.String), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32) y [UInt64](xref:System.UInt64), así como los tipos [DBNull](xref:System.DBNull) y [Enum](xref:System.Enum)) implementa la interfaz [IConvertible](xref:System.IConvertible). Pero se trata de implementaciones de interfaz explícitas; solo se puede llamar al método de conversión mediante una variable de la interfaz [IConvertible](xref:System.IConvertible), como se muestra en el ejemplo siguiente. Este ejemplo convierte un valor [Int32](xref:System.Int32) en su valor [Char](xref:System.Char) equivalente.

```csharp
int codePoint = 1067;
IConvertible iConv = codePoint;
char ch = iConv.ToChar(null);
Console.WriteLine("Converted {0} to {1}.", codePoint, ch);
```

```vb
Dim codePoint As Integer = 1067
Dim iConv As IConvertible = codePoint
Dim ch As Char = iConv.ToChar(Nothing)
Console.WriteLine("Converted {0} to {1}.", codePoint, ch)
```

El requisito de llamar al método de conversión en su interfaz, en lugar de en el tipo que se está implementando, hace que las implementaciones de interfaz explícitas resulten relativamente costosas. En su lugar, se recomienda llamar al miembro adecuado de la clase [Convert](xref:System.Convert) para convertir entre los tipos base de Common Language Runtime. Para obtener más información, consulte la próxima sección, [Clase Convert](#the-convert-class). 

> [!NOTE]
> Además de la interfaz [IConvertible](xref:System.IConvertible) y la clase [Convert](xref:System.Convert) proporcionadas por .NET, los lenguajes individuales también pueden proporcionar maneras de realizar las conversiones. Por ejemplo, C# utiliza operadores de conversión, mientras que Visual Basic utiliza funciones de conversión implementadas por el compilador como `CType`, `CInt` y `DirectCast`.

En su mayor parte, la interfaz [IConvertible](xref:System.IConvertible) está diseñada para admitir la conversión entre los tipos base de .NET. Sin embargo, la interfaz también puede implementarse por un tipo personalizado con el fin de admitir la conversión de ese tipo a otros tipos personalizados. Para obtener más información, consulte la sección [Conversiones personalizadas con el método ChangeType](#custom-conversions-with-the-changetype-method) más adelante en este tema.

## <a name="the-convert-class"></a>Clase Convert

Aunque se puede llamar a la implementación de la interfaz [IConvertible](xref:System.IConvertible) de cada tipo base para realizar una conversión de tipo, llamar a los métodos de la clase [System.Convert](xref:System.Convert) es la manera recomendada de convertir de un tipo base en otro de una manera independiente del lenguaje. Además, se puede usar el método [Convert.ChangeType(Object, Type, IFormatProvider)](xref:System.Convert.ChangeType(System.Object,System.Type,System.IFormatProvider)) para convertir de un tipo personalizado concreto a otro tipo. 

### <a name="conversions-between-base-types"></a>Conversiones entre los tipos base

La clase [Convert](xref:System.Convert) proporciona una manera independiente del lenguaje de realizar conversiones entre los tipos base y está disponible para todos los lenguajes cuyo destino es Common Language Runtime. Ofrece un conjunto completo de métodos tanto para conversiones de ampliación como de restricción e inicia una excepción [InvalidCastException](xref:System.InvalidCastException) para las conversiones que no se admiten (como la conversión de un valor [DateTime](xref:System.DateTime) a un valor entero). Las conversiones de restricción se realizan en un contexto comprobado y se inicia una excepción [OverflowException](xref:System.OverflowException) si se produce un error en la conversión.

> [!IMPORTANT]
> Puesto que la clase [Convert](xref:System.Convert) incluye métodos para efectuar la conversión directa e inversa de cada tipo base, elimina la necesidad de llamar a la implementación de interfaz explícita [IConvertible](xref:System.IConvertible) de cada tipo base.

En el ejemplo siguiente se muestra el uso de la clase [System.Convert](xref:System.Convert) para realizar varias conversiones de restricción y ampliación entre los tipos base de .NET.

```csharp
// Convert an Int32 value to a Decimal (a widening conversion).
int integralValue = 12534;
decimal decimalValue = Convert.ToDecimal(integralValue);
Console.WriteLine("Converted the {0} value {1} to " +  
                                  "the {2} value {3:N2}.", 
                                  integralValue.GetType().Name, 
                                  integralValue, 
                                  decimalValue.GetType().Name, 
                                  decimalValue);
// Convert a Byte value to an Int32 value (a widening conversion).
byte byteValue = Byte.MaxValue;
int integralValue2 = Convert.ToInt32(byteValue);                                  
Console.WriteLine("Converted the {0} value {1} to " +  
                                  "the {2} value {3:G}.", 
                                  byteValue.GetType().Name, 
                                  byteValue, 
                                  integralValue2.GetType().Name, 
                                  integralValue2);

// Convert a Double value to an Int32 value (a narrowing conversion).
double doubleValue = 16.32513e12;
try {
   long longValue = Convert.ToInt64(doubleValue);
   Console.WriteLine("Converted the {0} value {1:E} to " +  
                                     "the {2} value {3:N0}.", 
                                     doubleValue.GetType().Name, 
                                     doubleValue, 
                                     longValue.GetType().Name, 
                                     longValue);
}
catch (OverflowException) {
   Console.WriteLine("Unable to convert the {0:E} value {1}.", 
                                     doubleValue.GetType().Name, doubleValue);
}

// Convert a signed byte to a byte (a narrowing conversion).     
sbyte sbyteValue = -16;
try {
   byte byteValue2 = Convert.ToByte(sbyteValue);
   Console.WriteLine("Converted the {0} value {1} to " +  
                                     "the {2} value {3:G}.", 
                                     sbyteValue.GetType().Name, 
                                     sbyteValue, 
                                     byteValue2.GetType().Name, 
                                     byteValue2);
}
catch (OverflowException) {
   Console.WriteLine("Unable to convert the {0} value {1}.", 
                                     sbyteValue.GetType().Name, sbyteValue);
}                                         
// The example displays the following output:
//       Converted the Int32 value 12534 to the Decimal value 12,534.00.
//       Converted the Byte value 255 to the Int32 value 255.
//       Converted the Double value 1.632513E+013 to the Int64 value 16,325,130,000,000.
//       Unable to convert the SByte value -16.
```

```vb
' Convert an Int32 value to a Decimal (a widening conversion).
Dim integralValue As Integer = 12534
Dim decimalValue As Decimal = Convert.ToDecimal(integralValue)
Console.WriteLine("Converted the {0} value {1} to the {2} value {3:N2}.", 
                  integralValue.GetType().Name,
                  integralValue,
                  decimalValue.GetType().Name,
                  decimalValue)

' Convert a Byte value to an Int32 value (a widening conversion).
Dim byteValue As Byte = Byte.MaxValue
Dim integralValue2 As Integer = Convert.ToInt32(byteValue)                                  
Console.WriteLine("Converted the {0} value {1} to " + 
                                  "the {2} value {3:G}.",
                                  byteValue.GetType().Name,
                                  byteValue,
                                  integralValue2.GetType().Name,
                                  integralValue2)

' Convert a Double value to an Int32 value (a narrowing conversion).
Dim doubleValue As Double = 16.32513e12
Try
   Dim longValue As Long = Convert.ToInt64(doubleValue)
   Console.WriteLine("Converted the {0} value {1:E} to " + 
                                     "the {2} value {3:N0}.",
                                     doubleValue.GetType().Name,
                                     doubleValue,
                                     longValue.GetType().Name,
                                     longValue)
Catch e As OverflowException
   Console.WriteLine("Unable to convert the {0:E} value {1}.",
                                     doubleValue.GetType().Name, doubleValue)
End Try                                                             

' Convert a signed byte to a byte (a narrowing conversion).     
Dim sbyteValue As SByte = -16
Try
   Dim byteValue2 As Byte = Convert.ToByte(sbyteValue)
   Console.WriteLine("Converted the {0} value {1} to " + 
                                     "the {2} value {3:G}.",
                                     sbyteValue.GetType().Name,
                                     sbyteValue,
                                     byteValue2.GetType().Name,
                                     byteValue2)
Catch e As OverflowException
   Console.WriteLine("Unable to convert the {0} value {1}.",
                                     sbyteValue.GetType().Name, sbyteValue)
End Try 
' The example displays the following output:
'       Converted the Int32 value 12534 to the Decimal value 12,534.00.
'       Converted the Byte value 255 to the Int32 value 255.
'       Converted the Double value 1.632513E+013 to the Int64 value 16,325,130,000,000.
'       Unable to convert the SByte value -16.
```

En algunos casos, en especial al efectuar conversiones directas e inversas de valores de punto flotante, una conversión puede conllevar una pérdida de precisión, aunque no se inicie una excepción [OverflowException](xref:System.OverflowException). En el ejemplo siguiente se muestra esta pérdida de precisión. En el primer caso, un valor [Decimal](xref:System.Decimal) tiene menos precisión (menos dígitos significativos) cuando se convierte en el tipo [Double](xref:System.Double). En el segundo caso, un valor [Double](xref:System.Double) se redondea de **42,72** a **43** para completar la conversión.

```csharp
double doubleValue; 

// Convert a Double to a Decimal.
decimal decimalValue = 13956810.96702888123451471211m;
doubleValue = Convert.ToDouble(decimalValue);
Console.WriteLine("{0} converted to {1}.", decimalValue, doubleValue);

doubleValue = 42.72;
try {
   int integerValue = Convert.ToInt32(doubleValue);
   Console.WriteLine("{0} converted to {1}.", 
                                     doubleValue, integerValue);
}
catch (OverflowException) {      
   Console.WriteLine("Unable to convert {0} to an integer.", 
                                     doubleValue);
}   
// The example displays the following output:
//       13956810.96702888123451471211 converted to 13956810.9670289.
//       42.72 converted to 43.
```

```vb
Dim doubleValue As Double 

' Convert a Double to a Decimal.
Dim decimalValue As Decimal = 13956810.96702888123451471211d
doubleValue = Convert.ToDouble(decimalValue)
Console.WriteLine("{0} converted to {1}.", decimalValue, doubleValue)

doubleValue = 42.72
Try
   Dim integerValue As Integer = Convert.ToInt32(doubleValue)
   Console.WriteLine("{0} converted to {1}.",
                                     doubleValue, integerValue)
Catch e As OverflowException
   Console.WriteLine("Unable to convert {0} to an integer.",
                                     doubleValue)
End Try   
' The example displays the following output:
'       13956810.96702888123451471211 converted to 13956810.9670289.
'       42.72 converted to 43.
```

Para obtener una tabla en la que se muestra una lista de conversiones de restricción y ampliación admitidas por la clase [Convert](xref:System.Convert), consulte [Tablas de conversiones de tipos](conversion-tables.md).

### <a name="custom-conversions-with-the-changetype-method"></a>Conversiones personalizadas con el método ChangeType

Además de admitir las conversiones en cada uno de los tipos base, la clase [Convert](xref:System.Convert) se puede usar para convertir un tipo personalizado en uno o varios tipos predefinidos. Esta conversión se realiza mediante el método [Convert.ChangeType(Object, Type, IFormatProvider)](xref:System.Convert.ChangeType(System.Object,System.Type,System.IFormatProvider)), que a su vez contiene una llamada al método [IConvertible.ToType](xref:System.IConvertible.ToType(System.Type,System.IFormatProvider)) del parámetro de valor. Esto significa que el objeto representado por el parámetro de valor debe proporcionar una implementación de la interfaz [IConvertible](xref:System.IConvertible).

> [!NOTE]
> Dado que los métodos [Convert.ChangeType(Object, Type)](xref:System.Convert.ChangeType(System.Object,System.Type)) y [Convert.ChangeType(Object, Type, IFormatProvider)](xref:System.Convert.ChangeType(System.Object,System.Type,System.IFormatProvider)) usan un objeto [Type](xref:System.Type) para especificar el tipo de destino al que se convierte el valor, se pueden usar para realizar una conversión dinámica a un objeto cuyo tipo se desconoce en tiempo de compilación. Pero observe que la implementación del valor de [IConvertible](xref:System.IConvertible) aún debe admitir esta conversión. 

En el ejemplo siguiente se muestra una posible implementación de la interfaz [IConvertible](xref:System.IConvertible) que permite convertir un objeto `TemperatureCelsius` en un objeto `TemperatureFahrenheit` y viceversa. El ejemplo define una clase base, `Temperature`, que implementa la interfaz [IConvertible](xref:System.IConvertible) e invalida el método [Object.ToString](xref:System.Object.ToString). Cada una de las clases derivadas `TemperatureCelsius` y `TemperatureFahrenheit` invalida los métodos `ToType` y `ToString` de la clase base. 

```csharp
using System;

public abstract class Temperature : IConvertible
{
   protected decimal temp;

   public Temperature(decimal temperature)
   {
      this.temp = temperature;
   }

   public decimal Value
   { 
      get { return this.temp; } 
      set { this.temp = Value; }        
   }

   public override string ToString()
   {
      return temp.ToString(null as IFormatProvider) + "º";
   }

   // IConvertible implementations.
   public TypeCode GetTypeCode() { 
      return TypeCode.Object;
   }   

   public bool ToBoolean(IFormatProvider provider) {
      throw new InvalidCastException(String.Format("Temperature-to-Boolean conversion is not supported."));
   }

   public byte ToByte(IFormatProvider provider) {
      if (temp < Byte.MinValue || temp > Byte.MaxValue)
         throw new OverflowException(String.Format("{0} is out of range of the Byte data type.", temp));
      else
         return (byte) temp;
   }

   public char ToChar(IFormatProvider provider) {
      throw new InvalidCastException("Temperature-to-Char conversion is not supported.");
   }

   public DateTime ToDateTime(IFormatProvider provider) {
      throw new InvalidCastException("Temperature-to-DateTime conversion is not supported.");
   }

   public decimal ToDecimal(IFormatProvider provider) {
      return temp;
   }

   public double ToDouble(IFormatProvider provider) {
      return (double) temp;
   }

   public short ToInt16(IFormatProvider provider) {
      if (temp < Int16.MinValue || temp > Int16.MaxValue)
         throw new OverflowException(String.Format("{0} is out of range of the Int16 data type.", temp));
      else
         return (short) Math.Round(temp);
   }

   public int ToInt32(IFormatProvider provider) {
      if (temp < Int32.MinValue || temp > Int32.MaxValue)
         throw new OverflowException(String.Format("{0} is out of range of the Int32 data type.", temp));
      else
         return (int) Math.Round(temp);
   }

   public long ToInt64(IFormatProvider provider) {
      if (temp < Int64.MinValue || temp > Int64.MaxValue)
         throw new OverflowException(String.Format("{0} is out of range of the Int64 data type.", temp));
      else
         return (long) Math.Round(temp);
   }

   public sbyte ToSByte(IFormatProvider provider) {
      if (temp < SByte.MinValue || temp > SByte.MaxValue)
         throw new OverflowException(String.Format("{0} is out of range of the SByte data type.", temp));
      else
         return (sbyte) temp;
   }

   public float ToSingle(IFormatProvider provider) {
      return (float) temp;
   }

   public virtual string ToString(IFormatProvider provider) {
      return temp.ToString(provider) + "°";
   }

   // If conversionType is implemented by another IConvertible method, call it.
   public virtual object ToType(Type conversionType, IFormatProvider provider) {
      switch (Type.GetTypeCode(conversionType))
      {
         case TypeCode.Boolean:
            return this.ToBoolean(provider);
         case TypeCode.Byte:
            return this.ToByte(provider);
         case TypeCode.Char:
            return this.ToChar(provider);
         case TypeCode.DateTime:
            return this.ToDateTime(provider);
         case TypeCode.Decimal:
            return this.ToDecimal(provider);
         case TypeCode.Double:
            return this.ToDouble(provider);
         case TypeCode.Empty:
            throw new NullReferenceException("The target type is null.");
         case TypeCode.Int16:
            return this.ToInt16(provider);
         case TypeCode.Int32:
            return this.ToInt32(provider);
         case TypeCode.Int64:
            return this.ToInt64(provider);
         case TypeCode.Object:
            // Leave conversion of non-base types to derived classes.
            throw new InvalidCastException(String.Format("Cannot convert from Temperature to {0}.", 
                                           conversionType.Name));
         case TypeCode.SByte:
            return this.ToSByte(provider);
         case TypeCode.Single:
            return this.ToSingle(provider);
         case TypeCode.String:
            IConvertible iconv = this;
            return iconv.ToString(provider);
         case TypeCode.UInt16:
            return this.ToUInt16(provider);
         case TypeCode.UInt32:
            return this.ToUInt32(provider);
         case TypeCode.UInt64:
            return this.ToUInt64(provider);
         default:
            throw new InvalidCastException("Conversion not supported.");
      }
   }

   public ushort ToUInt16(IFormatProvider provider) {
      if (temp < UInt16.MinValue || temp > UInt16.MaxValue)
         throw new OverflowException(String.Format("{0} is out of range of the UInt16 data type.", temp));
      else
         return (ushort) Math.Round(temp);
   }

   public uint ToUInt32(IFormatProvider provider) {
      if (temp < UInt32.MinValue || temp > UInt32.MaxValue)
         throw new OverflowException(String.Format("{0} is out of range of the UInt32 data type.", temp));
      else
         return (uint) Math.Round(temp);
   }

   public ulong ToUInt64(IFormatProvider provider) {
      if (temp < UInt64.MinValue || temp > UInt64.MaxValue)
         throw new OverflowException(String.Format("{0} is out of range of the UInt64 data type.", temp));
      else
         return (ulong) Math.Round(temp);
   }
}

public class TemperatureCelsius : Temperature, IConvertible
{
   public TemperatureCelsius(decimal value) : base(value)
   {
   }

   // Override ToString methods.
   public override string ToString()
   {
      return this.ToString(null);
   }

   public override string ToString(IFormatProvider provider)
   {
      return temp.ToString(provider) + "°C"; 
   }

   // If conversionType is a implemented by another IConvertible method, call it.
   public override object ToType(Type conversionType, IFormatProvider provider) {
      // For non-objects, call base method.
      if (Type.GetTypeCode(conversionType) != TypeCode.Object) {
         return base.ToType(conversionType, provider);
      }   
      else
      {   
         if (conversionType.Equals(typeof(TemperatureCelsius)))
            return this;
         else if (conversionType.Equals(typeof(TemperatureFahrenheit)))
            return new TemperatureFahrenheit((decimal) this.temp * 9 / 5 + 32);
         else
            throw new InvalidCastException(String.Format("Cannot convert from Temperature to {0}.", 
                                           conversionType.Name));
      }
   }
}

public class TemperatureFahrenheit : Temperature, IConvertible 
{
   public TemperatureFahrenheit(decimal value) : base(value)
   {
   }

   // Override ToString methods.
   public override string ToString()
   {
      return this.ToString(null);
   }

   public override string ToString(IFormatProvider provider)
   {
      return temp.ToString(provider) + "°F"; 
   }

   public override object ToType(Type conversionType, IFormatProvider provider)
   { 
      // For non-objects, call base methood.
      if (Type.GetTypeCode(conversionType) != TypeCode.Object) {
         return base.ToType(conversionType, provider);
      }   
      else
      {   
         // Handle conversion between derived classes.
         if (conversionType.Equals(typeof(TemperatureFahrenheit))) 
            return this;
         else if (conversionType.Equals(typeof(TemperatureCelsius)))
            return new TemperatureCelsius((decimal) (this.temp - 32) * 5 / 9);
         // Unspecified object type: throw an InvalidCastException.
         else
            throw new InvalidCastException(String.Format("Cannot convert from Temperature to {0}.", 
                                           conversionType.Name));
      }                                 
   }
}
```

```vb
Public MustInherit Class Temperature
   Implements IConvertible

   Protected temp As Decimal

   Public Sub New(temperature As Decimal)
      Me.temp = temperature
   End Sub

   Public Property Value As Decimal
      Get 
         Return Me.temp
      End Get
      Set
         Me.temp = Value
      End Set   
   End Property

   Public Overrides Function ToString() As String
      Return temp.ToString() & "º"
   End Function

   ' IConvertible implementations.
   Public Function GetTypeCode() As TypeCode Implements IConvertible.GetTypeCode
      Return TypeCode.Object
   End Function   

   Public Function ToBoolean(provider As IFormatProvider) As Boolean Implements IConvertible.ToBoolean
      Throw New InvalidCastException(String.Format("Temperature-to-Boolean conversion is not supported."))
   End Function

   Public Function ToByte(provider As IFormatProvider) As Byte Implements IConvertible.ToByte
      If temp < Byte.MinValue Or temp > Byte.MaxValue Then
         Throw New OverflowException(String.Format("{0} is out of range of the Byte data type.", temp))
      Else
         Return CByte(temp)
      End If    
   End Function

   Public Function ToChar(provider As IFormatProvider) As Char Implements IConvertible.ToChar
      Throw New InvalidCastException("Temperature-to-Char conversion is not supported.")
   End Function

   Public Function ToDateTime(provider As IFormatProvider) As DateTime Implements IConvertible.ToDateTime
      Throw New InvalidCastException("Temperature-to-DateTime conversion is not supported.")
   End Function

   Public Function ToDecimal(provider As IFormatProvider) As Decimal Implements IConvertible.ToDecimal
      Return temp
   End Function

   Public Function ToDouble(provider As IFormatProvider) As Double Implements IConvertible.ToDouble
      Return CDbl(temp)
   End Function

   Public Function ToInt16(provider As IFormatProvider) As Int16 Implements IConvertible.ToInt16
      If temp < Int16.MinValue Or temp > Int16.MaxValue Then
         Throw New OverflowException(String.Format("{0} is out of range of the Int16 data type.", temp))
      End If
      Return CShort(Math.Round(temp))
   End Function

   Public Function ToInt32(provider As IFormatProvider) As Int32 Implements IConvertible.ToInt32
      If temp < Int32.MinValue Or temp > Int32.MaxValue Then
         Throw New OverflowException(String.Format("{0} is out of range of the Int32 data type.", temp))
      End If
      Return CInt(Math.Round(temp))
   End Function

   Public Function ToInt64(provider As IFormatProvider) As Int64 Implements IConvertible.ToInt64
      If temp < Int64.MinValue Or temp > Int64.MaxValue Then
         Throw New OverflowException(String.Format("{0} is out of range of the Int64 data type.", temp))
      End If
      Return CLng(Math.Round(temp))
   End Function

   Public Function ToSByte(provider As IFormatProvider) As SByte Implements IConvertible.ToSByte
      If temp < SByte.MinValue Or temp > SByte.MaxValue Then
         Throw New OverflowException(String.Format("{0} is out of range of the SByte data type.", temp))
      Else
         Return CSByte(temp)
      End If    
   End Function

   Public Function ToSingle(provider As IFormatProvider) As Single Implements IConvertible.ToSingle
      Return CSng(temp)
   End Function

   Public Overridable Overloads Function ToString(provider As IFormatProvider) As String Implements IConvertible.ToString
      Return temp.ToString(provider) & " °C"
   End Function

   ' If conversionType is a implemented by another IConvertible method, call it.
   Public Overridable Function ToType(conversionType As Type, provider As IFormatProvider) As Object Implements IConvertible.ToType
      Select Case Type.GetTypeCode(conversionType)
         Case TypeCode.Boolean
            Return Me.ToBoolean(provider)
         Case TypeCode.Byte
            Return Me.ToByte(provider)
         Case TypeCode.Char
            Return Me.ToChar(provider)   
         Case TypeCode.DateTime
            Return Me.ToDateTime(provider)
         Case TypeCode.Decimal
            Return Me.ToDecimal(provider)
         Case TypeCode.Double
            Return Me.ToDouble(provider)
         Case TypeCode.Empty
            Throw New NullReferenceException("The target type is null.")
         Case TypeCode.Int16
            Return Me.ToInt16(provider)
         Case TypeCode.Int32
            Return Me.ToInt32(provider)
         Case TypeCode.Int64
            Return Me.ToInt64(provider)
         Case TypeCode.Object
            ' Leave conversion of non-base types to derived classes.
            Throw New InvalidCastException(String.Format("Cannot convert from Temperature to {0}.", _
                                           conversionType.Name))
         Case TypeCode.SByte
            Return Me.ToSByte(provider)
         Case TypeCode.Single
            Return Me.ToSingle(provider)
         Case TypeCode.String
            Return Me.ToString(provider)
         Case TypeCode.UInt16
            Return Me.ToUInt16(provider)
         Case TypeCode.UInt32
            Return Me.ToUInt32(provider)
         Case TypeCode.UInt64
            Return Me.ToUInt64(provider)
         Case Else
            Throw New InvalidCastException("Conversion not supported.")   
      End Select
   End Function

   Public Function ToUInt16(provider As IFormatProvider) As UInt16 Implements IConvertible.ToUInt16
      If temp < UInt16.MinValue Or temp > UInt16.MaxValue Then
         Throw New OverflowException(String.Format("{0} is out of range of the UInt16 data type.", temp))
      End If
      Return CUShort(Math.Round(temp))
   End Function

   Public Function ToUInt32(provider As IFormatProvider) As UInt32 Implements IConvertible.ToUInt32
      If temp < UInt32.MinValue Or temp > UInt32.MaxValue Then
         Throw New OverflowException(String.Format("{0} is out of range of the UInt32 data type.", temp))
      End If
      Return CUInt(Math.Round(temp))
   End Function

   Public Function ToUInt64(provider As IFormatProvider) As UInt64 Implements IConvertible.ToUInt64
      If temp < UInt64.MinValue Or temp > UInt64.MaxValue Then
         Throw New OverflowException(String.Format("{0} is out of range of the UInt64 data type.", temp))
      End If
      Return CULng(Math.Round(temp))
   End Function
End Class

Public Class TemperatureCelsius : Inherits Temperature : Implements IConvertible
   Public Sub New(value As Decimal)
      MyBase.New(value)
   End Sub

   ' Override ToString methods.
   Public Overrides Function ToString() As String
      Return Me.ToString(Nothing)
   End Function

   Public Overrides Function ToString(provider As IFormatProvider ) As String
      Return temp.ToString(provider) + "°C" 
   End Function

  ' If conversionType is a implemented by another IConvertible method, call it.
   Public Overrides Function ToType(conversionType As Type, provider As IFormatProvider) As Object
      ' For non-objects, call base method.
      If Type.GetTypeCode(conversionType) <> TypeCode.Object Then
         Return MyBase.ToType(conversionType, provider)
      Else   
         If conversionType.Equals(GetType(TemperatureCelsius)) Then
            Return Me
         ElseIf conversionType.Equals(GetType(TemperatureFahrenheit))
            Return New TemperatureFahrenheit(CDec(Me.temp * 9 / 5 + 32))
         ' Unspecified object type: throw an InvalidCastException.
         Else
            Throw New InvalidCastException(String.Format("Cannot convert from Temperature to {0}.", _ 
                                           conversionType.Name))
         End If
      End If                                  
   End Function
End Class

Public Class TemperatureFahrenheit : Inherits Temperature : Implements IConvertible
   Public Sub New(value As Decimal)
      MyBase.New(value)
   End Sub

   ' Override ToString methods.
   Public Overrides Function ToString() As String
      Return Me.ToString(Nothing)
   End Function

   Public Overrides Function ToString(provider As IFormatProvider ) As String
      Return temp.ToString(provider) + "°F" 
   End Function

   Public Overrides Function ToType(conversionType As Type, provider As IFormatProvider) As Object
      ' For non-objects, call base methood.
      If Type.GetTypeCode(conversionType) <> TypeCode.Object Then
         Return MyBase.ToType(conversionType, provider)
      Else   
         ' Handle conversion between derived classes.
         If conversionType.Equals(GetType(TemperatureFahrenheit)) Then 
            Return Me
         ElseIf conversionType.Equals(GetType(TemperatureCelsius))
            Return New TemperatureCelsius(CDec((MyBase.temp - 32) * 5 / 9))
         ' Unspecified object type: throw an InvalidCastException.
         Else
            Throw New InvalidCastException(String.Format("Cannot convert from Temperature to {0}.", _
                                           conversionType.Name))
         End If
      End If                                  
   End Function
End Class
```

En el ejemplo siguiente se muestran varias llamadas a estas implementaciones de [IConvertible](xref:System.IConvertible) para convertir los objetos `TemperatureCelsius` en objetos `TemperatureFahrenheit` y viceversa.

```csharp
TemperatureCelsius tempC1 = new TemperatureCelsius(0);
TemperatureFahrenheit tempF1 = (TemperatureFahrenheit) Convert.ChangeType(tempC1, typeof(TemperatureFahrenheit), null);
Console.WriteLine("{0} equals {1}.", tempC1, tempF1);
TemperatureCelsius tempC2 = (TemperatureCelsius) Convert.ChangeType(tempC1, typeof(TemperatureCelsius), null);
Console.WriteLine("{0} equals {1}.", tempC1, tempC2);
TemperatureFahrenheit tempF2 = new TemperatureFahrenheit(212);
TemperatureCelsius tempC3 = (TemperatureCelsius) Convert.ChangeType(tempF2, typeof(TemperatureCelsius), null);
Console.WriteLine("{0} equals {1}.", tempF2, tempC3);
TemperatureFahrenheit tempF3 = (TemperatureFahrenheit) Convert.ChangeType(tempF2, typeof(TemperatureFahrenheit), null);
Console.WriteLine("{0} equals {1}.", tempF2, tempF3);
// The example displays the following output:
//       0°C equals 32°F.
//       0°C equals 0°C.
//       212°F equals 100°C.
//       212°F equals 212°F.
```

```vb
Dim tempC1 As New TemperatureCelsius(0)
Dim tempF1 As TemperatureFahrenheit = CType(Convert.ChangeType(tempC1, GetType(TemperatureFahrenheit), Nothing), TemperatureFahrenheit)
Console.WriteLine("{0} equals {1}.", tempC1, tempF1) 
Dim tempC2 As TemperatureCelsius = CType(Convert.ChangeType(tempC1, GetType(TemperatureCelsius), Nothing), TemperatureCelsius)
Console.WriteLine("{0} equals {1}.", tempC1, tempC2) 
Dim tempF2 As New TemperatureFahrenheit(212)
Dim tempC3 As TEmperatureCelsius = CType(Convert.ChangeType(tempF2, GEtType(TemperatureCelsius), Nothing), TemperatureCelsius)
Console.WriteLine("{0} equals {1}.", tempF2, tempC3) 
Dim tempF3 As TemperatureFahrenheit = CType(Convert.ChangeType(tempF2, GetType(TemperatureFahrenheit), Nothing), TemperatureFahrenheit)
Console.WriteLine("{0} equals {1}.", tempF2, tempF3)
' The example displays the following output:
'       0°C equals 32°F.
'       0°C equals 0°C.
'       212°F equals 100°C.
'       212°F equals 212°F.
```

## <a name="the-typeconverter-class"></a>Clase TypeConverter

.NET también permite definir un convertidor de tipos para un tipo personalizado extendiendo la clase [System.ComponentModel.TypeConverter](xref:System.ComponentModel.TypeConverter) y asociando el convertidor de tipos al tipo por medio de un atributo [System.ComponentModel.TypeConverterAttribute](xref:System.ComponentModel.TypeConverterAttribute). En la tabla siguiente se resaltan las diferencias entre este enfoque y la implementación de la interfaz [IConvertible](xref:System.IConvertible) para un tipo personalizado.

> [!NOTE]
> Se puede proporcionar compatibilidad en tiempo de diseño para un tipo personalizado sólo si se ha definido un convertidor de tipos para éste.

Conversión mediante TypeConverter | Conversión mediante IConvertible
------------------------------ | -----------------------------
Se implementa para un tipo personalizado derivando una clase independiente de [TypeConverter](xref:System.ComponentModel.TypeConverter). Esta clase derivada se asocia al tipo personalizado aplicando un atributo [TypeConverterAttribute](xref:System.ComponentModel.TypeConverterAttribute). | Se implementa mediante un tipo personalizado para realizar la conversión. Un usuario del tipo invoca un método de conversión de [IConvertible](xref:System.IConvertible) para el tipo.
Se puede utilizar en tiempo de diseño y en tiempo de ejecución. | Sólo se puede utilizar en tiempo de ejecución.
Usa la reflexión; por tanto, es más lenta que la conversión mediante [IConvertible](xref:System.IConvertible). | No utiliza la reflexión.
Permite realizar conversiones bidireccionales; es decir, convertir el tipo personalizado en otros tipos de datos y convertir otros tipos de datos en el tipo personalizado. Por ejemplo, un [TypeConverter](xref:System.ComponentModel.TypeConverter) definido para `MyType` permite conversiones de `MyType` a [String](xref:System.String) y de [String](xref:System.String) a `MyType`. | Permite convertir un tipo personalizado en otros tipos de datos, pero no otros tipos de datos en el tipo personalizado.

Para obtener más información acerca de cómo usar convertidores de tipos para realizar conversiones, consulte [System.ComponentModel.TypeConverter](xref:System.ComponentModel.TypeConverter).

## <a name="see-also"></a>Vea también

[System.Convert](xref:System.Convert)

[IConvertible](xref:System.IConvertible)

[Tablas de conversión de tipos](conversion-tables.md)


<!--HONumber=Nov16_HO1-->


