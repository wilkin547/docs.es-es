---
title: "Codificación de caracteres de .NET"
description: "Codificación de caracteres de .NET"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: bce54e41-e9dc-493a-8988-1cbadc340fe8
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: a8f42fa6a37f8de6f13186ea2ac17b2b2ced1601
ms.lasthandoff: 03/02/2017

---

# <a name="character-encoding-in-net"></a>Codificación de caracteres de .NET

Los caracteres son entidades abstractas que se pueden representar de muchas maneras diferentes. Una codificación de caracteres es un sistema que empareja cada carácter de un juego de caracteres compatible con algún valor que representa ese carácter. Por ejemplo, el código Morse es una codificación de caracteres que empareja cada carácter del alfabeto latino con un patrón de puntos y guiones que son adecuados para la transmisión a través de las líneas de telégrafo. Una codificación de caracteres para los equipos empareja cada carácter de un juego de caracteres compatible con un valor numérico que representa ese carácter. Una codificación de caracteres tiene dos componentes distintos:

* Un codificador, que traduce una secuencia de caracteres en una secuencia de valores numéricos (bytes).

* Un descodificador, que traduce una secuencia de bytes en una secuencia de caracteres.

La codificación de caracteres describe las reglas por las que funcionan un codificador y un descodificador. Por ejemplo, la clase [UTF8Encoding](xref:System.Text.UTF8Encoding) describe las reglas para codificar y descodificar del Formato de transformación Unicode de 8 bits (UTF-8), que usa de uno a cuatro bytes para representar un único carácter Unicode. La codificación y la descodificación también pueden incluir validación. Por ejemplo, la clase [UnicodeEncoding](xref:System.Text.UnicodeEncoding) comprueba todos los suplentes para asegurarse de que constituyen pares suplentes válidos. (Un par suplente consta de un carácter con un punto de código que va de U+D800 a U+DBFF, seguido de un carácter con un punto de código que va de U+DC00 a U+DFFF.) Una estrategia de reserva determina cómo trata un codificador los caracteres no válidos o cómo trata un descodificador los bytes no válidos. 

> [!WARNING]
> Las clases de codificación de .NET proporcionan una manera de almacenar y convertir datos de caracteres. No se deben usar para almacenar datos binarios en formato de cadena. Dependiendo de la codificación empleada, la conversión de datos binarios al formato de cadena con las clases de codificación puede presentar un comportamiento inesperado y mostrar datos inexactos o dañados. Para convertir datos binarios en un formato de cadena, use el método [Convert.ToBase64String](xref:System.Convert.ToBase64String(System.Byte[])). 
 
.NET usa la codificación UTF-16 (representada por la clase [UnicodeEncoding](xref:System.Text.UnicodeEncoding)) para representar caracteres y cadenas. Las aplicaciones cuyo destino es Common Language Runtime usan descodificadores para asignar representaciones de caracteres Unicode admitidas por Common Language Runtime a otros esquemas de codificación. Usan descodificadores para asignar caracteres de codificaciones no Unicode a Unicode.

Este tema consta de las siguientes secciones:

