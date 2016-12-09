---
title: Usar la clase StringBuilder
description: Usar la clase StringBuilder
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: f4f5d1c7-d84d-4867-810f-2708cd6de0da
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: 2c42a4ac5fcd889eedea27b54b249f48c4848c88

---

# <a name="using-the-stringbuilder-class"></a>Usar la clase StringBuilder

El objeto [String](xref:System.String) es inmutable. Cada vez que se usa uno de los métodos de la clase [System.String](xref:System.String), se crea un nuevo objeto de cadena en la memoria, lo que requiere una nueva asignación de espacio para ese objeto. En las situaciones en las que es necesario realizar modificaciones repetidas en una cadena, la sobrecarga asociada a la creación de un nuevo objeto [String](xref:System.String) puede disminuir el rendimiento. La clase [System.Text.StringBuilder](xref:System.Text.StringBuilder) se puede usar para modificar una cadena sin crear un objeto nuevo. Por ejemplo, el uso de la clase [StringBuilder](xref:System.Text.StringBuilder) puede mejorar el rendimiento al concatenar muchas cadenas en un bucle.

## <a name="importing-the-systemtext-namespace"></a>Importar el espacio de nombres System.Text

La clase [StringBuilder](xref:System.Text.StringBuilder) clase se encuentra en el espacio de nombres [System.Text](xref:System.Text). Para evitar proporcionar un nombre de tipo completo en el código, se puede importar el espacio de nombres [System.Text](xref:System.Text): 

```csharp
using System;
using System.Text;
```

```vb
Imports System.Text
```

## <a name="instantiating-a-stringbuilder-object"></a>Crear instancias de un objeto StringBuilder

Para crear una nueva instancia de la clase [StringBuilder](xref:System.Text.StringBuilder), inicialice la variable con uno de los métodos de constructor sobrecargado, como se muestra en el ejemplo siguiente.

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
```

## <a name="setting-the-capacity-and-length"></a>Configurar la capacidad y la longitud

Aunque [StringBuilder](xref:System.Text.StringBuilder) es un objeto dinámico que permite expandir el número de caracteres de la cadena que encapsula, se puede especificar un valor para el número máximo de caracteres que puede contener. Este valor se conoce como la capacidad del objeto y no debe confundirse con la longitud de la cadena que el objeto [StringBuilder](xref:System.Text.StringBuilder) actual contiene. Por ejemplo, podría crear una nueva instancia de la clase [StringBuilder](xref:System.Text.StringBuilder) con la cadena "Hello" que tiene una longitud de 5, y podría especificar que el objeto tiene una capacidad máxima de 25. Al modificar [StringBuilder](xref:System.Text.StringBuilder), este no reasigna el tamaño para sí mismo hasta que se alcanza la capacidad. Cuando esto sucede, el nuevo espacio se asigna automáticamente y se duplica la capacidad. La capacidad de la clase [StringBuilder](xref:System.Text.StringBuilder) se puede especificar con uno de los constructores sobrecargados. En el ejemplo siguiente se especifica que el objeto `MyStringBuilder` se puede expandir hasta un máximo de 25 espacios.

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!", 25);
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!", 25) 
```

Además, se puede usar la propiedad de lectura y escritura [Capacity](xref:System.Text.StringBuilder.Capacity) para establecer la longitud máxima del objeto. En el ejemplo siguiente se usa la propiedad [Capacity](xref:System.Text.StringBuilder.Capacity) para definir la longitud máxima del objeto.

```csharp
MyStringBuilder.Capacity = 25;
```

```vb
MyStringBuilder.Capacity = 25
```

El método [EnsureCapacity](xref:System.Text.StringBuilder.EnsureCapacity(System.Int32)) se puede usar para comprobar la capacidad del objeto [StringBuilder](xref:System.Text.StringBuilder) actual. Si la capacidad es mayor que el valor transmitido, no se realiza ningún cambio, pero si es menor que este, la capacidad actual se cambia para que coincida con el valor en cuestión.

