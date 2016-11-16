---
title: "Implementar un método Dispose"
description: "Implementar un método Dispose"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 08/16/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: eca6cdc3-6a14-4296-86fb-1eb2f21455b0
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: dfe2cebfbcf1f4c2697683ebda8c1e11567fd015

---

# <a name="implementing-a-dispose-method"></a>Implementar un método Dispose

El método [Dispose](xref:System.IDisposable.Dispose) se implementa para liberar recursos no administrados que usa la aplicación. El recolector de elementos no utilizados de .NET no asigna ni libera memoria no administrada. 

El modelo para desechar un objeto, lo que se conoce como modelo de Dispose, sirve para imponer orden sobre la duración de un objeto. El patrón de Dispose se utiliza solo con los objetos que tienen acceso a recursos no administrados, como identificadores de archivo y de canalización, identificadores de registro, identificadores de espera o punteros a bloques de memoria sin administrar. Esto se debe a que el recolector de elementos no utilizados es muy eficaz a la hora de reclamar objetos administrados no usados, aunque no puede reclamar objetos no administrados.

El patrón de Dispose tiene dos variaciones:

* Incluir los recursos no administrados que use un tipo en un controlador seguro (es decir, en una clase derivada de [System.Runtime.InteropServices.SafeHandle](xref:System.Runtime.InteropServices.SafeHandle)). En este caso, se implementa la interfaz [IDisposable](xref:System.IDisposable) y un método `Dispose(Boolean)` adicional. Esta es la variación recomendada y no requiere invalidar el método [Object.Finalize](xref:System.Object.Finalize). 