* [Codificaciones de .NET](#encodings-in-net)

* [Seleccionar una clase de codificación](#selecting-an-encoding-class)

* [Usar un objeto de codificación](#using-an-encoding-object)

* [Elegir una estrategia de reinterpretación](#choosing-a-fallback-strategy)

* [Implementar una estrategia de reserva personalizada](#implementing-a-custom-fallback-strategy)

## <a name="encodings-in-net"></a>Codificaciones de .NET

Todas las clases de codificación de caracteres de .NET heredan de la clase [System.Text.Encoding](xref:System.Text.Encoding), que es una clase abstracta que define la funcionalidad común a todas las codificaciones de caracteres. Para acceder a los objetos individuales de codificación implementados en .NET, haga lo siguiente:

* Use las propiedades estáticas de la clase [Encoding](xref:System.Text.Encoding), que devuelven objetos que representan las codificaciones de caracteres estándar disponibles en .NET (ASCII, UTF-7, UTF-8, UTF-16 y UTF-32). Por ejemplo, la propiedad [Encoding.Unicode](xref:System.Text.Encoding.Unicode) devuelve un objeto [UnicodeEncoding](xref:System.Text.UnicodeEncoding). Cada objeto usa la reserva de reemplazo para controlar las cadenas que no puede codificar y los bytes que no puede descodificar. (Para obtener más información, consulte la sección [Reserva de reemplazo](#replacement-fallback)).

* Llame al constructor de clase de la codificación. Se pueden crear instancias de los objetos para las codificaciones ASCII, UTF-7, UTF-8, UTF-16 y UTF-32 de esta manera. De forma predeterminada, cada objeto usa la reserva de reemplazo para controlar las cadenas que no puede codificar y los bytes que no puede descodificar, pero puede especificar que se debe producir una excepción en su lugar. (Para obtener más información, consulte las secciones [Reserva de reemplazo](#replacement-fallback) y [Reserva de excepción](#exception-fallback)).

* Llame al constructor [Encoding.Encoding(Int32)](xref:System.Text.Encoding.GetEncoding(System.Int32)) y pásele un entero que represente la codificación. Los objetos de codificación estándar usan la reserva de reemplazo, y los objetos de codificación para la página de códigos y el juego de caracteres de doble byte (DBCS) usan el retroceso de ajuste perfecto para controlar las cadenas que no pueden codificar y los bytes que no pueden descodificar. (Para obtener más información, consulte la sección [Reserva con ajuste perfecto](#best-fit-fallback)).

* Llame al método [Encoding.GetEncoding](xref:System.Text.Encoding.GetEncoding(System.Int32)), que devuelve cualquier estándar, página de códigos o codificación DBCS disponible en .NET. Las sobrecargas permiten especificar un objeto de reserva para el codificador y para el descodificador.

> [!NOTE]
> El estándar Unicode asigna un punto de código (un número) y un nombre a cada carácter en todos los scripts admitidos. Por ejemplo, el carácter "A" está representado por el punto de código U+0041 y el nombre "LATIN CAPITAL LETTER A". Las codificaciones de Formato de transformación Unicode (UTF) definen formas de codificar ese punto de código en una secuencia de uno o más bytes. Un esquema de codificación Unicode simplifica el desarrollo de aplicaciones de uso internacional porque permite que los caracteres de cualquier juego de caracteres estén representados en una única codificación. Los desarrolladores de aplicaciones ya no tienen que realizar el seguimiento del esquema de codificación empleado para producir caracteres para un idioma o un sistema de escritura concreto, y se pueden compartir los datos internacionalmente entre sistemas sin dañarlos.
>
>  .NET admite tres codificaciones definidas por el estándar Unicode: UTF-8, UTF-16 y UTF-32. Para obtener más información, consulte el estándar Unicode en la página principal de [Unicode](http://www.unicode.org/).
 
.NET admite los sistemas de codificación de caracteres que se muestran en la tabla siguiente.

Codificación | Clase | Descripción | Ventajas y desventajas
-------- | ----- | ----------- | ------------------------ 
ASCII | [ASCIIEncoding](xref:System.Text.ASCIIEncoding) | Codifica un intervalo limitado de caracteres usando los siete bits inferiores de un byte. | Como esta codificación solo admite valores de caracteres de U+0000 a U+007F, en la mayoría de los casos no resulta suficiente para aplicaciones de uso internacional.
UTF-7 | [UTF7Encoding](xref:System.Text.UTF7Encoding) | Representa los caracteres como secuencias de caracteres ASCII de 7 bits. Los caracteres Unicode no ASCII se representan con una secuencia de escape de caracteres ASCII. | UTF-7 admite protocolos como los protocolos de correo electrónico y de grupos de noticias. Sin embargo, la codificación UTF-7 no es particularmente segura ni sólida. En algunos casos, cambiar un bit puede modificar radicalmente la interpretación de toda una cadena UTF-7. En otros casos, diferentes cadenas UTF-7 pueden codificar el mismo texto. Para las secuencias que incluyen caracteres no ASCII, UTF-7 necesita más espacio que UTF-8, y la codificación y descodificación son más lentas. Por tanto, debe usar UTF-8 en lugar de UTF-7 si es posible.
UTF-8 | [UTF8Encoding](xref:System.Text.UTF8Encoding) | Representa cada punto de código Unicode como una secuencia de uno a cuatro bytes. | UTF-8 admite tamaños de datos de 8 bits y funciona bien con muchos sistemas operativos existentes. Para el intervalo ASCII de caracteres, UTF-8 es idéntico a la codificación ASCII y permite un conjunto mayor de caracteres. Sin embargo, para los scripts de Chino-Japonés-Coreano (CJK), UTF-8 puede necesitar tres bytes para cada carácter y puede generar tamaños de datos mayores que UTF-16. Tenga en cuenta que, algunas veces, la cantidad de datos ASCII, como las etiquetas HTML, justifica el mayor tamaño para el intervalo de CJK.
UTF-16 | [UnicodeEncoding](xref:System.Text.UnicodeEncoding) | Representa cada punto de código Unicode como una secuencia de uno o dos enteros de 16 bits. La mayoría de los caracteres Unicode comunes solo necesitan un punto de código UTF-16, aunque los caracteres Unicode suplementarios (U+10000 y posteriores) necesitan dos puntos de código UTF-16 suplentes. Se admiten tanto el orden de bytes little-endian como el big-endian. | Common Language Runtime usa la codificación UTF-16 para representar valores de tipo Char y String, y el sistema operativo Windows la usa para representar valores de tipo WCHAR.
UTF-32 | [UTF32Encoding](xref:System.Text.UTF32Encoding) | Representa cada punto de código Unicode como un entero de 32 bits. Se admiten tanto el orden de bytes little-endian como el big-endian. | La codificación UTF-32 se usa cuando las aplicaciones desean evitar el comportamiento de punto de código suplente de la codificación UTF-16 en sistemas operativos para los que el espacio codificado es muy importante. Los glifos únicos representados en una pantalla aún se pueden codificar con más de un carácter UTF-32.

Estas codificaciones permiten trabajar con caracteres Unicode, así como con codificaciones que son las más usadas en aplicaciones heredadas. Además, puede crear una codificación personalizada si define una clase que se deriva de [Encoding](xref:System.Text.Encoding) e invalida sus miembros.

> [!NOTE]
> De manera predeterminada, .NET Core no pone a disposición codificaciones de páginas de código que no sean la página de códigos 28591 y las codificaciones Unicode, como UTF-8 y UTF-16. Sin embargo, puede agregar que las codificaciones de páginas de código que se encuentran en las aplicaciones estándar de Windows que tienen como destino .NET Framework a la aplicación. Para obtener toda la información, consulte el tema [EncodingProvider](xref:System.Text.EncodingProvider). 

## <a name="selecting-an-encoding-class"></a>Seleccionar una clase de codificación

Si tiene la oportunidad de elegir la codificación que se usará en la aplicación, debe usar una codificación Unicode, preferiblemente [UTF8Encoding](xref:System.Text.UTF8Encoding) o [UnicodeEncoding](xref:System.Text.UnicodeEncoding). (.NET también admite una tercera codificación Unicode, [UTF32Encoding](xref:System.Text.UTF32Encoding)). 

Si piensa usar una codificación ASCII ([ASCIIEncoding](xref:System.Text.ASCIIEncoding)), elija [UTF8Encoding](xref:System.Text.UTF8Encoding) en su lugar. Las dos codificaciones son idénticas para el juego de caracteres ASCII, pero [UTF8Encoding](xref:System.Text.UTF8Encoding) presenta las ventajas siguientes: 

* Puede representar todos los caracteres Unicode, mientras que [ASCIIEncoding](xref:System.Text.ASCIIEncoding) solo admite los valores de caracteres Unicode entre U+0000 y U+007F.

* Proporciona detección de errores y una mayor seguridad.

* Se ha mejorado en materia de velocidad y debe ser más rápida que cualquier otra codificación. Incluso cuando todo el contenido es ASCII, las operaciones realizadas con [UTF8Encoding](xref:System.Text.UTF8Encoding) son más rápidas que las operaciones realizadas con [ASCIIEncoding](xref:System.Text.ASCIIEncoding).

Debe considerar la posibilidad de usar [ASCIIEncoding](xref:System.Text.ASCIIEncoding) solo para las aplicaciones heredadas. En cambio, incluso para las aplicaciones heredadas, [UTF8Encoding](xref:System.Text.UTF8Encoding) podría ser una opción mejor por las razones siguientes (suponiendo la configuración predeterminada):

* Si la aplicación tiene contenido que no es estrictamente ASCII y lo codifica con [ASCIIEncoding](xref:System.Text.ASCIIEncoding), cada carácter no ASCII se codifica como un signo de interrogación (?). Si la aplicación descodifica después estos datos, la información se pierde.


* Si la aplicación tiene contenido que no es estrictamente ASCII y lo codifica con [UTF8Encoding](xref:System.Text.UTF8Encoding), el resultado parece ininteligible si se interpreta como ASCII. Sin embargo, si la aplicación usa un descodificador UTF-8 para descodificar estos datos, los datos realizan una acción de ida y vuelta correctamente.

En una aplicación web, los caracteres enviados al cliente como respuesta a una solicitud web deben reflejar la codificación empleada en el cliente. En la mayoría de los casos, debe establecer la propiedad [HttpResponse.ContentEncoding](xref:System.Net.HttpResponseHeader.ContentEncoding) en el valor devuelto por la propiedad [HttpRequestHeader.ContentEncoding](xref:System.Net.HttpRequestHeader.ContentEncoding) para mostrar el texto en la codificación que el usuario espera.

## <a name="using-an-encoding-object"></a>Usar un objeto de codificación

Un codificador convierte una cadena de caracteres (normalmente, caracteres Unicode) en su equivalente numérico (bytes). Por ejemplo, podría usar un codificador ASCII para convertir caracteres Unicode en ASCII de forma que se puedan mostrar en la consola. Para realizar la conversión, llame al método [Encoding.GetBytes](xref:System.Text.Encoding.GetBytes(System.Char[])). Si quiere determinar cuántos bytes son necesarios para almacenar los caracteres codificados antes de realizar la codificación, puede llamar al método [GetByteCount](xref:System.Text.Encoding.GetByteCount(System.Char[])).

En el ejemplo siguiente se usa una única matriz de bytes para codificar cadenas en dos operaciones independientes. Mantiene un índice que indica la posición inicial de la matriz de bytes para el siguiente conjunto de bytes codificados con ASCII. Llama al método [ASCIIEncoding.GetByteCount(String)](xref:System.Text.ASCIIEncoding.GetByteCount(System.String)) para asegurarse de que la matriz de bytes es suficiente para alojar la cadena codificada. Después, llama al método [ASCIIEncoding.GetBytes(String, Int32, Int32, Byte[], Int32)](xref:System.Text.ASCIIEncoding.GetBytes(System.Char[],System.Int32,System.Int32,System.Byte[],System.Int32)) para codificar los caracteres de la cadena.

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      string[] strings= { "This is the first sentence. ", 
                          "This is the second sentence. " };
      Encoding asciiEncoding = Encoding.ASCII;

      // Create array of adequate size.
      byte[] bytes = new byte[49];
      // Create index for current position of array.
      int index = 0;

      Console.WriteLine("Strings to encode:");
      foreach (var stringValue in strings) {
         Console.WriteLine("   {0}", stringValue);

         int count = asciiEncoding.GetByteCount(stringValue);
         if (count + index >=  bytes.Length)
            Array.Resize(ref bytes, bytes.Length + 50);

         int written = asciiEncoding.GetBytes(stringValue, 0, 
                                              stringValue.Length, 
                                              bytes, index);    

         index = index + written; 
      } 
      Console.WriteLine("\nEncoded bytes:");
      Console.WriteLine("{0}", ShowByteValues(bytes, index));
      Console.WriteLine();

      // Decode Unicode byte array to a string.
      string newString = asciiEncoding.GetString(bytes, 0, index);
      Console.WriteLine("Decoded: {0}", newString);
   }

   private static string ShowByteValues(byte[] bytes, int last ) 
   {
      string returnString = "   ";
      for (int ctr = 0; ctr <= last - 1; ctr++) {
         if (ctr % 20 == 0)
            returnString += "\n   ";
         returnString += String.Format("{0:X2} ", bytes[ctr]);
      }
      return returnString;
   }
}
// The example displays the following output:
//       Strings to encode:
//          This is the first sentence.
//          This is the second sentence.
//       
//       Encoded bytes:
//       
//          54 68 69 73 20 69 73 20 74 68 65 20 66 69 72 73 74 20 73 65
//          6E 74 65 6E 63 65 2E 20 54 68 69 73 20 69 73 20 74 68 65 20
//          73 65 63 6F 6E 64 20 73 65 6E 74 65 6E 63 65 2E 20
//       
//       Decoded: This is the first sentence. This is the second sentence.
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim strings() As String = { "This is the first sentence. ", 
                                  "This is the second sentence. " }
      Dim asciiEncoding As Encoding = Encoding.ASCII

      ' Create array of adequate size.
      Dim bytes(50) As Byte
      ' Create index for current position of array.
      Dim index As Integer = 0

      Console.WriteLine("Strings to encode:")
      For Each stringValue In strings
         Console.WriteLine("   {0}", stringValue)

         Dim count As Integer = asciiEncoding.GetByteCount(stringValue)
         If count + index >=  bytes.Length Then
            Array.Resize(bytes, bytes.Length + 50)
         End If
         Dim written As Integer = asciiEncoding.GetBytes(stringValue, 0, 
                                                         stringValue.Length, 
                                                         bytes, index)    

         index = index + written 
      Next 
      Console.WriteLine()
      Console.WriteLine("Encoded bytes:")
      Console.WriteLine("{0}", ShowByteValues(bytes, index))
      Console.WriteLine()

      ' Decode Unicode byte array to a string.
      Dim newString As String = asciiEncoding.GetString(bytes, 0, index)
      Console.WriteLine("Decoded: {0}", newString)
   End Sub

   Private Function ShowByteValues(bytes As Byte(), last As Integer) As String
      Dim returnString As String = "   "
      For ctr As Integer = 0 To last - 1
         If ctr Mod 20 = 0 Then returnString += vbCrLf + "   "
         returnString += String.Format("{0:X2} ", bytes(ctr))
      Next
      Return returnString
   End Function
End Module
' The example displays the following output:
'       Strings to encode:
'          This is the first sentence.
'          This is the second sentence.
'       
'       Encoded bytes:
'       
'          54 68 69 73 20 69 73 20 74 68 65 20 66 69 72 73 74 20 73 65
'          6E 74 65 6E 63 65 2E 20 54 68 69 73 20 69 73 20 74 68 65 20
'          73 65 63 6F 6E 64 20 73 65 6E 74 65 6E 63 65 2E 20
'       
'       Decoded: This is the first sentence. This is the second sentence.
```

Un descodificador convierte una matriz de bytes que refleja una codificación de caracteres determinada en un juego de caracteres, ya sea en una matriz de caracteres o en una cadena. Para descodificar una matriz de bytes en una matriz de caracteres, llame al método [Encoding.GetChars](xref:System.Text.Encoding.GetChars(System.Byte[])). Para descodificar una matriz de bytes en una cadena, llame al método [GetString](xref:System.Text.Encoding.GetString(System.Byte[])). Si quiere determinar cuántos caracteres son necesarios para almacenar los bytes descodificados antes de realizar la descodificación, puede llamar al método [GetCharCount](xref:System.Text.Encoding.GetCharCount(System.Byte[])).

En el ejemplo siguiente se codifican tres cadenas y después se descodifican en una sola matriz de caracteres. Se mantiene un índice que indica la posición inicial de la matriz de caracteres para el siguiente juego de caracteres descodificados. Llama al método [GetCharCount](xref:System.Text.Encoding.GetCharCount(System.Byte[])) para asegurarse de que la matriz de caracteres es suficientemente grande para alojar todos los caracteres descodificados. Después, llama al método [ASCIIEncoding.GetChars(Byte[], Int32, Int32, Char[], Int32)](xref:System.Text.ASCIIEncoding.GetChars(System.Byte[],System.Int32,System.Int32,System.Char[],System.Int32)) para descodificar la matriz de bytes.

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      string[] strings = { "This is the first sentence. ", 
                           "This is the second sentence. ",
                           "This is the third sentence. " };
      Encoding asciiEncoding = Encoding.ASCII;
      // Array to hold encoded bytes.
      byte[] bytes;
      // Array to hold decoded characters.
      char[] chars = new char[50];
      // Create index for current position of character array.
      int index = 0;     

      foreach (var stringValue in strings) {
         Console.WriteLine("String to Encode: {0}", stringValue);
         // Encode the string to a byte array.
         bytes = asciiEncoding.GetBytes(stringValue);
         // Display the encoded bytes.
         Console.Write("Encoded bytes: ");
         for (int ctr = 0; ctr < bytes.Length; ctr++)
            Console.Write(" {0}{1:X2}", 
                          ctr % 20 == 0 ? Environment.NewLine : "", 
                          bytes[ctr]);
         Console.WriteLine();

         // Decode the bytes to a single character array.
         int count = asciiEncoding.GetCharCount(bytes);
         if (count + index >=  chars.Length)
            Array.Resize(ref chars, chars.Length + 50);

         int written = asciiEncoding.GetChars(bytes, 0, 
                                              bytes.Length, 
                                              chars, index);              
         index = index + written;
         Console.WriteLine();       
      }

      // Instantiate a single string containing the characters.
      string decodedString = new string(chars, 0, index - 1);
      Console.WriteLine("Decoded string: ");
      Console.WriteLine(decodedString);
   }
}
// The example displays the following output:
//    String to Encode: This is the first sentence.
//    Encoded bytes:
//    54 68 69 73 20 69 73 20 74 68 65 20 66 69 72 73 74 20 73 65
//    6E 74 65 6E 63 65 2E 20
//    
//    String to Encode: This is the second sentence.
//    Encoded bytes:
//    54 68 69 73 20 69 73 20 74 68 65 20 73 65 63 6F 6E 64 20 73
//    65 6E 74 65 6E 63 65 2E 20
//    
//    String to Encode: This is the third sentence.
//    Encoded bytes:
//    54 68 69 73 20 69 73 20 74 68 65 20 74 68 69 72 64 20 73 65
//    6E 74 65 6E 63 65 2E 20
//    
//    Decoded string:
//    This is the first sentence. This is the second sentence. This is the third sentence.
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim strings() As String = { "This is the first sentence. ", 
                                  "This is the second sentence. ",
                                  "This is the third sentence. " }
      Dim asciiEncoding As Encoding = Encoding.ASCII
      ' Array to hold encoded bytes.
      Dim bytes() As Byte
      ' Array to hold decoded characters.
      Dim chars(50) As Char
      ' Create index for current position of character array.
      Dim index As Integer     

      For Each stringValue In strings
         Console.WriteLine("String to Encode: {0}", stringValue)
         ' Encode the string to a byte array.
         bytes = asciiEncoding.GetBytes(stringValue)
         ' Display the encoded bytes.
         Console.Write("Encoded bytes: ")
         For ctr As Integer = 0 To bytes.Length - 1
            Console.Write(" {0}{1:X2}", If(ctr Mod 20 = 0, vbCrLf, ""), 
                                        bytes(ctr))
         Next         
         Console.WriteLine()

         ' Decode the bytes to a single character array.
         Dim count As Integer = asciiEncoding.GetCharCount(bytes)
         If count + index >=  chars.Length Then
            Array.Resize(chars, chars.Length + 50)
         End If
         Dim written As Integer = asciiEncoding.GetChars(bytes, 0, 
                                                         bytes.Length, 
                                                         chars, index)              
         index = index + written
         Console.WriteLine()       
      Next

      ' Instantiate a single string containing the characters.
      Dim decodedString As New String(chars, 0, index - 1)
      Console.WriteLine("Decoded string: ")
      Console.WriteLine(decodedString)
   End Sub
End Module
' The example displays the following output:
'    String to Encode: This is the first sentence.
'    Encoded bytes:
'    54 68 69 73 20 69 73 20 74 68 65 20 66 69 72 73 74 20 73 65
'    6E 74 65 6E 63 65 2E 20
'    
'    String to Encode: This is the second sentence.
'    Encoded bytes:
'    54 68 69 73 20 69 73 20 74 68 65 20 73 65 63 6F 6E 64 20 73
'    65 6E 74 65 6E 63 65 2E 20
'    
'    String to Encode: This is the third sentence.
'    Encoded bytes:
'    54 68 69 73 20 69 73 20 74 68 65 20 74 68 69 72 64 20 73 65
'    6E 74 65 6E 63 65 2E 20
'    
'    Decoded string:
'    This is the first sentence. This is the second sentence. This is the third sentence.
```

Los métodos de codificación y descodificación de una clase derivada de [Encoding](xref:System.Text.Encoding) están diseñados para funcionar en un conjunto completo de datos; es decir, todos los datos que se van a codificar o descodificar se proporcionan en una única llamada al método. Sin embargo, en algunos casos, los datos están disponibles en una secuencia y los datos que se va a codificar o descodificar pueden estar disponibles solo desde operaciones de lectura independientes. Para ello, la operación de codificación o descodificación debe recordar cualquier estado guardado de su invocación anterior. Los métodos de clases derivadas de [Encoder](xref:System.Text.Encoder) y [Decoder](xref:System.Text.Decoder) pueden controlar las operaciones de codificación y descodificación que abarcan varias llamadas a métodos.

Hay disponible un objeto [Encoder](xref:System.Text.Encoder) para una codificación determinada desde la propiedad [Encoding.GetEncoder](xref:System.Text.Encoding.GetEncoder) de esa codificación. Hay disponible un objeto [Decoder](xref:System.Text.Decoder) para una codificación determinada desde la propiedad [Encoding.GetDecoder](xref:System.Text.Encoding.GetDecoder) de esa codificación. Para las operaciones de descodificación, tenga en cuenta que las clases derivadas de [Decoder](xref:System.Text.Decoder) incluyen un método [Decoder.GetChars](xref:System.Text.Decoder.GetChars(System.Byte[],System.Int32,System.Int32,System.Char[],System.Int32)), pero no tienen un método que se corresponda con [Encoding.GetString](xref:System.Text.Encoding.GetString(System.Byte[])).

En el ejemplo siguiente, se muestra la diferencia entre el uso de los métodos [Encoding.GetChars](xref:System.Text.Encoding.GetChars(System.Byte[])) y [Decoder.GetChars](xref:System.Text.Decoder.GetChars(System.Byte[],System.Int32,System.Int32,System.Char[],System.Int32)) para descodificar una matriz de bytes Unicode. En el ejemplo se codifica una cadena que contiene algunos caracteres Unicode en un archivo y, a continuación, se usan los dos métodos de descodificación para descodificarlos de diez bytes en diez bytes. Puesto que hay un par suplente en los bytes décimo y undécimo, se descodifica en llamadas a métodos independientes. Como muestra el resultado, el método [Encoding.GetChars](xref:System.Text.Encoding.GetChars(System.Byte[])) no puede descodificar los bytes correctamente y, en su lugar, los reemplaza con U+FFFD (CARÁCTER DE REEMPLAZO). Por otra parte, el método [Decoder.GetChars](xref:System.Text.Decoder.GetChars(System.Byte[],System.Int32,System.Int32,System.Char[],System.Int32)) puede descodificar correctamente la matriz de bytes para obtener la cadena original.

```csharp
using System;
using System.IO;
using System.Text;

public class Example
{
   public static void Main()
   {
      // Use default replacement fallback for invalid encoding.
      UnicodeEncoding enc = new UnicodeEncoding(true, false, false);

      // Define a string with various Unicode characters.
      string str1 = "AB YZ 19 \uD800\udc05 \u00e4"; 
      str1 += "Unicode characters. \u00a9 \u010C s \u0062\u0308"; 
      Console.WriteLine("Created original string...\n");

      // Convert string to byte array.                     
      byte[] bytes = enc.GetBytes(str1);

      FileStream fs = File.Create(@".\characters.bin");
      BinaryWriter bw = new BinaryWriter(fs);
      bw.Write(bytes);
      bw.Close();

      // Read bytes from file.
      FileStream fsIn = File.OpenRead(@".\characters.bin");
      BinaryReader br = new BinaryReader(fsIn);

      const int count = 10;            // Number of bytes to read at a time. 
      byte[] bytesRead = new byte[10]; // Buffer (byte array).
      int read;                        // Number of bytes actually read. 
      string str2 = String.Empty;      // Decoded string.

      // Try using Encoding object for all operations.
      do { 
         read = br.Read(bytesRead, 0, count);
         str2 += enc.GetString(bytesRead, 0, read); 
      } while (read == count);
      br.Close();
      Console.WriteLine("Decoded string using UnicodeEncoding.GetString()...");
      CompareForEquality(str1, str2);
      Console.WriteLine();

      // Use Decoder for all operations.
      fsIn = File.OpenRead(@".\characters.bin");
      br = new BinaryReader(fsIn);
      Decoder decoder = enc.GetDecoder();
      char[] chars = new char[50];
      int index = 0;                   // Next character to write in array.
      int written = 0;                 // Number of chars written to array.
      do { 
         read = br.Read(bytesRead, 0, count);
         if (index + decoder.GetCharCount(bytesRead, 0, read) - 1 >= chars.Length) 
            Array.Resize(ref chars, chars.Length + 50);

         written = decoder.GetChars(bytesRead, 0, read, chars, index);
         index += written;                          
      } while (read == count);
      br.Close();            
      // Instantiate a string with the decoded characters.
      string str3 = new String(chars, 0, index); 
      Console.WriteLine("Decoded string using UnicodeEncoding.Decoder.GetString()...");
      CompareForEquality(str1, str3); 
   }

   private static void CompareForEquality(string original, string decoded)
   {
      bool result = original.Equals(decoded);
      Console.WriteLine("original = decoded: {0}", 
                        original.Equals(decoded, StringComparison.Ordinal));
      if (! result) {
         Console.WriteLine("Code points in original string:");
         foreach (var ch in original)
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));
         Console.WriteLine();

         Console.WriteLine("Code points in decoded string:");
         foreach (var ch in decoded)
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));
         Console.WriteLine();
      }
   }
}
// The example displays the following output:
//    Created original string...
//    
//    Decoded string using UnicodeEncoding.GetString()...
//    original = decoded: False
//    Code points in original string:
//    0041 0042 0020 0059 005A 0020 0031 0039 0020 D800 DC05 0020 00E4 0055 006E 0069 0063 006F
//    0064 0065 0020 0063 0068 0061 0072 0061 0063 0074 0065 0072 0073 002E 0020 00A9 0020 010C
//    0020 0073 0020 0062 0308
//    Code points in decoded string:
//    0041 0042 0020 0059 005A 0020 0031 0039 0020 FFFD FFFD 0020 00E4 0055 006E 0069 0063 006F
//    0064 0065 0020 0063 0068 0061 0072 0061 0063 0074 0065 0072 0073 002E 0020 00A9 0020 010C
//    0020 0073 0020 0062 0308
//    
//    Decoded string using UnicodeEncoding.Decoder.GetString()...
//    original = decoded: True
```

```vb
Imports System.IO
Imports System.Text

Module Example
   Public Sub Main()
      ' Use default replacement fallback for invalid encoding.
      Dim enc As New UnicodeEncoding(True, False, False)

      ' Define a string with various Unicode characters.
      Dim str1 As String = String.Format("AB YZ 19 {0}{1} {2}", 
                                         ChrW(&hD800), ChrW(&hDC05), ChrW(&h00e4))
      str1 += String.Format("Unicode characters. {0} {1} s {2}{3}", 
                            ChrW(&h00a9), ChrW(&h010C), ChrW(&h0062), ChrW(&h0308))
      Console.WriteLine("Created original string...")
      Console.WriteLine()

      ' Convert string to byte array.                     
      Dim bytes() As Byte = enc.GetBytes(str1)

      Dim fs As FileStream = File.Create(".\characters.bin")
      Dim bw As New BinaryWriter(fs)
      bw.Write(bytes)
      bw.Close()

      ' Read bytes from file.
      Dim fsIn As FileStream = File.OpenRead(".\characters.bin")
      Dim br As New BinaryReader(fsIn)

      Const count As Integer = 10      ' Number of bytes to read at a time. 
      Dim bytesRead(9) As Byte         ' Buffer (byte array).
      Dim read As Integer              ' Number of bytes actually read. 
      Dim str2 As String = ""          ' Decoded string.

      ' Try using Encoding object for all operations.
      Do 
         read = br.Read(bytesRead, 0, count)
         str2 += enc.GetString(bytesRead, 0, read) 
      Loop While read = count
      br.Close()
      Console.WriteLine("Decoded string using UnicodeEncoding.GetString()...")
      CompareForEquality(str1, str2)
      Console.WriteLine()

      ' Use Decoder for all operations.
      fsIn = File.OpenRead(".\characters.bin")
      br = New BinaryReader(fsIn)
      Dim decoder As Decoder = enc.GetDecoder()
      Dim chars(50) As Char
      Dim index As Integer = 0         ' Next character to write in array.
      Dim written As Integer = 0       ' Number of chars written to array.
      Do 
         read = br.Read(bytesRead, 0, count)
         If index + decoder.GetCharCount(bytesRead, 0, read) - 1 >= chars.Length Then 
            Array.Resize(chars, chars.Length + 50)
         End If   
         written = decoder.GetChars(bytesRead, 0, read, chars, index)
         index += written                          
      Loop While read = count
      br.Close()            
      ' Instantiate a string with the decoded characters.
      Dim str3 As New String(chars, 0, index) 
      Console.WriteLine("Decoded string using UnicodeEncoding.Decoder.GetString()...")
      CompareForEquality(str1, str3) 
   End Sub

   Private Sub CompareForEquality(original As String, decoded As String)
      Dim result As Boolean = original.Equals(decoded)
      Console.WriteLine("original = decoded: {0}", 
                        original.Equals(decoded, StringComparison.Ordinal))
      If Not result Then
         Console.WriteLine("Code points in original string:")
         For Each ch In original
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
         Next
         Console.WriteLine()

         Console.WriteLine("Code points in decoded string:")
         For Each ch In decoded
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
         Next
         Console.WriteLine()
      End If
   End Sub
End Module
' The example displays the following output:
'    Created original string...
'    
'    Decoded string using UnicodeEncoding.GetString()...
'    original = decoded: False
'    Code points in original string:
'    0041 0042 0020 0059 005A 0020 0031 0039 0020 D800 DC05 0020 00E4 0055 006E 0069 0063 006F
'    0064 0065 0020 0063 0068 0061 0072 0061 0063 0074 0065 0072 0073 002E 0020 00A9 0020 010C
'    0020 0073 0020 0062 0308
'    Code points in decoded string:
'    0041 0042 0020 0059 005A 0020 0031 0039 0020 FFFD FFFD 0020 00E4 0055 006E 0069 0063 006F
'    0064 0065 0020 0063 0068 0061 0072 0061 0063 0074 0065 0072 0073 002E 0020 00A9 0020 010C
'    0020 0073 0020 0062 0308
'    
'    Decoded string using UnicodeEncoding.Decoder.GetString()...
'    original = decoded: True
```

## <a name="choosing-a-fallback-strategy"></a>Elegir una estrategia de reinterpretación

Cuando un método intenta codificar o descodificar un carácter pero no existe ninguna asignación, debe implementar una estrategia de reserva que determine cómo se debe tratar la asignación incorrecta. Hay tres tipos de estrategias de reserva: 

* Reserva con ajuste perfecto

* Reserva de reemplazo

* Reserva de excepción

> [!IMPORTANT]
> Los problemas más frecuentes en las operaciones de codificación se producen cuando un carácter Unicode no se puede asignar a una codificación determinada de la página de códigos. Los problemas más comunes de las operaciones de descodificación se producen cuando las secuencias no válidas de bytes no se pueden traducir a caracteres Unicode válidos. Por estas razones, debe saber qué estrategia de reserva emplea un determinado objeto de codificación. Siempre que sea posible, debe especificar la estrategia de reserva usada por un objeto de codificación cuando se crea una instancia del objeto.
 
### <a name="best-fit-fallback"></a>Reserva con ajuste perfecto

Cuando un carácter no tiene una coincidencia exacta en la codificación de destino, el codificador puede intentar asignarle a un carácter similar. (La reserva con ajuste perfecto es principalmente un problema de codificación en lugar de un problema de descodificación. Hay muy pocas páginas de códigos que contengan caracteres que no se puedan asignar correctamente a Unicode.) La reserva con ajuste perfecto es el valor predeterminado para las codificaciones de páginas de códigos y de juegos de caracteres de doble byte recuperadas por las sobrecargas de [Encoding.GetEncoding(Int32)](xref:System.Text.Encoding.GetEncoding(System.Int32)) y [Encoding.GetEncoding(String)](xref:System.Text.Encoding.GetEncoding(System.String)).

> [!NOTE]
> En teoría, las clases de codificación Unicode proporcionadas en .NET ([UTF8Encoding](xref:System.Text.UTF8Encoding), [UnicodeEncoding](xref:System.Text.UnicodeEncoding) y [UTF32Encoding](xref:System.Text.UTF32Encoding)) admiten cada carácter de todos los juegos de caracteres, por lo que se pueden usar para eliminar los problemas de reserva con ajuste perfecto. 
 

Las estrategias de ajuste perfecto varían en función de la página de códigos y no se encuentran documentadas de manera detallada. Por ejemplo, para algunas páginas de códigos, los caracteres latinos de ancho completo se asignarán a caracteres latinos de ancho medio, que son más comunes. Para otras páginas de códigos no se realiza esta asignación. Incluso con una estrategia de ajuste perfecto dinámica, algunos caracteres no tienen un ajuste imaginable en algunas codificaciones. Por ejemplo, un ideograma chino no tiene ninguna asignación razonable a la página de códigos 1252. En este caso, se emplea una cadena de reemplazo. De forma predeterminada, esta cadena es simplemente un carácter QUESTION MARK (U+003F).

En el ejemplo siguiente se usa la página de códigos 1252 (la página de códigos de Windows para los idiomas de Europa occidental) para mostrar la asignación con ajuste perfecto y sus desventajas. El método [Encoding.GetEncoding(Int32](xref:System.Text.Encoding.GetEncoding(System.Int32)) se usa para recuperar un objeto de codificación para la página de códigos 1252. De forma predeterminada, usa una asignación con ajuste perfecto para los caracteres Unicode que no admite. En el ejemplo se crea una instancia de una cadena que contiene tres caracteres no ASCII, CIRCLED LATIN CAPITAL LETTER S (U+24C8), SUPERSCRIPT FIVE (U+2075) e INFINITY (U+221E), separados por espacios en blanco. Como muestra el resultado del ejemplo, cuando se codifica la cadena, los tres caracteres originales que no son espacios en blanco se reemplazan con QUESTION MARK (U+003F), DIGIT FIVE (U+0035) y DIGIT EIGHT (U+0038). DIGIT EIGHT es un reemplazo especialmente deficiente para el carácter INFINITY no compatible y QUESTION MARK indica que no había ninguna asignación disponible para el carácter original.

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      // Get an encoding for code page 1252 (Western Europe character set).
      Encoding cp1252 = Encoding.GetEncoding(1252);

      // Define and display a string.
      string str = "\u24c8 \u2075 \u221e";
      Console.WriteLine("Original string: " + str);
      Console.Write("Code points in string: ");
      foreach (var ch in str)
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

      Console.WriteLine("\n");   

      // Encode a Unicode string.
      Byte[] bytes = cp1252.GetBytes(str);
      Console.Write("Encoded bytes: ");
      foreach (byte byt in bytes)
         Console.Write("{0:X2} ", byt);
      Console.WriteLine("\n");

      // Decode the string.
      string str2 = cp1252.GetString(bytes);
      Console.WriteLine("String round-tripped: {0}", str.Equals(str2));
      if (! str.Equals(str2)) {
         Console.WriteLine(str2);
         foreach (var ch in str2)
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));
      }
   }
}
// The example displays the following output:
//       Original string: Ⓢ ⁵ ∞
//       Code points in string: 24C8 0020 2075 0020 221E
//       
//       Encoded bytes: 3F 20 35 20 38
//       
//       String round-tripped: False
//       ? 5 8
//       003F 0020 0035 0020 0038
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      ' Get an encoding for code page 1252 (Western Europe character set).
      Dim cp1252 As Encoding = Encoding.GetEncoding(1252)

      ' Define and display a string.
      Dim str As String = String.Format("{0} {1} {2}", ChrW(&h24c8), ChrW(&H2075), ChrW(&h221E))
      Console.WriteLine("Original string: " + str)
      Console.Write("Code points in string: ")
      For Each ch In str
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
      Next
      Console.WriteLine()   
      Console.WriteLine()

      ' Encode a Unicode string.
      Dim bytes() As Byte = cp1252.GetBytes(str)
      Console.Write("Encoded bytes: ")
      For Each byt In bytes
         Console.Write("{0:X2} ", byt)
      Next
      Console.WriteLine()
      Console.WriteLine()

      ' Decode the string.
      Dim str2 As String = cp1252.GetString(bytes)
      Console.WriteLine("String round-tripped: {0}", str.Equals(str2))
      If Not str.Equals(str2) Then
         Console.WriteLine(str2)
         For Each ch In str2
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
         Next
      End If
   End Sub
End Module
' The example displays the following output:
'       Original string: Ⓢ ⁵ ∞
'       Code points in string: 24C8 0020 2075 0020 221E
'       
'       Encoded bytes: 3F 20 35 20 38
'       
'       String round-tripped: False
'       ? 5 8
'       003F 0020 0035 0020 0038
```

La asignación con ajuste perfecto es el comportamiento predeterminado para un objeto [Encoding](xref:System.Text.Encoding) que codifica los datos Unicode en datos de página de códigos, y hay aplicaciones heredadas que se basan en este comportamiento. Sin embargo, la mayoría de las aplicaciones nuevas deben evitarlo por razones de seguridad. Por ejemplo, las aplicaciones no deben asignar nombres de dominio mediante una codificación con ajuste perfecto.

> [!Note]
> También puede implementar una asignación personalizada de reserva con ajuste perfecto para una codificación. Para obtener más información, consulte la sección [Implementar una estrategia de reserva personalizada](#implementing-a-custom-fallback-strategy).
 
Si la reserva con ajuste perfecto es el valor predeterminado para un objeto de codificación, puede elegir otra estrategia de reserva cuando recupera un objeto [Encoding](xref:System.Text.Encoding) al llamar a las sobrecargas [Encoding.GetEncoding(Int32, EncoderFallback, DecoderFallback)](xref:System.Text.Encoding.GetEncoding(System.Int32,System.Text.EncoderFallback,System.Text.DecoderFallback)) o [Encoding.GetEncoding(String, EncoderFallback, DecoderFallback)](xref:System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback)). La próxima sección incluye un ejemplo que reemplaza con un asterisco (\*) cada carácter que no se puede asignar a la página de códigos 1252.

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      Encoding cp1252r = Encoding.GetEncoding(1252, 
                                  new EncoderReplacementFallback("*"),
                                  new DecoderReplacementFallback("*"));

      string str1 = "\u24C8 \u2075 \u221E";
      Console.WriteLine(str1);
      foreach (var ch in str1)
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

      Console.WriteLine();

      byte[] bytes = cp1252r.GetBytes(str1);
      string str2 = cp1252r.GetString(bytes);
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2));
      if (! str1.Equals(str2)) {
         Console.WriteLine(str2);
         foreach (var ch in str2)
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

         Console.WriteLine();
      } 
   }
}
// The example displays the following output:
//       Ⓢ ⁵ ∞
//       24C8 0020 2075 0020 221E
//       Round-trip: False
//       * * *
//       002A 0020 002A 0020 002A
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim cp1252r As Encoding = Encoding.GetEncoding(1252, 
                                         New EncoderReplacementFallback("*"),
                                         New DecoderReplacementFallback("*"))

      Dim str1 As String = String.Format("{0} {1} {2}", ChrW(&h24C8), ChrW(&h2075), ChrW(&h221E))
      Console.WriteLine(str1)
      For Each ch In str1
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
      Next    
      Console.WriteLine()

      Dim bytes() As Byte = cp1252r.GetBytes(str1)
      Dim str2 As String = cp1252r.GetString(bytes)
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2))
      If Not str1.Equals(str2) Then
         Console.WriteLine(str2)
         For Each ch In str2
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
         Next    
         Console.WriteLine()
      End If 
   End Sub
End Module
' The example displays the following output:
'       Ⓢ ⁵ ∞
'       24C8 0020 2075 0020 221E
'       Round-trip: False
'       * * *
'       002A 0020 002A 0020 002A
```

### <a name="replacement-fallback"></a>Reserva de reemplazo

Cuando un carácter no tiene una coincidencia exacta en el esquema de destino, pero no hay ningún carácter adecuado al que se pueda asignar, la aplicación puede especificar un carácter o una cadena de reemplazo. Este es el comportamiento predeterminado del descodificador Unicode, que reemplaza cualquier secuencia de dos bytes que no pueda descodificar con REPLACEMENT_CHARACTER (U+FFFD). También es el comportamiento predeterminado de la clase [ASCIIEncoding](xref:System.Text.ASCIIEncoding), que reemplaza cada carácter que no puede codificar o descodificar con un signo de interrogación. En el ejemplo siguiente se muestra el reemplazo de caracteres para la cadena Unicode del ejemplo anterior. Como muestra el resultado, cada carácter que no se puede descodificar en un valor de bytes ASCII se reemplaza con 0x3F, que es el código ASCII de un signo de interrogación.

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      Encoding enc = Encoding.ASCII;

      string str1 = "\u24C8 \u2075 \u221E";
      Console.WriteLine(str1);
      foreach (var ch in str1)
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

      Console.WriteLine("\n");

      // Encode the original string using the ASCII encoder.
      byte[] bytes = enc.GetBytes(str1);
      Console.Write("Encoded bytes: ");
      foreach (var byt in bytes)
         Console.Write("{0:X2} ", byt);
      Console.WriteLine("\n");

      // Decode the ASCII bytes.
      string str2 = enc.GetString(bytes);
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2));
      if (! str1.Equals(str2)) {
         Console.WriteLine(str2);
         foreach (var ch in str2)
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

         Console.WriteLine();
      } 
   }
}
// The example displays the following output:
//       Ⓢ ⁵ ∞
//       24C8 0020 2075 0020 221E
//       
//       Encoded bytes: 3F 20 3F 20 3F
//       
//       Round-trip: False
//       ? ? ?
//       003F 0020 003F 0020 003F
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim enc As Encoding = Encoding.Ascii

      Dim str1 As String = String.Format("{0} {1} {2}", ChrW(&h24C8), ChrW(&h2075), ChrW(&h221E))
      Console.WriteLine(str1)
      For Each ch In str1
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
      Next    
      Console.WriteLine()
      Console.WriteLine() 

      ' Encode the original string using the ASCII encoder.
      Dim bytes() As Byte = enc.GetBytes(str1)
      Console.Write("Encoded bytes: ")
      For Each byt In bytes
         Console.Write("{0:X2} ", byt)
      Next
      Console.WriteLine()
      Console.WriteLine()

      ' Decode the ASCII bytes.
      Dim str2 As String = enc.GetString(bytes)
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2))
      If Not str1.Equals(str2) Then
         Console.WriteLine(str2)
         For Each ch In str2
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
         Next    
         Console.WriteLine()
      End If 
   End Sub
End Module
' The example displays the following output:
'       Ⓢ ⁵ ∞
'       24C8 0020 2075 0020 221E
'       
'       Encoded bytes: 3F 20 3F 20 3F
'       
'       Round-trip: False
'       ? ? ?
'       003F 0020 003F 0020 003F
```

.NET incluye las clases [EncoderReplacementFallback](xref:System.Text.EncoderReplacementFallback) y [DecoderReplacementFallback](xref:System.Text.DecoderReplacementFallback), que sustituyen una cadena de reemplazo si un carácter no se asigna exactamente en una operación de codificación o descodificación. De forma predeterminada, esta cadena de reemplazo es un signo de interrogación, pero puede llamar a una sobrecarga del constructor de clase para elegir otra cadena diferente. Normalmente, la cadena de reemplazo es un carácter único, aunque esto no es un requisito. En el ejemplo siguiente, se cambia el comportamiento del codificador de la página de códigos 1252 al crear una instancia de un objeto [EncoderReplacementFallback](xref:System.Text.EncoderReplacementFallback) que usa un asterisco (\*) como cadena de reemplazo.

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      Encoding cp1252r = Encoding.GetEncoding(1252, 
                                  new EncoderReplacementFallback("*"),
                                  new DecoderReplacementFallback("*"));

      string str1 = "\u24C8 \u2075 \u221E";
      Console.WriteLine(str1);
      foreach (var ch in str1)
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

      Console.WriteLine();

      byte[] bytes = cp1252r.GetBytes(str1);
      string str2 = cp1252r.GetString(bytes);
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2));
      if (! str1.Equals(str2)) {
         Console.WriteLine(str2);
         foreach (var ch in str2)
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

         Console.WriteLine();
      } 
   }
}
// The example displays the following output:
//       Ⓢ ⁵ ∞
//       24C8 0020 2075 0020 221E
//       Round-trip: False
//       * * *
//       002A 0020 002A 0020 002A
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim cp1252r As Encoding = Encoding.GetEncoding(1252, 
                                         New EncoderReplacementFallback("*"),
                                         New DecoderReplacementFallback("*"))

      Dim str1 As String = String.Format("{0} {1} {2}", ChrW(&h24C8), ChrW(&h2075), ChrW(&h221E))
      Console.WriteLine(str1)
      For Each ch In str1
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
      Next    
      Console.WriteLine()

      Dim bytes() As Byte = cp1252r.GetBytes(str1)
      Dim str2 As String = cp1252r.GetString(bytes)
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2))
      If Not str1.Equals(str2) Then
         Console.WriteLine(str2)
         For Each ch In str2
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
         Next    
         Console.WriteLine()
      End If 
   End Sub
End Module
' The example displays the following output:
'       Ⓢ ⁵ ∞
'       24C8 0020 2075 0020 221E
'       Round-trip: False
'       * * *
'       002A 0020 002A 0020 002A
```

> [!NOTE]
> También puede implementar una clase de reemplazo para una codificación. Para obtener más información, consulte la sección [Implementar una estrategia de reserva personalizada](#implementing-a-custom-fallback-strategy).
 
Además de QUESTION MARK (U+003F), el REPLACEMENT CHARACTER de Unicode (U+FFFD) se suele usar como cadena de reemplazo, especialmente al descodificar secuencias de bytes que no se puede traducir correctamente a caracteres Unicode. Sin embargo, se puede elegir cualquier cadena de reemplazo y esta puede contener varios caracteres.

### <a name="exception-fallback"></a>Reserva de excepción

En lugar de proporcionar una reserva con ajuste perfecto o una cadena de reemplazo, un codificador puede producir [EncoderFallbackException](xref:System.Text.EncoderFallbackException) si no puede codificar un juego de caracteres y un descodificador puede producir [DecoderFallbackException](xref:System.Text.DecoderFallbackException) si no puede descodificar una matriz de bytes. Para producir una excepción en las operaciones de codificación y descodificación, proporcione un objeto [EncoderFallbackException](xref:System.Text.EncoderFallbackException) y un objeto [DecoderFallbackException](xref:System.Text.DecoderFallbackException), respectivamente, al método [Encoding.GetEncoding(String, EncoderFallback, DecoderFallback)](xref:System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback)). En el ejemplo siguiente, se muestra la reserva de excepción con la clase ASCIIEncoding.

```csharp
using System;
using System.Text;

public class Example
{
   public static void Main()
   {
      Encoding enc = Encoding.GetEncoding("us-ascii", 
                                          new EncoderExceptionFallback(), 
                                          new DecoderExceptionFallback());

      string str1 = "\u24C8 \u2075 \u221E";
      Console.WriteLine(str1);
      foreach (var ch in str1)
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

      Console.WriteLine("\n");

      // Encode the original string using the ASCII encoder.
      byte[] bytes = {};
      try {
         bytes = enc.GetBytes(str1);
         Console.Write("Encoded bytes: ");
         foreach (var byt in bytes)
            Console.Write("{0:X2} ", byt);

         Console.WriteLine();
      }
      catch (EncoderFallbackException e) {
         Console.Write("Exception: ");
         if (e.IsUnknownSurrogate())
            Console.WriteLine("Unable to encode surrogate pair 0x{0:X4} 0x{1:X3} at index {2}.", 
                              Convert.ToUInt16(e.CharUnknownHigh), 
                              Convert.ToUInt16(e.CharUnknownLow), 
                              e.Index);
         else
            Console.WriteLine("Unable to encode 0x{0:X4} at index {1}.", 
                              Convert.ToUInt16(e.CharUnknown), 
                              e.Index);
         return;
      }
      Console.WriteLine();

      // Decode the ASCII bytes.
      try {
         string str2 = enc.GetString(bytes);
         Console.WriteLine("Round-trip: {0}", str1.Equals(str2));
         if (! str1.Equals(str2)) {
            Console.WriteLine(str2);
            foreach (var ch in str2)
               Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

            Console.WriteLine();
         } 
      }
      catch (DecoderFallbackException e) {
         Console.Write("Unable to decode byte(s) ");
         foreach (byte unknown in e.BytesUnknown)
            Console.Write("0x{0:X2} ");

         Console.WriteLine("at index {0}", e.Index);
      }
   }
}
// The example displays the following output:
//       Ⓢ ⁵ ∞
//       24C8 0020 2075 0020 221E
//       
//       Exception: Unable to encode 0x24C8 at index 0.
```

```vb
Imports System.Text

Module Example
   Public Sub Main()
      Dim enc As Encoding = Encoding.GetEncoding("us-ascii", 
                                                 New EncoderExceptionFallback(), 
                                                 New DecoderExceptionFallback())

      Dim str1 As String = String.Format("{0} {1} {2}", ChrW(&h24C8), ChrW(&h2075), ChrW(&h221E))
      Console.WriteLine(str1)
      For Each ch In str1
         Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
      Next    
      Console.WriteLine()
      Console.WriteLine() 

      ' Encode the original string using the ASCII encoder.
      Dim bytes() As Byte = {}
      Try
         bytes = enc.GetBytes(str1)
         Console.Write("Encoded bytes: ")
         For Each byt In bytes
            Console.Write("{0:X2} ", byt)
         Next
         Console.WriteLine()
      Catch e As EncoderFallbackException
         Console.Write("Exception: ")
         If e.IsUnknownSurrogate() Then
            Console.WriteLine("Unable to encode surrogate pair 0x{0:X4} 0x{1:X3} at index {2}.", 
                              Convert.ToUInt16(e.CharUnknownHigh), 
                              Convert.ToUInt16(e.CharUnknownLow), 
                              e.Index)
         Else
            Console.WriteLine("Unable to encode 0x{0:X4} at index {1}.", 
                              Convert.ToUInt16(e.CharUnknown), 
                              e.Index)
         End If                              
         Exit Sub
      End Try
      Console.WriteLine()

      ' Decode the ASCII bytes.
      Try
         Dim str2 As String = enc.GetString(bytes)
         Console.WriteLine("Round-trip: {0}", str1.Equals(str2))
         If Not str1.Equals(str2) Then
            Console.WriteLine(str2)
            For Each ch In str2
               Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
            Next    
            Console.WriteLine()
         End If 
      Catch e As DecoderFallbackException
         Console.Write("Unable to decode byte(s) ")
         For Each unknown As Byte In e.BytesUnknown
            Console.Write("0x{0:X2} ")
         Next
         Console.WriteLine("at index {0}", e.Index)
      End Try
   End Sub
End Module
' The example displays the following output:
'       Ⓢ ⁵ ∞
'       24C8 0020 2075 0020 221E
'       
'       Exception: Unable to encode 0x24C8 at index 0.
```

> [!NOTE]
> También puede implementar un controlador de excepciones personalizado para una operación de codificación. Para obtener más información, consulte la sección [Implementar una estrategia de reserva personalizada](#implementing-a-custom-fallback-strategy).
 
Los objetos [EncoderFallbackException](xref:System.Text.EncoderFallbackException) y [DecoderFallbackException](xref:System.Text.DecoderFallbackException) proporcionan la siguiente información sobre la condición que ha provocado la excepción: 

* El objeto [EncoderFallbackException](xref:System.Text.EncoderFallbackException) incluye un método [IsUnknownSurrogate](xref:System.Text.EncoderFallbackException.IsUnknownSurrogate), que indica si el carácter o los caracteres que no se pueden codificar representan un par suplente desconocido (en este caso, el método devuelve `true`) o un único carácter desconocido (en este caso, el método devuelve `false`). Los caracteres del par suplente están disponibles desde las propiedades [EncoderFallbackException.CharUnknownHigh](xref:System.Text.EncoderFallbackException.CharUnknownHigh) y [EncoderFallbackException.CharUnknownLow](xref:System.Text.EncoderFallbackException.CharUnknownLow). El único carácter desconocido está disponible desde la propiedad [EncoderFallbackException.CharUnknown](xref:System.Text.EncoderFallbackException.CharUnknown). La propiedad [EncoderFallbackException.Index](xref:System.Text.EncoderFallbackException.Index) indica la posición de la cadena en la que se ha encontrado el primer carácter que no se pudo codificar.

* El objeto [DecoderFallbackException](xref:System.Text.DecoderFallbackException) incluye una propiedad [BytesUnknown](xref:System.Text.DecoderFallbackException.BytesUnknown) que devuelve una matriz de bytes que no se pueden descodificar. La propiedad [DecoderFallbackException.Index](xref:System.Text.DecoderFallbackException.Index) indica la posición inicial de los bytes desconocidos.

Aunque los objetos [EncoderFallbackException](xref:System.Text.EncoderFallbackException) y [DecoderFallbackException](xref:System.Text.DecoderFallbackException) proporcionan información suficiente de diagnóstico sobre la excepción, no proporcionan acceso al búfer de codificación o descodificación. Por tanto, no permiten reemplazar o corregir datos no válidos dentro del método de codificación o descodificación.

## <a name="implementing-a-custom-fallback-strategy"></a>Implementar una estrategia de reserva personalizada

Además de la asignación con ajuste perfecto implementada internamente por las páginas de códigos, .NET incluye las siguientes clases para implementar una estrategia de reserva:

* Use [EncoderReplacementFallback](xref:System.Text.EncoderReplacementFallback) y [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) para reemplazar caracteres en operaciones de codificación.

* Use [DecoderReplacementFallback](xref:System.Text.DecoderReplacementFallback) y [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) para reemplazar caracteres en operaciones de descodificación.

* Use [EncoderExceptionFallback](xref:System.Text.EncoderExceptionFallback) y [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) para producir [EncoderFallbackException](xref:System.Text.EncoderFallbackException) cuando no se puede codificar un carácter.

* Use [DecoderExceptionFallback](xref:System.Text.DecoderExceptionFallback) y [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) para producir [DecoderFallbackException](xref:System.Text.DecoderFallbackException) cuando no se puede descodificar un carácter.

Además, puede implementar una solución personalizada que use reserva con ajuste perfecto, reserva de reemplazo o reserva de excepción siguiendo estos pasos: 

1. Derive una clase de [EncoderFallback](xref:System.Text.EncoderFallback) para las operaciones de codificación y de [DecoderFallback](xref:System.Text.DecoderFallback) para las operaciones de descodificación.

2. Derive una clase de [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) para las operaciones de codificación y de [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) para las operaciones de descodificación.

3. Para la reserva de excepción, si las clases [EncoderFallbackException](xref:System.Text.EncoderFallbackException) y [DecoderFallbackException](xref:System.Text.DecoderFallbackException) predefinidas no cumplen sus necesidades, derive una clase de un objeto de excepción como [Exception](xref:System.Exception) o [ArgumentException](xref:System.ArgumentException).

### <a name="deriving-from-encoderfallback-or-decoderfallback"></a>Derivar de EncoderFallback o DecoderFallback

Para implementar una solución de reserva personalizada, debe crear una clase que herede de [EncoderFallback](xref:System.Text.EncoderFallback) para las operaciones de codificación y de [DecoderFallback](xref:System.Text.DecoderFallback) para las operaciones de descodificación. Las instancias de estas clases se pasan al método [Encoding.GetEncoding(String, EncoderFallback, DecoderFallback)](xref:System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback)) y actúan como intermediario entre la clase de codificación y la implementación de reserva.

Cuando se crea una solución de reserva personalizada para un codificador o un descodificador, debe implementar los miembros siguientes:

* Las propiedades [EncoderFallback.MaxCharCount](xref:System.Text.EncoderFallback.MaxCharCount) o [DecoderFallback.MaxCharCount](xref:System.Text.DecoderFallback.MaxCharCount), que devuelven el número máximo de caracteres posible que el reemplazo con mejor ajuste o la reserva de excepción puedan devolver para reemplazar un único carácter. En el caso de la reserva de excepción personalizada, su valor es cero. 

* Los métodos [EncoderFallback.CreateFallbackBuffer](xref:System.Text.EncoderFallback.CreateFallbackBuffer) o [DecoderFallback.CreateFallbackBuffer](xref:System.Text.DecoderFallback.CreateFallbackBuffer), que devuelven las implementaciones [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) o [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) personalizadas. El codificador llama al método cuando encuentra el primer carácter que no puede codificar correctamente o lo llama el decodificador cuando encuentra el primer byte que no puede descodificar correctamente.

### <a name="deriving-from-encoderfallbackbuffer-or-decoderfallbackbuffer"></a>Derivar de EncoderFallbackBuffer o DecoderFallbackBuffer

Para implementar una solución de reserva personalizada, debe crear también una clase que herede de [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) para las operaciones de codificación y de [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) para las operaciones de descodificación. El método `CreateFallbackBuffer` de las clases [EncoderFallback](xref:System.Text.EncoderFallback) y [DecoderFallback](xref:System.Text.DecoderFallback) devuelve instancias de estas clases. El codificador llama al método [EncoderFallback.CreateFallbackBuffer](xref:System.Text.EncoderFallback.CreateFallbackBuffer) cuando encuentra el primer carácter que no puede codificar y el descodificador llama al método [DecoderFallback.CreateFallbackBuffer](xref:System.Text.DecoderFallback.CreateFallbackBuffer) cuando encuentra uno o más bytes que no puede descodificar. Las clases [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) y [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) proporcionan la implementación de reserva. Cada instancia representa un búfer que contiene los caracteres de reserva que reemplazarán el carácter que no se puede codificar o la secuencia de bytes que no se puede descodificar.

Cuando se crea una solución de reserva personalizada para un codificador o un descodificador, debe implementar los miembros siguientes:

* Los métodos [EncoderFallbackBuffer.Fallback](xref:System.Text.EncoderFallbackBuffer.%23ctor) o [DecoderFallbackBuffer.Fallback](xref:System.Text.DecoderFallbackBuffer.Fallback(System.Byte[],System.Int32)). El codificador llama a [EncoderFallbackBuffer.Fallback](xref:System.Text.EncoderFallbackBuffer.Fallback(System.Char,System.Char,System.Int32)) para proporcionar al búfer de reserva información sobre el carácter que no puede codificar. Puesto que el carácter que se va a codificar puede ser un par suplente, este método está sobrecargado. Se pasa a una sobrecarga el carácter que se va a codificar y su índice en la cadena. A la segunda sobrecarga se le pasa el suplente máximo y mínimo junto con su índice en la cadena. El descodificador llama al método [DecoderFallbackBuffer.Fallback](xref:System.Text.DecoderFallbackBuffer.Fallback(System.Byte[],System.Int32)) para proporcionar al búfer de reserva información sobre los bytes que no puede descodificar. Se pasa a este método una matriz de bytes que no puede descodificar, junto con el índice del primer byte. El método de reserva debe devolver `true` si el búfer de reserva puede proporcionar un carácter o caracteres de mejor ajuste o de reemplazo; de lo contrario, debe devolver `false`. En el caso de una reserva de excepción, el método de reserva debe producir una excepción.

* Los métodos [EncoderFallbackBuffer.GetNextChar](xref:System.Text.EncoderFallbackBuffer.GetNextChar) o [DecoderFallbackBuffer.GetNextChar](xref:System.Text.DecoderFallbackBuffer.GetNextChar), a los que llaman repetidamente el codificador o el descodificador para obtener el siguiente carácter del búfer de reserva. Cuando se han devuelto todos los caracteres de reserva, el método debe devolver U+0000. 

* Las propiedades [EncoderFallbackBuffer.Remaining](xref:System.Text.EncoderFallbackBuffer.Remaining) o [DecoderFallbackBuffer.Remaining](xref:System.Text.DecoderFallbackBuffer.Remaining), que devuelven el número de caracteres restantes del búfer de reserva.

* Los métodos [EncoderFallbackBuffer.MovePrevious](xref:System.Text.EncoderFallbackBuffer.MovePrevious) o [DecoderFallbackBuffer.MovePrevious](xref:System.Text.DecoderFallbackBuffer.MovePrevious), que mueven la posición actual del búfer de reserva al carácter anterior.

* Los métodos [EncoderFallbackBuffer.Reset](xref:System.Text.EncoderFallbackBuffer.Reset) o [DecoderFallbackBuffer.Reset](xref:System.Text.DecoderFallbackBuffer.Reset), que reinicializan el búfer de reserva.

Si la implementación de reserva es una reserva con ajuste perfecto o una reserva de reemplazo, las clases derivadas de [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer) y [DecoderFallbackBuffer](xref:System.Text.DecoderFallbackBuffer) también mantienen dos campos de instancia privados: el número exacto de caracteres del búfer y el índice del carácter siguiente del búfer que se va a devolver.

### <a name="an-encoderfallback-example"></a>Ejemplo de EncoderFallback

En un ejemplo anterior se usaba la reserva de reemplazo para reemplazar caracteres Unicode que no correspondían a caracteres ASCII con un asterisco (\*). En el ejemplo siguiente se usa una implementación personalizada de reserva con ajuste perfecto en su lugar para proporcionar una mejor asignación de caracteres no ASCII.

En el código siguiente se define una clase denominada `CustomMapper` que se deriva de [EncoderFallback](xref:System.Text.EncoderFallback) para controlar la asignación con ajuste perfecto de caracteres no ASCII. Su método `CreateFallbackBuffer` devuelve un objeto `CustomMapperFallbackBuffer`, que proporciona la implementación de [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer). La clase `CustomMapper` usa un objeto [Dictionary&lt;TKey, TValue&gt;](xref:System.Collections.Generic.Dictionary%602) para almacenar las asignaciones de caracteres Unicode no compatibles (el valor de clave) y sus caracteres de 8 bits correspondientes (que se almacenan en dos bytes consecutivos en un entero de 64 bits). Para que esta asignación esté disponible para el búfer de reserva, la instancia de `CustomMapper` se pasa como un parámetro al constructor de clase `CustomMapperFallbackBuffer`. Puesto que la asignación más larga es la cadena "INF" por el carácter Unicode U+221E, la propiedad `MaxCharCount` devuelve 3. 

```csharp
public class CustomMapper : EncoderFallback
{
   public string DefaultString;
   internal Dictionary<ushort, ulong> mapping;

   public CustomMapper() : this("*")
   {   
   }

   public CustomMapper(string defaultString)
   {
      this.DefaultString = defaultString;

      // Create table of mappings
      mapping = new Dictionary<ushort, ulong>();
      mapping.Add(0x24C8, 0x53);
      mapping.Add(0x2075, 0x35);
      mapping.Add(0x221E, 0x49004E0046);
   }

   public override EncoderFallbackBuffer CreateFallbackBuffer()
   {
      return new CustomMapperFallbackBuffer(this);
   }

   public override int MaxCharCount
   {
      get { return 3; }
   } 
}
```

```vb
Public Class CustomMapper : Inherits EncoderFallback
   Public DefaultString As String
   Friend mapping As Dictionary(Of UShort, ULong)

   Public Sub New()
      Me.New("?")
   End Sub

   Public Sub New(ByVal defaultString As String)
      Me.DefaultString = defaultString

      ' Create table of mappings
      mapping = New Dictionary(Of UShort, ULong)
      mapping.Add(&H24C8, &H53)
      mapping.Add(&H2075, &H35)
      mapping.Add(&H221E, &H49004E0046)
   End Sub

   Public Overrides Function CreateFallbackBuffer() As System.Text.EncoderFallbackBuffer
      Return New CustomMapperFallbackBuffer(Me)
   End Function

   Public Overrides ReadOnly Property MaxCharCount As Integer
      Get
         Return 3
      End Get
   End Property
End Class
```

En el código siguiente se define la clase `CustomMapperFallbackBuffer`, que se deriva de [EncoderFallbackBuffer](xref:System.Text.EncoderFallbackBuffer). El diccionario que contiene las asignaciones con ajuste perfecto y que se define en la instancia de `CustomMapper` está disponible desde su constructor de clase. Su método `Fallback` devuelve `true` si cualquiera de los caracteres Unicode que el codificador ASCII no puede codificar se definen en el diccionario de asignación; de lo contrario, devuelve `false`. Para cada reserva, la variable `count` privada indica el número de caracteres que quedan por devolver y la variable `index` privada indica la posición en el búfer de cadena, `charsToReturn`, del siguiente carácter que se va a devolver. 

```csharp
public class CustomMapperFallbackBuffer : EncoderFallbackBuffer
{
   int count = -1;                   // Number of characters to return
   int index = -1;                   // Index of character to return
   CustomMapper fb; 
   string charsToReturn; 

   public CustomMapperFallbackBuffer(CustomMapper fallback)
   {
      this.fb = fallback;
   }

   public override bool Fallback(char charUnknownHigh, char charUnknownLow, int index)
   {
      // Do not try to map surrogates to ASCII.
      return false;
   }

   public override bool Fallback(char charUnknown, int index)
   {
      // Return false if there are already characters to map.
      if (count >= 1) return false;

      // Determine number of characters to return.
      charsToReturn = String.Empty;

      ushort key = Convert.ToUInt16(charUnknown);
      if (fb.mapping.ContainsKey(key)) {
         byte[] bytes = BitConverter.GetBytes(fb.mapping[key]);
         int ctr = 0;
         foreach (var byt in bytes) {
            if (byt > 0) {
               ctr++;
               charsToReturn += (char) byt;
            }
         }
         count = ctr;
      }
      else {
         // Return default.
         charsToReturn = fb.DefaultString;
         count = 1;
      }
      this.index = charsToReturn.Length - 1;

      return true;
   }

   public override char GetNextChar()
   {
      // We'll return a character if possible, so subtract from the count of chars to return.
      count--;
      // If count is less than zero, we've returned all characters.
      if (count < 0) 
         return '\u0000';

      this.index--;
      return charsToReturn[this.index + 1];
   }

   public override bool MovePrevious()
   {
      // Original: if count >= -1 and pos >= 0
      if (count >= -1) {
         count++;
         return true;
      }
      else {
         return false;
      }
   }

   public override int Remaining 
   {
      get { return count < 0 ? 0 : count; }
   }

   public override void Reset()
   {
      count = -1;
      index = -1;
   }
}
```

```vb
Public Class CustomMapperFallbackBuffer : Inherits EncoderFallbackBuffer

   Dim count As Integer = -1        ' Number of characters to return
   Dim index As Integer = -1        ' Index of character to return
   Dim fb As CustomMapper
   Dim charsToReturn As String

   Public Sub New(ByVal fallback As CustomMapper)
      MyBase.New()
      Me.fb = fallback
   End Sub

   Public Overloads Overrides Function Fallback(ByVal charUnknownHigh As Char, ByVal charUnknownLow As Char, ByVal index As Integer) As Boolean
      ' Do not try to map surrogates to ASCII.
      Return False
   End Function

   Public Overloads Overrides Function Fallback(ByVal charUnknown As Char, ByVal index As Integer) As Boolean
      ' Return false if there are already characters to map.
      If count >= 1 Then Return False

      ' Determine number of characters to return.
      charsToReturn = String.Empty

      Dim key As UShort = Convert.ToUInt16(charUnknown)
      If fb.mapping.ContainsKey(key) Then
         Dim bytes() As Byte = BitConverter.GetBytes(fb.mapping.Item(key))
         Dim ctr As Integer
         For Each byt In bytes
            If byt > 0 Then
               ctr += 1
               charsToReturn += Chr(byt)
            End If
         Next
         count = ctr
      Else
         ' Return default.
         charsToReturn = fb.DefaultString
         count = 1
      End If
      Me.index = charsToReturn.Length - 1

      Return True
   End Function

   Public Overrides Function GetNextChar() As Char
      ' We'll return a character if possible, so subtract from the count of chars to return.
      count -= 1
      ' If count is less than zero, we've returned all characters.
      If count < 0 Then Return ChrW(0)

      Me.index -= 1
      Return charsToReturn(Me.index + 1)
   End Function

   Public Overrides Function MovePrevious() As Boolean
      ' Original: if count >= -1 and pos >= 0
      If count >= -1 Then
         count += 1
         Return True
      Else
         Return False
      End If
   End Function

   Public Overrides ReadOnly Property Remaining As Integer
      Get
         Return If(count < 0, 0, count)
      End Get
   End Property

   Public Overrides Sub Reset()
      count = -1
      index = -1
   End Sub
End Class
```

En el código siguiente se crean instancias del objeto `CustomMapper` y se pasa una instancia de él al método [Encoding.GetEncoding(String, EncoderFallback, DecoderFallback)](xref:System.Text.Encoding.GetEncoding(System.String,System.Text.EncoderFallback,System.Text.DecoderFallback)). El resultado indica que la implementación de reserva con ajuste perfecto controla correctamente los tres caracteres no ASCII de la cadena original.

```csharp
using System;
using System.Collections.Generic;
using System.Text;

class Program
{
   static void Main()
   {
      Encoding enc = Encoding.GetEncoding("us-ascii", new CustomMapper(), new DecoderExceptionFallback());

      string str1 = "\u24C8 \u2075 \u221E";
      Console.WriteLine(str1);
      for (int ctr = 0; ctr <= str1.Length - 1; ctr++) {
         Console.Write("{0} ", Convert.ToUInt16(str1[ctr]).ToString("X4"));
         if (ctr == str1.Length - 1) 
            Console.WriteLine();
      }
      Console.WriteLine();

      // Encode the original string using the ASCII encoder.
      byte[] bytes = enc.GetBytes(str1);
      Console.Write("Encoded bytes: ");
      foreach (var byt in bytes)
         Console.Write("{0:X2} ", byt);

      Console.WriteLine("\n");

      // Decode the ASCII bytes.
      string str2 = enc.GetString(bytes);
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2));
      if (! str1.Equals(str2)) {
         Console.WriteLine(str2);
         foreach (var ch in str2)
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"));

         Console.WriteLine();
      }
   }
}
```

```vb
Imports System.Text
Imports System.Collections.Generic

Module Module1

   Sub Main()
      Dim enc As Encoding = Encoding.GetEncoding("us-ascii", New CustomMapper(), New DecoderExceptionFallback())

      Dim str1 As String = String.Format("{0} {1} {2}", ChrW(&H24C8), ChrW(&H2075), ChrW(&H221E))
      Console.WriteLine(str1)
      For ctr As Integer = 0 To str1.Length - 1
         Console.Write("{0} ", Convert.ToUInt16(str1(ctr)).ToString("X4"))
         If ctr = str1.Length - 1 Then Console.WriteLine()
      Next
      Console.WriteLine()

      ' Encode the original string using the ASCII encoder.
      Dim bytes() As Byte = enc.GetBytes(str1)
      Console.Write("Encoded bytes: ")
      For Each byt In bytes
         Console.Write("{0:X2} ", byt)
      Next
      Console.WriteLine()
      Console.WriteLine()

      ' Decode the ASCII bytes.
      Dim str2 As String = enc.GetString(bytes)
      Console.WriteLine("Round-trip: {0}", str1.Equals(str2))
      If Not str1.Equals(str2) Then
         Console.WriteLine(str2)
         For Each ch In str2
            Console.Write("{0} ", Convert.ToUInt16(ch).ToString("X4"))
         Next
         Console.WriteLine()
      End If
   End Sub
End Module
```

## <a name="see-also"></a>Vea también

[System.Text.Encoder](xref:System.Text.Encoder)

[System.Text.EncoderFallback](xref:System.Text.EncoderFallback)

[System.Text.Decoder](xref:System.Text.Decoder)

[System.Text.DecoderFallback](xref:System.Text.DecoderFallback)

[System.Text.Encoding](xref:System.Text.Encoding)