También se puede ver o establecer la propiedad [Length](xref:System.Text.StringBuilder.Length). Si la propiedad [Length](xref:System.Text.StringBuilder.Length) se establece en un valor mayor que el de la propiedad [Capacity](xref:System.Text.StringBuilder.Capacity), la propiedad [Capacity](xref:System.Text.StringBuilder.Capacity) se cambia automáticamente al mismo valor de la propiedad [Length](xref:System.Text.StringBuilder.Length). Si la propiedad [Length](xref:System.Text.StringBuilder.Length) se establece en un valor menor que la longitud de la cadena de [StringBuilder](xref:System.Text.StringBuilder) actual, se acorta la cadena.

## <a name="modifying-the-stringbuilder-string"></a>Modificar la cadena StringBuilder

En la tabla siguiente se enumeran los métodos que se pueden usar para modificar el contenido de [StringBuilder](xref:System.Text.StringBuilder).

Nombre del método | Uso
----------- | ---
[StringBuilder.Append](xref:System.Text.StringBuilder.Append(System.Char)) | Anexa información al final del objeto [StringBuilder](xref:System.Text.StringBuilder) actual.
[StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object)) | Reemplaza a un especificador de formato que se pasa en una cadena con texto con formato
[StringBuilder.Insert](xref:System.Text.StringBuilder.Insert(System.Int32,System.Char)) | Inserta una cadena o un objeto en el índice especificado del elemento [StringBuilder](xref:System.Text.StringBuilder) actual.
[StringBuilder.Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32)) | Quita el número de caracteres especificado del objeto [StringBuilder](xref:System.Text.StringBuilder) actual.
[StringBuilder.Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char)) | Reemplaza un carácter concreto en un índice especificado.

### <a name="append"></a>Anexar

El método [StringBuilder.Append](xref:System.Text.StringBuilder.Append(System.Char)) se puede usar para agregar texto o la representación de cadena de un objeto al final de una cadena representada por el objeto [StringBuilder](xref:System.Text.StringBuilder) actual. En el ejemplo siguiente, se inicializa [StringBuilder](xref:System.Text.StringBuilder) en "Hello World" y, después, se anexa texto al final del objeto. El espacio se asigna automáticamente según sea necesario.

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
MyStringBuilder.Append(" What a beautiful day.");
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Hello World! What a beautiful day.
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
MyStringBuilder.Append(" What a beautiful day.")
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'       Hello World! What a beautiful day.
```

### <a name="appendformat"></a>AppendFormat

El método [StringBuilder.AppendFormat](xref:System.Text.StringBuilder.AppendFormat(System.IFormatProvider,System.String,System.Object)) agrega texto al final del objeto [StringBuilder](xref:System.Text.StringBuilder). Admite la característica de formatos compuestos (para obtener más información, consulte [Formatos compuestos](composite-format.md)) mediante la llamada a la implementación de [IFormattable](xref:System.IFormattable) del objeto u objetos a los que se va a dar formato. Por tanto, acepta las cadenas de formato estándar para valores numéricos, de fecha y hora y de enumeración; las cadenas de formato personalizado para valores numéricos y de fecha y hora; y las cadenas de formato definidas para los tipos personalizados. (Para obtener información acerca del formato, consulte [Aplicar formato a tipos](formatting-types.md).) Este método se puede usar para personalizar el formato de las variables y anexar esos valores a [StringBuilder](xref:System.Text.StringBuilder). En el ejemplo siguiente se usa el método AppendFormat para colocar un valor entero con formato de valor de divisa al final de un objeto [StringBuilder](xref:System.Text.StringBuilder).

```csharp
int MyInt = 25; 
StringBuilder MyStringBuilder = new StringBuilder("Your total is ");
MyStringBuilder.AppendFormat("{0:C} ", MyInt);
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Your total is $25.00
```

```vb
Dim MyInt As Integer = 25
Dim MyStringBuilder As New StringBuilder("Your total is ")
MyStringBuilder.AppendFormat("{0:C} ", MyInt)
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'     Your total is $25.00 
```

### <a name="insert"></a>Insertar

El método [StringBuilder.Insert](xref:System.Text.StringBuilder.Insert(System.Int32,System.Char)) agrega una cadena u objeto en una posición especificada del objeto [StringBuilder](xref:System.Text.StringBuilder) actual. En el ejemplo siguiente se usa este método para insertar una palabra en la sexta posición de un objeto [StringBuilder](xref:System.Text.StringBuilder).

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
MyStringBuilder.Insert(6,"Beautiful ");
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Hello Beautiful World!
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
MyStringBuilder.Insert(6, "Beautiful ")
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'      Hello Beautiful World!
```

