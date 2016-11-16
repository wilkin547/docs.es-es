---
title: Uso de objetos que implementan IDisposable
description: Uso de objetos que implementan IDisposable
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 08/19/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: df780a6e-734e-44b8-9747-9f7783f79e20
translationtype: Human Translation
ms.sourcegitcommit: 213ce098bcc2b5e31c55e759d895254d5ca33caa
ms.openlocfilehash: 51655742b8975c84eae3f58c4ef0f7381a0bed6b

---

# <a name="using-objects-that-implement-idisposable"></a>Uso de objetos que implementan IDisposable

El recolector de elementos no utilizados de Common Language Runtime reclama la memoria usada por los objetos no administrados, aunque los tipos que usan recursos no administrados implementan la interfaz [IDisposable](xref:System.IDisposable) para permitir que se reclame esta memoria no administrada. Cuando termine de usar un objeto que implementa [IDisposable](xref:System.IDisposable), debe llamar a la implementación [IDisposable.Dispose](xref:System.IDisposable.Dispose) del objeto. Hay dos maneras de hacerlo:

* Mediante la instrucción `using` de C# o la instrucción `Using` de Visual Basic.

* Mediante la implementación de un bloque `try/finally`. 

## <a name="the-using-statement"></a>La instrucción using

Las instrucciones `using` de C# y `Using` de Visual Basic simplifican el código que se debe escribir para crear y limpiar un objeto. La instrucción `using` obtiene uno o más recursos, ejecuta las instrucciones especificadas y desecha el objeto automáticamente. Pero la instrucción `using` solo resulta útil para los objetos que se usan dentro del ámbito del método en el que se construyen. 

En el ejemplo siguiente se usa la instrucción `using` para crear y liberar un objeto [System.IO.StreamReader](xref:System.IO.StreamReader).

```cs
using System;
using System.IO;

public class Example
{
   public static void Main()
   {
      Char[] buffer = new Char[50];
      using (StreamReader s = new StreamReader("File1.txt")) {
         int charsRead = 0;
         while (s.Peek() != -1) {
            charsRead = s.Read(buffer, 0, buffer.Length);
            //
            // Process characters read.
            //   
         }
         s.Close();    
      }

   }
}
```

```vb
Imports System.IO

Module Example
   Public Sub Main()
      Dim buffer(49) As Char
      Using s As New StreamReader("File1.txt")
         Dim charsRead As Integer
         Do While s.Peek() <> -1
            charsRead = s.Read(buffer, 0, buffer.Length)         
            ' 
            ' Process characters read.
            '
         Loop
         s.Close()
      End Using
   End Sub
End Module
```

Si bien la clase [StreamReader](xref:System.IO.StreamReader) implementa la interfaz [IDisposable](xref:System.IDisposable), que indica que usa un recurso no administrado, en el ejemplo no se llama al método [StreamReader.Dispose](xref:System.IO.StreamReader.Dispose(System.Boolean)) de manera explícita. Cuando el compilador de C# o de Visual Basic encuentra la instrucción `using`, emite un lenguaje intermedio (IL), que equivale al código siguiente que contiene un bloque `try/finally` de manera explícita. 

```cs
using System;
using System.IO;

public class Example
{
   public static void Main()
   {
      Char[] buffer = new Char[50];
      {
         StreamReader s = new StreamReader("File1.txt"); 
         try {
            int charsRead = 0;
            while (s.Peek() != -1) {
               charsRead = s.Read(buffer, 0, buffer.Length);
               //
               // Process characters read.
               //   
            }
            s.Close();
         }
         finally {
            if (s != null)
               ((IDisposable)s).Dispose();     
         }       
      }
   }
}
```

```vb
Imports System.IO

Module Example
   Public Sub Main()
      Dim buffer(49) As Char
''      Dim s As New StreamReader("File1.txt")
With s As New StreamReader("File1.txt")
      Try
         Dim charsRead As Integer
         Do While s.Peek() <> -1
            charsRead = s.Read(buffer, 0, buffer.Length)         
            ' 
            ' Process characters read.
            '
         Loop
         s.Close()
      Finally
         If s IsNot Nothing Then DirectCast(s, IDisposable).Dispose()
      End Try
End With
   End Sub
End Module
```

