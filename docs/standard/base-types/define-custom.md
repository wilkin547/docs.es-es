---
title: "Cómo: Definir y usar proveedores de formato numérico personalizado"
description: "Cómo definir y usar proveedores de formato numérico personalizado"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 9b184114-6612-4c1a-a2db-2e24e65b0f77
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: bb62bdd03d4af4f764ac3bc8734c67902fffa798

---

# <a name="how-to-define-and-use-custom-numeric-format-providers"></a>Cómo: Definir y usar proveedores de formato numérico personalizado

.NET ofrece un amplio control sobre la representación de cadena de valores numéricos. Admite las siguientes características para personalizar el formato de los valores numéricos:

* Cadenas con formato numérico estándar, que proporcionan un conjunto predefinido de formatos para convertir números en su representación de cadena. También puede usarlas con cualquier método de formato numérico, como [Decimal.ToString(String](xref:System.Decimal.ToString(System.String)), que tiene un parámetro de formato. Para obtener detalles, consulte [Cadenas con formato numérico estándar](standard-numeric.md).

* Cadenas con formato numérico personalizado, que proporcionan un conjunto de símbolos que pueden combinarse para definir especificadores de formato numérico personalizado. También se pueden usar con cualquier método de formato numérico, como [Decimal.ToString(String](xref:System.Decimal.ToString(System.String)), que tiene un parámetro de formato. Para obtener detalles, consulte [Cadenas con formato numérico personalizado](custom-numeric.md).

* Objetos personalizados [CultureInfo](xref:System.Globalization.CultureInfo) o [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo), que definen los símbolos y los patrones de formato que se usan para mostrar las representaciones de cadena de valores numéricos. Se pueden usar con cualquier método de formato numérico, como [ToString](xref:System.Int32.ToString(System.IFormatProvider)), que tiene un parámetro *provider*. Normalmente, el parámetro *provider* se usa para especificar el formato específico de la referencia cultural.

En algunos casos (por ejemplo, cuando una aplicación debe mostrar un número de cuenta con formato, un número de identificación o un código postal) estas tres técnicas no resultan apropiadas. .NET también permite definir un objeto de formato que no es ni un objeto [CultureInfo](xref:System.Globalization.CultureInfo) ni un objeto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) para determinar cómo se aplica formato a un valor numérico. En este tema se proporcionan instrucciones paso a paso para implementar este tipo de objeto y se ofrece un ejemplo que da formato a números de teléfono.

## <a name="to-define-a-custom-format-provider"></a>Para definir un proveedor de formato personalizado

1. Defina una clase que implemente las interfaces [IFormatProvider](xref:System.IFormatProvider) e [ICustomFormatter](xref:System.ICustomFormatter). 

2. Implemente el método [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)). [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) es un método de devolución de llamada que el método de formato (como el método [String.Format(IFormatProvider,String,Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object))) invoca para recuperar el objeto realmente responsable del formato personalizado. Una implementación típica de [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) hace lo siguiente:

    a. Determina si el objeto [Type](xref:System.Type) pasado como un parámetro de método representa a una interfaz [ICustomFormatter](xref:System.ICustomFormatter).
    
    b. Si el parámetro representa a la interfaz [ICustomFormatter](xref:System.ICustomFormatter), [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) devuelve un objeto que implementa la interfaz [ICustomFormatter](xref:System.ICustomFormatter), que es responsable de proporcionar el formato personalizado. Normalmente, el objeto de formato personalizado se devuelve a sí mismo. 
    
    c. Si el parámetro no representa a la interfaz [ICustomFormatter](xref:System.ICustomFormatter), [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) devuelve `null`.
    