> [!NOTE]
> El espacio de nombres [Microsoft.Win32.SafeHandles](xref:Microsoft.Win32.SafeHandles) proporciona un conjunto de clases derivadas de [SafeHandle](xref:System.Runtime.InteropServices.SafeHandle) que aparecen enumeradas en la sección [Uso de controladores seguros](#using-safe-handles). Si no encuentra ninguna clase que sea capaz de liberar el recurso no administrado, puede implementar su propia subclase de [SafeHandle](xref:System.Runtime.InteropServices.SafeHandle). 
 
* Puede implementar la interfaz [IDisposable](xref:System.IDisposable) y un método `Dispose(Boolean` adicional, así como invalidar el método [Object.Finalize](xref:System.Object.Finalize). Debe invalidar [Finalize](xref:System.Object.Finalize) para asegurarse de que los recursos no administrados se eliminan en el caso de que un consumidor de su tipo no llame a la implementación [IDisposable.Dispose](xref:System.IDisposable.Dispose). Si usa la técnica recomendada analizada en el punto anterior, la clase [System.Runtime.InteropServices.SafeHandle](xref:System.Runtime.InteropServices.SafeHandle) realiza este procedimiento en su nombre. 

Para asegurarse de que los recursos se limpien siempre correctamente, un método [Dispose](xref:System.IDisposable.Dispose) debe ser invocable varias veces sin que se produzca una excepción. 

El ejemplo de código proporcionado para el método [GC.KeepAlive](xref:System.GC.KeepAlive(System.Object)) muestra cómo la recolección de elementos no utilizados rigurosa puede hacer que se ejecute un finalizador mientras un miembro del objeto reclamado todavía se está ejecutando. Suele ser recomendable llamar al método [KeepAlive](xref:System.GC.KeepAlive(System.Object)) al final de un método `Dispose` prolongado.

## <a name="dispose-and-disposeboolean"></a>Dispose() y Dispose (booleano)

La interfaz [IDisposable](xref:System.IDisposable) requiere la implementación de un único método sin parámetros, [Dispose](xref:System.IDisposable.Dispose). Sin embargo, el patrón de Dispose requiere dos métodos `Dispose` para implementarse: 

* Una implementación pública que no sea virtual (`NonInheritable` en Visual Basic) [IDisposable.Dispose](xref:System.IDisposable.Dispose) y que no tenga parámetros.

* Un método protegido virtual (`Overridable` in Visual Basic) `Dispose` cuya signatura es:

  ```cs
  protected virtual void Dispose(bool disposing)
  ```

  ```vb
  Protected Overridable Sub Dispose(disposing As Boolean)
  ```

### <a name="the-dispose-overload"></a>La sobrecarga Dispose()

Dado que un consumidor del tipo llama a este método `NonInheritable` público, no virtual (`Dispose` en Visual Basic) y sin parámetros, su propósito consiste en liberar recursos no administrados e indicar que el finalizador, si existe, no tiene que ejecutarse. Debido a esto, se realiza una implementación estándar:

```cs
public void Dispose()
{
   // Dispose of unmanaged resources.
   Dispose(true);
   // Suppress finalization.
   GC.SuppressFinalize(this);
}
```

```vb
Public Sub Dispose() _
           Implements IDisposable.Dispose
   ' Dispose of unmanaged resources.
   Dispose(True)
   ' Suppress finalization.
   GC.SuppressFinalize(Me)
End Sub
```

El método `Dispose` limpia todos los objetos, por lo que el recolector de elementos no utilizados no necesita llamar a la invalidación [Object.Finalize](xref:System.Object.Finalize) de los objetos. Por consiguiente, la llamada al método [GC.SuppressFinalize](xref:System.GC.SuppressFinalize(System.Object)) evita que el recolector de elementos no utilizados ejecute el finalizador. Si el tipo no tiene ningún finalizador, la llamada a [SuppressFinalize](xref:System.GC.SuppressFinalize(System.Object)) no tiene ningún efecto. Observe que el trabajo real de liberar recursos no administrados lo realiza la segunda sobrecarga del método `Dispose`.

### <a name="the-disposeboolean-overload"></a>La sobrecarga Dispose(Boolean)

En la segunda sobrecarga, el parámetro *disposing* es un valor [Boolean](xref:System.Boolean) que indica si la llamada al método procede de un método [Dispose](xref:System.IDisposable.Dispose) (su valor es `true`) o de un finalizador (su valor es `false`). 

El cuerpo del método consta de dos bloques de código: 

* Un bloque que libera los recursos no administrados. Este bloque se ejecuta independientemente del valor del parámetro *disposing*. 

* Un bloque condicional que libera los recursos administrados. Este bloque se ejecuta si el valor de *disposing* es `true`. Estos son algunos de los recursos administrados que se liberan: 

    **Objetos administrados que implementan IDisposable**. El bloque condicional se puede usar para llamar a la implementación [Dispose](xref:System.IDisposable.Dispose). Si ha usado un controlador seguro para incluir el recurso no administrado, debe llamar aquí a la implementación [SafeHandle.Dispose(Boolean](xref:System.Runtime.InteropServices.SafeHandle.Dispose(System.Boolean)). 

    **Objetos administrados que consumen gran cantidad de memoria o recursos insuficientes.** Al liberar estos objetos explícitamente en el método `Dispose`, se liberan más rápido que si el recolector de elementos no utilizados los reclamara de forma no determinista. 


Si la llamada al método procede de un finalizador (es decir, *disposing* es `false`), solo se ejecuta el código que libera los recursos no administrados. Como no se define el orden en que el recolector de elementos no utilizados destruye los objetos administrados durante la finalización, la llamada a esta sobrecarga `Dispose` con un valor de `false` evita que el finalizador intente liberar los recursos administrados que ya se hayan reclamado. 

## <a name="implementing-the-dispose-pattern-for-a-base-class"></a>Implementación del patrón de Dispose para una clase base

Cuando se implementa el patrón de Dispose para una clase base, debe proporcionar lo siguiente: 

> [!IMPORTANT]
> Implemente este patrón para todas las clases base que implementen [IDisposable](xref:System.IDisposable) y no sean `sealed`. 
 
* Una implementación [Dispose](xref:System.IDisposable.Dispose) que llame al método `Dispose(Boolean)`. 

* Un método `Dispose(Boolean)` que realiza el trabajo real de liberar recursos. 

* Una clase derivada de [SafeHandle](xref:System.Runtime.InteropServices.SafeHandle) que contiene el recurso no administrado (recomendado), o una invalidación del método [Object.Finalize](xref:System.Object.Finalize). La clase [SafeHandle](xref:System.Runtime.InteropServices.SafeHandle)SafeHandle proporciona un finalizador que evita que tenga que programar uno. 

A continuación se muestra el patrón general para implementar el patrón de Dispose para una clase base que utiliza un controlador seguro. 

```cs
using Microsoft.Win32.SafeHandles;
using System;
using System.Runtime.InteropServices;

class BaseClass : IDisposable
{
   // Flag: Has Dispose already been called?
   bool disposed = false;
   // Instantiate a SafeHandle instance.
   SafeHandle handle = new SafeFileHandle(IntPtr.Zero, true);

   // Public implementation of Dispose pattern callable by consumers.
   public void Dispose()
   { 
      Dispose(true);
      GC.SuppressFinalize(this);           
   }

   // Protected implementation of Dispose pattern.
   protected virtual void Dispose(bool disposing)
   {
      if (disposed)
         return; 

      if (disposing) {
         handle.Dispose();
         // Free any other managed objects here.
         //
      }

      // Free any unmanaged objects here.
      //
      disposed = true;
   }
}
```

```vb
Imports Microsoft.Win32.SafeHandles
Imports System.Runtime.InteropServices

Class BaseClass : Implements IDisposable
   ' Flag: Has Dispose already been called?
   Dim disposed As Boolean = False
   ' Instantiate a SafeHandle instance.
   Dim handle As SafeHandle = New SafeFileHandle(IntPtr.Zero, True)

   ' Public implementation of Dispose pattern callable by consumers.
   Public Sub Dispose() _
              Implements IDisposable.Dispose
      Dispose(True)
      GC.SuppressFinalize(Me)           
   End Sub

   ' Protected implementation of Dispose pattern.
   Protected Overridable Sub Dispose(disposing As Boolean)
      If disposed Then Return

      If disposing Then
         handle.Dispose()
         ' Free any other managed objects here.
         '
      End If

      ' Free any unmanaged objects here.
      '
      disposed = True
   End Sub
End Class
```

> [!NOTE] 
> El ejemplo anterior usa un objeto [SafeFileHandle](xref:Microsoft.Win32.SafeHandles.SafeFileHandle) para ilustrar el patrón; cualquier objeto derivado de [SafeHandle](xref:System.Runtime.InteropServices.SafeHandle) podría usarse en su lugar. Tenga en cuenta que el ejemplo no crea una instancia de su objeto [SafeFileHandle](xref:Microsoft.Win32.SafeHandles.SafeFileHandle) correctamente. 
 
A continuación se muestra el patrón general para implementar el patrón de Dispose para una clase base que invalide a [Object.Finalize](xref:System.Object.Finalize). 

```cs
using System;

class BaseClass : IDisposable
{
   // Flag: Has Dispose already been called?
   bool disposed = false;

   // Public implementation of Dispose pattern callable by consumers.
   public void Dispose()
   { 
      Dispose(true);
      GC.SuppressFinalize(this);           
   }

   // Protected implementation of Dispose pattern.
   protected virtual void Dispose(bool disposing)
   {
      if (disposed)
         return; 

      if (disposing) {
         // Free any other managed objects here.
         //
      }

      // Free any unmanaged objects here.
      //
      disposed = true;
   }

   ~BaseClass()
   {
      Dispose(false);
   }
}
```

```vb
Class BaseClass : Implements IDisposable
   ' Flag: Has Dispose already been called?
   Dim disposed As Boolean = False

   ' Public implementation of Dispose pattern callable by consumers.
   Public Sub Dispose() _
              Implements IDisposable.Dispose
      Dispose(True)
      GC.SuppressFinalize(Me)           
   End Sub

   ' Protected implementation of Dispose pattern.
   Protected Overridable Sub Dispose(disposing As Boolean)
      If disposed Then Return

      If disposing Then
         ' Free any other managed objects here.
         '
      End If

      ' Free any unmanaged objects here.
      '
      disposed = True
   End Sub

   Protected Overrides Sub Finalize()
      Dispose(False)      
   End Sub
End Class
```

> [!NOTE]
> En C#, invalide [Object.Finalize](xref:System.Object.Finalize) con la definición de `destructor`. 


## <a name="implementing-the-dispose-pattern-for-a-derived-class"></a>Implementación del patrón de Dispose para una clase derivada

Una clase derivada de una clase que implemente la interfaz [IDisposable](xref:System.IDisposable) no debe implementar [IDisposable](xref:System.IDisposable), porque la implementación de la clase base de [IDisposable.Dispose](xref:System.IDisposable.Dispose) la heredan sus clases derivadas. En su lugar, para implementar el patrón de Dispose para una clase derivada, debe proporcionar lo siguiente: 

* Un método `protected Dispose(Boolean)` que invalide el método de la clase base y realice el trabajo real de liberar los recursos de la clase derivada. Este método también debe llamar al método `Dispose(Boolean)` de la clase base y pasarle un valor `true` para el argumento *disposing*. 

* Una clase derivada de [SafeHandle](xref:System.Runtime.InteropServices.SafeHandle) que contiene el recurso no administrado (recomendado), o una invalidación del método [Object.Finalize](xref:System.Object.Finalize). La clase [SafeHandle](xref:System.Runtime.InteropServices.SafeHandle) proporciona un finalizador que evita que tenga que programar uno. Si proporciona un finalizador, debe llamar a la sobrecarga de `Dispose(Boolean)` con un argumento *disposing* que sea `false`. 

A continuación se muestra el patrón general para implementar el patrón de Dispose para una clase derivada que utiliza un controlador seguro: 

```cs
using Microsoft.Win32.SafeHandles;
using System;
using System.Runtime.InteropServices;

class DerivedClass : BaseClass
{
   // Flag: Has Dispose already been called?
   bool disposed = false;
   // Instantiate a SafeHandle instance.
   SafeHandle handle = new SafeFileHandle(IntPtr.Zero, true);

   // Protected implementation of Dispose pattern.
   protected override void Dispose(bool disposing)
   {
      if (disposed)
         return; 

      if (disposing) {
         handle.Dispose();
         // Free any other managed objects here.
         //
      }

      // Free any unmanaged objects here.
      //

      disposed = true;
      // Call base class implementation.
      base.Dispose(disposing);
   }
}
```

```vb
Imports Microsoft.Win32.SafeHandles
Imports System.Runtime.InteropServices

Class DerivedClass : Inherits BaseClass 
   ' Flag: Has Dispose already been called?
   Dim disposed As Boolean = False
   ' Instantiate a SafeHandle instance.
   Dim handle As SafeHandle = New SafeFileHandle(IntPtr.Zero, True)

   ' Protected implementation of Dispose pattern.
   Protected Overrides Sub Dispose(disposing As Boolean)
      If disposed Then Return

      If disposing Then
         handle.Dispose()
         ' Free any other managed objects here.
         '
      End If

      ' Free any unmanaged objects here.
      '
      disposed = True

      ' Call base class implementation.
      MyBase.Dispose(disposing)
   End Sub
End Class
```

> [!NOTE] 
> El ejemplo anterior usa un objeto [SafeFileHandle](xref:Microsoft.Win32.SafeHandles.SafeFileHandle) para ilustrar el patrón; cualquier objeto derivado de [SafeHandle](xref:System.Runtime.InteropServices.SafeHandle) podría usarse en su lugar. Tenga en cuenta que el ejemplo no crea una instancia de su objeto [SafeFileHandle](xref:Microsoft.Win32.SafeHandles.SafeFileHandle) correctamente. 

A continuación se muestra el patrón general para implementar el patrón de Dispose para una clase derivada que invalide a [Object.Finalize](xref:System.Object.Finalize):

```cs
using System;

class DerivedClass : BaseClass
{
   // Flag: Has Dispose already been called?
   bool disposed = false;

   // Protected implementation of Dispose pattern.
   protected override void Dispose(bool disposing)
   {
      if (disposed)
         return; 

      if (disposing) {
         // Free any other managed objects here.
         //
      }

      // Free any unmanaged objects here.
      //
      disposed = true;

      // Call the base class implementation.
      base.Dispose(disposing);
   }

   ~DerivedClass()
   {
      Dispose(false);
   }
}
```

```vb
Class DerivedClass : Inherits BaseClass
   ' Flag: Has Dispose already been called?
   Dim disposed As Boolean = False

   ' Protected implementation of Dispose pattern.
   Protected Overrides Sub Dispose(disposing As Boolean)
      If disposed Then Return

      If disposing Then
         ' Free any other managed objects here.
         '
      End If

      ' Free any unmanaged objects here.
      '
      disposed = True

      ' Call the base class implementation.
      MyBase.Dispose(disposing)
   End Sub

   Protected Overrides Sub Finalize()
      Dispose(False)
   End Sub 
End Class
```

> [!NOTE]
> En C#, invalide [Object.Finalize](xref:System.Object.Finalize) con la definición de `destructor`.

## <a name="using-safe-handles"></a>Uso de controladores seguros

La escritura de código para el finalizador de un objeto es una tarea compleja que puede producir problemas si no se realiza correctamente. Por tanto, se recomienda construir objetos [System.Runtime.InteropServices.SafeHandle](xref:System.Runtime.InteropServices.SafeHandle) en lugar de implementar un finalizador.

Las clases derivadas de la clase [System.Runtime.InteropServices.SafeHandle](xref:System.Runtime.InteropServices.SafeHandle) simplifican los problemas de duración de objetos mediante la asignación y liberación de identificadores sin interrupción. Contienen un finalizador crítico cuya ejecución está garantizada mientras se descarga un dominio de aplicación. Las clases derivadas siguientes en el espacio de nombres [Microsoft.Win32.SafeHandles](xref:Microsoft.Win32.SafeHandles) proporcionan controladores seguros: 

* Las clases [SafeFileHandle](xref:Microsoft.Win32.SafeHandles.SafeFileHandle), [SafeMemoryMappedFileHandle](xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedFileHandle) y [SafePipeHandle](xref:Microsoft.Win32.SafeHandles.SafePipeHandle) para archivos, archivos asignados a la memoria y canalizaciones. 

* La clase [SafeMemoryMappedViewHandle](xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle), para vistas de memoria. 

* Las clases [SafeNCryptKeyHandle](https://msdn.microsoft.com/en-us/library/microsoft.win32.safehandles.safencryptkeyhandle(v=vs.110).aspx), [SafeNCryptProviderHandle](https://msdn.microsoft.com/en-us/library/microsoft.win32.safehandles.safencryptproviderhandle(v=vs.110).aspx) y [SafeNCryptSecretHandle](https://msdn.microsoft.com/en-us/library/microsoft.win32.safehandles.safencryptsecrethandle(v=vs.110).aspx) para construcciones criptográficas.

* La clase [SafeRegistryHandle](xref:Microsoft.Win32.SafeHandles.SafeRegistryHandle) para las claves del registro. 

* La clase [SafeWaitHandle](xref:Microsoft.Win32.SafeHandles.SafeWaitHandle) para identificadores de espera. 

## <a name="using-a-safe-handle-to-implement-the-dispose-pattern-for-a-base-class"></a>Uso de un controlador seguro para implementar el patrón de Dispose para una clase base

En el ejemplo siguiente se muestra el patrón de Dispose para una clase base, `DisposableStreamResource`, que utiliza un controlador seguro para encapsular los recursos no administrados. Define una clase `DisposableResource` que usa [SafeFileHandle](xref:Microsoft.Win32.SafeHandles.SafeFileHandle) para incluir un objeto [Stream](xref:System.IO.Stream) que representa un archivo abierto. El método `DisposableResource` también incluye una propiedad única, `Size`, que devuelve el número total de bytes de la secuencia de archivos. 

```cs
using Microsoft.Win32.SafeHandles;
using System;
using System.IO;
using System.Runtime.InteropServices;

public class DisposableStreamResource : IDisposable
{
   // Define constants.
   protected const uint GENERIC_READ = 0x80000000;
   protected const uint FILE_SHARE_READ = 0x00000001;
   protected const uint OPEN_EXISTING = 3;
   protected const uint FILE_ATTRIBUTE_NORMAL = 0x80;
   protected IntPtr INVALID_HANDLE_VALUE = new IntPtr(-1);
   private const int INVALID_FILE_SIZE = unchecked((int) 0xFFFFFFFF);

   // Define Windows APIs.
   [DllImport("kernel32.dll", EntryPoint = "CreateFileW", CharSet = CharSet.Unicode)]
   protected static extern IntPtr CreateFile (
                                  string lpFileName, uint dwDesiredAccess, 
                                  uint dwShareMode, IntPtr lpSecurityAttributes, 
                                  uint dwCreationDisposition, uint dwFlagsAndAttributes, 
                                  IntPtr hTemplateFile);

   [DllImport("kernel32.dll")]
   private static extern int GetFileSize(SafeFileHandle hFile, out int lpFileSizeHigh);

   // Define locals.
   private bool disposed = false;
   private SafeFileHandle safeHandle; 
   private long bufferSize;
   private int upperWord;

   public DisposableStreamResource(string filename)
   {
      if (filename == null)
         throw new ArgumentNullException("The filename cannot be null.");
      else if (filename == "")
         throw new ArgumentException("The filename cannot be an empty string.");

      IntPtr handle = CreateFile(filename, GENERIC_READ, FILE_SHARE_READ,
                                 IntPtr.Zero, OPEN_EXISTING, FILE_ATTRIBUTE_NORMAL,
                                 IntPtr.Zero);
      if (handle != INVALID_HANDLE_VALUE)
         safeHandle = new SafeFileHandle(handle, true);
      else
         throw new FileNotFoundException(String.Format("Cannot open '{0}'", filename));

      // Get file size.
      bufferSize = GetFileSize(safeHandle, out upperWord); 
      if (bufferSize == INVALID_FILE_SIZE)
         bufferSize = -1;
      else if (upperWord > 0) 
         bufferSize = (((long)upperWord) << 32) + bufferSize;
   }

   public long Size 
   { get { return bufferSize; } }

   public void Dispose()
   {
      Dispose(true);
      GC.SuppressFinalize(this);
   }           

   protected virtual void Dispose(bool disposing)
   {
      if (disposed) return;

      // Dispose of managed resources here.
      if (disposing)
         safeHandle.Dispose();

      // Dispose of any unmanaged resources not wrapped in safe handles.

      disposed = true;
   }  
}
```

```vb
Imports Microsoft.Win32.SafeHandles
Imports System.IO

Public Class DisposableStreamResource : Implements IDisposable
   ' Define constants.
   Protected Const GENERIC_READ As UInteger = &H80000000ui
   Protected Const FILE_SHARE_READ As UInteger = &H0000000i
   Protected Const OPEN_EXISTING As UInteger = 3
   Protected Const FILE_ATTRIBUTE_NORMAL As UInteger = &H80
   Protected INVALID_HANDLE_VALUE As New IntPtr(-1)
   Private Const INVALID_FILE_SIZE As Integer = &HFFFFFFFF

   ' Define Windows APIs.
   Protected Declare Function CreateFile Lib "kernel32" Alias "CreateFileA" (
                                         lpFileName As String, dwDesiredAccess As UInt32, 
                                         dwShareMode As UInt32, lpSecurityAttributes As IntPtr, 
                                         dwCreationDisposition As UInt32, dwFlagsAndAttributes As UInt32, 
                                         hTemplateFile As IntPtr) As IntPtr
   Private Declare Function GetFileSize Lib "kernel32" (hFile As SafeFileHandle, 
                                                        ByRef lpFileSizeHigh As Integer) As Integer

   ' Define locals.
   Private disposed As Boolean = False
   Private safeHandle As SafeFileHandle 
   Private bufferSize As Long 
   Private upperWord As Integer

   Public Sub New(filename As String)
      If filename Is Nothing Then
         Throw New ArgumentNullException("The filename cannot be null.")
      Else If filename = ""
         Throw New ArgumentException("The filename cannot be an empty string.")
      End If

      Dim handle As IntPtr = CreateFile(filename, GENERIC_READ, FILE_SHARE_READ,
                                        IntPtr.Zero, OPEN_EXISTING, FILE_ATTRIBUTE_NORMAL,
                                        IntPtr.Zero)
      If handle <> INVALID_HANDLE_VALUE Then
         safeHandle = New SafeFileHandle(handle, True)
      Else
         Throw New FileNotFoundException(String.Format("Cannot open '{0}'", filename))
      End If

      ' Get file size.
      bufferSize = GetFileSize(safeHandle, upperWord) 
      If bufferSize = INVALID_FILE_SIZE Then
         bufferSize = -1
      Else If upperWord > 0 Then 
         bufferSize = (CLng(upperWord) << 32) + bufferSize
      End If     
   End Sub

   Public ReadOnly Property Size As Long
      Get
         Return bufferSize
      End Get
   End Property

   Public Sub Dispose() _
              Implements IDisposable.Dispose
      Dispose(True)
      GC.SuppressFinalize(Me)
   End Sub           

   Protected Overridable Sub Dispose(disposing As Boolean)
      If disposed Then Exit Sub

      ' Dispose of managed resources here.
      If disposing Then
         safeHandle.Dispose()
      End If

      ' Dispose of any unmanaged resources not wrapped in safe handles.

      disposed = True
   End Sub  
End Class
```

## <a name="using-a-safe-handle-to-implement-the-dispose-pattern-for-a-derived-class"></a>Uso de un controlador seguro para implementar el patrón de Dispose para una clase derivada

En el ejemplo siguiente se muestra el patrón de Dispose para una clase derivada, `DisposableStreamResource2`, que se hereda de la clase `DisposableStreamResource` mostrada en el ejemplo anterior. La clase agrega un método adicional, `WriteFileInfo`, y usa un objeto [SafeFileHandle](xref:Microsoft.Win32.SafeHandles.SafeFileHandle) para incluir el identificador del archivo editable. 

```cs
using Microsoft.Win32.SafeHandles;
using System;
using System.IO;
using System.Runtime.InteropServices;
using System.Threading;

public class DisposableStreamResource2 : DisposableStreamResource
{
   // Define additional constants.
   protected const uint GENERIC_WRITE = 0x40000000; 
   protected const uint OPEN_ALWAYS = 4;

   // Define additional APIs.
   [DllImport("kernel32.dll")]   
   protected static extern bool WriteFile(
                                SafeFileHandle safeHandle, string lpBuffer, 
                                int nNumberOfBytesToWrite, out int lpNumberOfBytesWritten,
                                IntPtr lpOverlapped);

   // Define locals.
   private bool disposed = false;
   private string filename;
   private bool created = false;
   private SafeFileHandle safeHandle;

   public DisposableStreamResource2(string filename) : base(filename)
   {
      this.filename = filename;
   }

   public void WriteFileInfo()
   { 
      if (! created) {
         IntPtr hFile = CreateFile(xref:".\FileInfo.txt", GENERIC_WRITE, 0, 
                                   IntPtr.Zero, OPEN_ALWAYS, 
                                   FILE_ATTRIBUTE_NORMAL, IntPtr.Zero);
         if (hFile != INVALID_HANDLE_VALUE)
            safeHandle = new SafeFileHandle(hFile, true);
         else
            throw new IOException("Unable to create output file.");

         created = true;
      }

      string output = String.Format("{0}: {1:N0} bytes\n", filename, Size);
      int bytesWritten;
      bool result = WriteFile(safeHandle, output, output.Length, out bytesWritten, IntPtr.Zero);                                     
   }

   protected new virtual void Dispose(bool disposing)
   {
      if (disposed) return;

      // Release any managed resources here.
      if (disposing)
         safeHandle.Dispose();

      disposed = true;

      // Release any unmanaged resources not wrapped by safe handles here.

      // Call the base class implementation.
      base.Dispose(true);
   }
}
```

```vb
Imports Microsoft.Win32.SafeHandles
Imports System.IO

Public Class DisposableStreamResource2 : Inherits DisposableStreamResource
   ' Define additional constants.
   Protected Const GENERIC_WRITE As Integer = &H40000000 
   Protected Const OPEN_ALWAYS As Integer = 4

   ' Define additional APIs.
   Protected Declare Function WriteFile Lib "kernel32.dll" (
                              safeHandle As SafeFileHandle, lpBuffer As String, 
                              nNumberOfBytesToWrite As Integer, ByRef lpNumberOfBytesWritten As Integer,
                              lpOverlapped As Object) As Boolean

   ' Define locals.
   Private disposed As Boolean = False
   Private filename As String
   Private created As Boolean = False
   Private safeHandle As SafeFileHandle

   Public Sub New(filename As String)
      MyBase.New(filename)
      Me.filename = filename
   End Sub

   Public Sub WriteFileInfo() 
      If Not created Then
         Dim hFile As IntPtr = CreateFile(".\FileInfo.txt", GENERIC_WRITE, 0, 
                                          IntPtr.Zero, OPEN_ALWAYS, 
                                          FILE_ATTRIBUTE_NORMAL, IntPtr.Zero)
         If hFile <> INVALID_HANDLE_VALUE Then
            safeHandle = New SafeFileHandle(hFile, True)
         Else
            Throw New IOException("Unable to create output file.")
         End If
         created = True
      End If
      Dim output As String = String.Format("{0}: {1:N0} bytes {2}", filename, Size, 
                                           vbCrLf)
      WriteFile(safeHandle, output, output.Length, 0&, Nothing)                                     
   End Sub

   Protected Overloads Overridable Sub Dispose(disposing As Boolean)
      If disposed Then Exit Sub

      ' Release any managed resources here.
      If disposing Then
         safeHandle.Dispose()
      End If

      disposed = True
      ' Release any unmanaged resources not wrapped by safe handles here.

      ' Call the base class implementation.
      MyBase.Dispose(True)
   End Sub
End Class
```

## <a name="see-also"></a>Vea también

[SuppressFinalize](xref:System.GC.SuppressFinalize(System.Object))

[IDisposable](xref:System.IDisposable)

[IDisposable.Dispose](xref:System.IDisposable.Dispose)

[Microsoft.Win32.SafeHandles](xref:Microsoft.Win32.SafeHandles)

[System.Runtime.InteropServices.SafeHandle](xref:System.Runtime.InteropServices.SafeHandle)

[IDisposable.Dispose](xref:System.IDisposable.Dispose)



<!--HONumber=Nov16_HO1-->