La instrucción `using` de C# también permite adquirir varios recursos en una sola instrucción, lo que internamente equivale a instrucciones using anidadas. En el ejemplo siguiente se crean instancias de dos objetos [StreamReader](xref:System.IO.StreamReader) para leer el contenido de dos archivos. 

```cs
using System;
using System.IO;

public class Example
{
   public static void Main()
   {
      Char[] buffer1 = new Char[50], buffer2 = new Char[50];

      using (StreamReader version1 = new StreamReader("file1.txt"),
                          version2 = new StreamReader("file2.txt")) {
         int charsRead1, charsRead2 = 0;
         while (version1.Peek() != -1 && version2.Peek() != -1) {
            charsRead1 = version1.Read(buffer1, 0, buffer1.Length);
            charsRead2 = version2.Read(buffer2, 0, buffer2.Length);
            //
            // Process characters read.
            //
         }
         version1.Close();
         version2.Close();
      }
   }
}
```

## <a name="tryfinally-block"></a>Bloque try/finally

En lugar de ajustar un bloque `try/finally` en una instrucción `using`, puede elegir implementar el bloque `try/finally` directamente. Puede adoptar este estilo como su método de codificación personal, o bien puede hacer esto por una de las razones siguientes: 

* Para incluir un bloque `catch` para controlar las excepciones producidas en el bloque `try`. De lo contrario, las excepciones que produzca la instrucción `using` no se controlan, al igual que las excepciones producidas dentro del bloque `using` si no hay ningún bloque `try/catch` presente. 

* Para crear instancias de un objeto que implementa [IDisposable](xref:System.IDisposable) cuyo ámbito no es local en el bloque en el que se declara. 

El siguiente ejemplo es similar al anterior, a excepción de que se usa un bloque `try/catch/finally` para crear instancias, usar y eliminar un objeto [StreamReader](xref:System.IO.StreamReader), y para controlar las excepciones que produce el constructor [StreamReader](xref:System.IO.StreamReader) y su método [ReadToEnd](xref:System.IO.StreamReader.ReadToEnd). Observe que el código del bloque `finally` comprueba que el objeto que implementa [IDisposable](xref:System.IDisposable) no es `null` antes de llamar al método [Dispose](xref:System.IDisposable.Dispose). No hacerlo puede provocar una excepción [NullReferenceException](xref:System.NullReferenceException) en tiempo de ejecución. 

```cs
using System;
using System.Globalization;
using System.IO;

public class Example
{
   public static void Main()
   {
      StreamReader sr = null;
      try {
         sr = new StreamReader("file1.txt");
         String contents = sr.ReadToEnd();
         sr.Close();
         Console.WriteLine("The file has {0} text elements.", 
                           new StringInfo(contents).LengthInTextElements);    
      }      
      catch (FileNotFoundException) {
         Console.WriteLine("The file cannot be found.");
      }   
      catch (IOException) {
         Console.WriteLine("An I/O error has occurred.");
      }
      catch (OutOfMemoryException) {
         Console.WriteLine("There is insufficient memory to read the file.");   
      }
      finally {
         if (sr != null) sr.Dispose();     
      }
   }
}
```

```vb
Imports System.Globalization
Imports System.IO

Module Example
   Public Sub Main()
      Dim sr As StreamReader = Nothing
      Try 
         sr = New StreamReader("file1.txt")
         Dim contents As String = sr.ReadToEnd()
         sr.Close()
         Console.WriteLine("The file has {0} text elements.", 
                           New StringInfo(contents).LengthInTextElements)    
      Catch e As FileNotFoundException
         Console.WriteLine("The file cannot be found.")
      Catch e As IOException
         Console.WriteLine("An I/O error has occurred.")
      Catch e As OutOfMemoryException
         Console.WriteLine("There is insufficient memory to read the file.")   
      Finally 
         If sr IsNot Nothing Then sr.Dispose()     
      End Try
   End Sub
End Module
```

Puede seguir este patrón básico si elige implementar o debe implementar un bloque `try/finally`, ya que el lenguaje de programación no admite una instrucción `using` pero sí llamadas directas al método [Dispose](xref:System.IDisposable.Dispose). 

## <a name="see-also"></a>Vea también

[Limpiar recursos no administrados](unmanaged.md)





<!--HONumber=Nov16_HO1-->