3. Implemente el método [ICustomFormatter.Format](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)). Este método es invocado por el método [String.Format(IFormatProvider,String,Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) y es responsable de devolver la representación de cadena de un número. La implementación del método normalmente implica lo siguiente:

    a. Opcionalmente, asegúrese de que el método se haya diseñado para proporcionar servicios de formato al examinar el parámetro *provider*. En el caso de los objetos de formato que implementan [IFormatProvider](xref:System.IFormatProvider) e [ICustomFormatter](xref:System.ICustomFormatter), esto implica probar la igualdad del parámetro *provider* y el objeto de formato actual.
    
    b. Determine si el objeto de formato debe admitir especificadores de formato personalizado. (Por ejemplo, un especificador de formato "N" podría indicar que debe generarse un número de teléfono de los Estados Unidos en formato NANP, mientras que una "I" podría indicar la salida en el formato de la recomendación E.123 de ITU-T). Si se usan especificadores de formato, el método debe controlar el especificador de formato específico. Se pasa al método en el parámetro de formato. Si no hay ningún especificador, el valor del parámetro *format* es [String.Empty](xref:System.String#System_String_Empty).
    
    c. Recupere el valor numérico pasado al método como parámetro *arg*. Realice todas las manipulaciones necesarias para convertirlo en su representación de cadena.
    
    d. Devuelva la representación de cadena del parámetro *arg*.
    
## <a name="to-use-a-custom-numeric-formatting-object"></a>Para usar un objeto de formato numérico personalizado

1. Cree una nueva instancia de la clase de formato personalizado.

2. Llame al método de formato [String.Format(IFormatProvider,String,Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)) y pásele el objeto de formato personalizado, el especificador de formato (o [String.Empty](xref:System.String.Empty) si no se usa ninguno) y el valor numérico al que se va a dar formato. 

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se define un proveedor de formato numérico personalizado denominado `TelephoneFormatter` que convierte un número que representa un número de teléfono de los Estados Unidos en su formato NANP o E.123. El método controla dos especificadores de formato, "N" (que genera el formato NANP) e "I" (que genera el formato E.123 internacional).

```csharp
using System;
using System.Globalization;

public class TelephoneFormatter : IFormatProvider, ICustomFormatter
{
   public object GetFormat(Type formatType)
   {
      if (formatType == typeof(ICustomFormatter))
         return this;
      else
         return null;
   }               

   public string Format(string format, object arg, IFormatProvider formatProvider)
   {
      // Check whether this is an appropriate callback             
      if (! this.Equals(formatProvider))
         return null; 

      // Set default format specifier             
      if (string.IsNullOrEmpty(format)) 
         format = "N";

      string numericString = arg.ToString();

      if (format == "N")
      {
         if (numericString.Length <= 4)
            return numericString;
         else if (numericString.Length == 7)
            return numericString.Substring(0, 3) + "-" + numericString.Substring(3, 4); 
         else if (numericString.Length == 10)
               return "(" + numericString.Substring(0, 3) + ") " +
                      numericString.Substring(3, 3) + "-" + numericString.Substring(6);   
         else
            throw new FormatException( 
                      string.Format("'{0}' cannot be used to format {1}.", 
                                    format, arg.ToString()));
      }
      else if (format == "I")
      {
         if (numericString.Length < 10)
            throw new FormatException(string.Format("{0} does not have 10 digits.", arg.ToString()));
         else
            numericString = "+1 " + numericString.Substring(0, 3) + " " + numericString.Substring(3, 3) + " " + numericString.Substring(6);
      }
      else
      {
         throw new FormatException(string.Format("The {0} format specifier is invalid.", format));
      } 
      return numericString;  
   }
}

public class TestTelephoneFormatter
{
   public static void Main()
   {
      Console.WriteLine(String.Format(new TelephoneFormatter(), "{0}", 0));
      Console.WriteLine(String.Format(new TelephoneFormatter(), "{0}", 911));
      Console.WriteLine(String.Format(new TelephoneFormatter(), "{0}", 8490216));
      Console.WriteLine(String.Format(new TelephoneFormatter(), "{0}", 4257884748));

      Console.WriteLine(String.Format(new TelephoneFormatter(), "{0:N}", 0));
      Console.WriteLine(String.Format(new TelephoneFormatter(), "{0:N}", 911));
      Console.WriteLine(String.Format(new TelephoneFormatter(), "{0:N}", 8490216));
      Console.WriteLine(String.Format(new TelephoneFormatter(), "{0:N}", 4257884748));

      Console.WriteLine(String.Format(new TelephoneFormatter(), "{0:I}", 4257884748));
   }
}
```

```vb
Public Class TelephoneFormatter : Implements IFormatProvider, ICustomFormatter
   Public Function GetFormat(formatType As Type) As Object _
                   Implements IFormatProvider.GetFormat
      If formatType Is GetType(ICustomFormatter) Then
         Return Me
      Else
         Return Nothing
      End If               
   End Function               

   Public Function Format(fmt As String, arg As Object, _
                          formatProvider As IFormatProvider) As String _
                   Implements ICustomFormatter.Format
      ' Check whether this is an appropriate callback             
      If Not Me.Equals(formatProvider) Then Return Nothing 

      ' Set default format specifier             
      If String.IsNullOrEmpty(fmt) Then fmt = "N"

      Dim numericString As String = arg.ToString

      If fmt = "N" Then
         Select Case numericString.Length
            Case <= 4 
               Return numericString
            Case 7
               Return Left(numericString, 3) & "-" & Mid(numericString, 4) 
            Case 10
               Return "(" & Left(numericString, 3) & ") " & _
                      Mid(numericString, 4, 3) & "-" & Mid(numericString, 7)   
            Case Else
               Throw New FormatException( _
                         String.Format("'{0}' cannot be used to format {1}.", _
                                       fmt, arg.ToString()))
         End Select
      ElseIf fmt = "I" Then
         If numericString.Length < 10 Then
            Throw New FormatException(String.Format("{0} does not have 10 digits.", arg.ToString()))
         Else
            numericString = "+1 " & Left(numericString, 3) & " " & Mid(numericString, 4, 3) & " " & Mid(numericString, 7)
         End If      
      Else
         Throw New FormatException(String.Format("The {0} format specifier is invalid.", fmt))
      End If 
      Return numericString  
   End Function
End Class

Public Module TestTelephoneFormatter
   Public Sub Main
      Console.WriteLine(String.Format(New TelephoneFormatter, "{0}", 0))
      Console.WriteLine(String.Format(New TelephoneFormatter, "{0}", 911))
      Console.WriteLine(String.Format(New TelephoneFormatter, "{0}", 8490216))
      Console.WriteLine(String.Format(New TelephoneFormatter, "{0}", 4257884748))

      Console.WriteLine(String.Format(New TelephoneFormatter, "{0:N}", 0))
      Console.WriteLine(String.Format(New TelephoneFormatter, "{0:N}", 911))
      Console.WriteLine(String.Format(New TelephoneFormatter, "{0:N}", 8490216))
      Console.WriteLine(String.Format(New TelephoneFormatter, "{0:N}", 4257884748))

      Console.WriteLine(String.Format(New TelephoneFormatter, "{0:I}", 4257884748))
   End Sub
End Module
```

El proveedor de formato numérico personalizado solo se puede usar con el método [String.Format(IFormatProvider,String,Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)). Las demás sobrecargas de métodos de formato numérico (como `ToString`) que tienen un parámetro de tipo [IFormatProvider](xref:System.IFormatProvider) pasan a la implementación de [IFormatProvider.GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) un objeto [Type](xref:System.Type) que representa al tipo [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo). A cambio, esperan que el método devuelva un objeto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo). Si no es así, se omite el proveedor de formato numérico personalizado y se usa el objeto [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) de la referencia cultural actual en su lugar. En el ejemplo, el método `TelephoneFormatter.GetFormat` controla la posibilidad de que se pueda pasar incorrectamente a un método de formato numérico al examinar el parámetro de método y devolver *null* si representa a un tipo distinto de [ICustomFormatter](xref:System.ICustomFormatter).

Si un proveedor de formato numérico personalizado admite un conjunto de especificadores de formato, asegúrese de proporcionar un comportamiento predeterminado si no se proporciona ningún especificador de formato en el elemento de formato usado en la llamada al método [String.Format(IFormatProvider,String,Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)). En el ejemplo, "N" es el especificador de formato predeterminado. Esto permite convertir un número en un número de teléfono con formato al proporcionar un especificador de formato explícito. En el ejemplo siguiente se muestra una llamada al método así.

```csharp
Console.WriteLine(String.Format(new TelephoneFormatter(), "{0:N}", 4257884748));
```

```vb
Console.WriteLine(String.Format(New TelephoneFormatter, "{0:N}", 4257884748))
```

Pero también permite que se produzca la conversión si no hay ningún especificador de formato. En el ejemplo siguiente se muestra una llamada al método así.

```csharp
Console.WriteLine(String.Format(new TelephoneFormatter(), "{0}", 4257884748));
```

```vb
Console.WriteLine(String.Format(New TelephoneFormatter, "{0}", 4257884748))
```

Si no se ha definido ningún especificador de formato predeterminado, la implementación del método [ICustomFormatter.Format](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) debe incluir código como el siguiente para que .NET pueda proporcionar formato no admitido por el código.

```csharp
if (arg is IFormattable) 
   s = ((IFormattable)arg).ToString(format, formatProvider);
else if (arg != null)    
   s = arg.ToString();
```

```vb
If TypeOf(arg) Is IFormattable Then 
   s = DirectCast(arg, IFormattable).ToString(fmt, formatProvider)
ElseIf arg IsNot Nothing Then    
   s = arg.ToString()
End If
```

En el caso de este ejemplo, el método que implementa [ICustomFormatter.Format](xref:System.ICustomFormatter.Format(System.String,System.Object,System.IFormatProvider)) está diseñado para actuar como un método de devolución de llamada del método [String.Format(IFormatProvider,String,Object[])](xref:System.String.Format(System.IFormatProvider,System.String,System.Object)). Por lo tanto, examina el parámetro *formatProvider* para determinar si contiene una referencia al objeto `TelephoneFormatter` actual. Pero también se puede llamar al método directamente desde el código. En ese caso, puede usar el parámetro *formatProvider* para proporcionar un objeto [CultureInfo](xref:System.Globalization.CultureInfo) o [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) que aporte información de formato específica de la referencia cultural.

## <a name="see-also"></a>Vea también

[Efectuar operaciones de formato](performing-formatting-operations.md)



<!--HONumber=Nov16_HO3-->