### <a name="remove"></a>Quitar

El método [StringBuilder.Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32)) se puede usar para quitar un número de caracteres especificado del objeto [StringBuilder](xref:System.Text.StringBuilder), a partir de un índice de base cero definido. En el ejemplo siguiente se usa el método [Remove](xref:System.Text.StringBuilder.Remove(System.Int32,System.Int32)) para acortar un objeto [StringBuilder](xref:System.Text.StringBuilder).

```csharp
StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
MyStringBuilder.Remove(5,7);
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Hello
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
MyStringBuilder.Remove(5, 7)
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'       Hello
```

### <a name="replace"></a>Reemplazar

El método [StringBuilder.Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char)) | Reemplaza un carácter especificado en el índice especificado.
se puede usar para reemplazar caracteres del objeto [StringBuilder](xref:System.Text.StringBuilder) por otro carácter especificado. En el ejemplo siguiente se usa el método [Replace](xref:System.Text.StringBuilder.Replace(System.Char,System.Char)) | Reemplaza un carácter especificado en el índice especificado.
para buscar todas las instancias del carácter de signo de exclamación (!) y reemplazarlas por el carácter de signo de interrogación (?) en un objeto [StringBuilder](xref:System.Text.StringBuilder).
 
 ```csharp
 StringBuilder MyStringBuilder = new StringBuilder("Hello World!");
MyStringBuilder.Replace('!', '?');
Console.WriteLine(MyStringBuilder);
// The example displays the following output:
//       Hello World?
```

```vb
Dim MyStringBuilder As New StringBuilder("Hello World!")
MyStringBuilder.Replace("!"c, "?"c)
Console.WriteLine(MyStringBuilder)
' The example displays the following output:
'       Hello World?
```

## <a name="converting-a-stringbuilder-object-to-a-string"></a>Convertir un objeto StringBuilder en String

Para poder pasar la cadena representada por el objeto [StringBuilder](xref:System.Text.StringBuilder) a un método con un parámetro [String](xref:System.String) o mostrarla en la interfaz de usuario, antes debe convertir el objeto [StringBuilder](xref:System.Text.StringBuilder) en un objeto [String](xref:System.String). Esta conversión se realiza llamando al método [StringBuilder.ToString](xref:System.Text.StringBuilder.ToString). En el ejemplo siguiente se llama a varios métodos [StringBuilder](xref:System.Text.StringBuilder) y, después, se llama al método [StringBuilder.ToString](xref:System.Text.StringBuilder.ToString) para mostrar la cadena.

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      StringBuilder sb = new StringBuilder();
      bool flag = true;
      string[] spellings = { "recieve", "receeve", "receive" };
      sb.AppendFormat("Which of the following spellings is {0}:", flag);
      sb.AppendLine();
      for (int ctr = 0; ctr <= spellings.GetUpperBound(0); ctr++) {
         sb.AppendFormat("   {0}. {1}", ctr, spellings[ctr]);
         sb.AppendLine();
      }
      sb.AppendLine();
      Console.WriteLine(sb.ToString());
   }
}
// The example displays the following output:
//       Which of the following spellings is True:
//          0. recieve
//          1. receeve
//          2. receive
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim sb As New StringBuilder()
      Dim flag As Boolean = True
      Dim spellings() As String = { "recieve", "receeve", "receive" }
      sb.AppendFormat("Which of the following spellings is {0}:", flag)
      sb.AppendLine()
      For ctr As Integer = 0 To spellings.GetUpperBound(0)
         sb.AppendFormat("   {0}. {1}", ctr, spellings(ctr))
         sb.AppendLine()
      Next
      sb.AppendLine()
      Console.WriteLine(sb.ToString())
   End Sub
End Module
' The example displays the following output:
'       Which of the following spellings is True:
'          0. recieve
'          1. receeve
'          2. receive
```

## <a name="see-also"></a>Vea también

[System.Text.StringBuilder](xref:System.Text.StringBuilder)

[Operaciones básicas de cadenas](basic-string-operations.md)

[Aplicar formato a tipos](formatting-types.md)



<!--HONumber=Nov16_HO3-->


