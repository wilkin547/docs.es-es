---
title: Especificar un punto de entrada
ms.date: 03/30/2017
helpviewer_keywords:
- EntryPoint field
- platform invoke, attribute fields
- attribute fields in platform invoke, EntryPoint
ms.assetid: d1247f08-0965-416a-b978-e0b50652dfe3
ms.openlocfilehash: c5f8f735dd3e8c359f88044a532c29303237acc8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181310"
---
# <a name="specifying-an-entry-point"></a>Especificar un punto de entrada

Un punto de entrada identifica la ubicación de una función en un archivo DLL. En un proyecto administrado, el nombre original o el punto de entrada ordinal de una función de destino identifica dicha función dentro de los límites de la interoperabilidad. Además, puede asignarle otro nombre al punto de entrada, lo que supone en realidad un cambio de nombre de la función.  
  
 La siguiente es una lista de posibles razones para cambiar el nombre de una función DLL:  
  
- Para no utilizar nombres de función de la API que distinguen mayúsculas de minúsculas  
  
- Para cumplir los estándares de nomenclatura existentes  
  
- Para incluir funciones que toman tipos de datos distintos (declarando varias versiones de la misma función de un archivo DLL)  
  
- Para simplificar el uso de las API que contienen versiones ANSI y Unicode  
  
 En este tema se muestra la forma de cambiar el nombre de una función de un archivo DLL en código administrado.  
  
## <a name="renaming-a-function-in-visual-basic"></a>Cambiar el nombre de una función en Visual Basic  

Visual Basic usa la palabra clave **Function** en la instrucción **Declare** para establecer el campo <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType>. En el siguiente ejemplo muestra una declaración básica.  
  
```vb
Friend Class NativeMethods
    Friend Declare Auto Function MessageBox Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
End Class
```
  
Es posible reemplazar el punto de entrada **MessageBox** por **MsgBox** incluyendo la palabra clave **Alias** en la definición, tal y como se muestra en el ejemplo siguiente. En los dos ejemplos, la palabra clave **Auto** elimina la necesidad de especificar la versión del juego de caracteres del punto de entrada. Para obtener más información sobre cómo seleccionar un juego de caracteres, vea [Specifying a Character Set](specifying-a-character-set.md) (Especificar un juego de caracteres).  
  
```vb
Friend Class NativeMethods
    Friend Declare Auto Function MsgBox _
        Lib "user32.dll" Alias "MessageBox" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
End Class
```
  
## <a name="renaming-a-function-in-c-and-c"></a>Cambiar el nombre de una función en C# y C++  
 Puede utilizar el campo <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> para especificar una función DLL por nombre u ordinal. Si el nombre de la función en la definición del método es el mismo que el punto de entrada en el archivo DLL, no es necesario identificar la función de forma explícita con el campo **EntryPoint**. En caso contrario, utilice una de las siguientes formas de atributo para indicar un nombre u ordinal:  
  
```csharp
[DllImport("DllName", EntryPoint = "Functionname")]
[DllImport("DllName", EntryPoint = "#123")]
```
  
 Tenga en cuenta que los ordinales deben ir precedidos del símbolo de libra esterlina (#).  
  
 En el siguiente ejemplo se muestra cómo reemplazar **MessageBoxA** por **MsgBox** en el código usando el campo **EntryPoint**.  
  
```csharp
using System;
using System.Runtime.InteropServices;

internal static class NativeMethods
{
    [DllImport("user32.dll", EntryPoint = "MessageBoxA")]
    internal static extern int MessageBox(
        IntPtr hWnd, string lpText, string lpCaption, uint uType);
}
```
  
```cpp
using namespace System;
using namespace System::Runtime::InteropServices;

typedef void* HWND;
[DllImport("user32", EntryPoint = "MessageBoxA")]
extern "C" int MsgBox(
    HWND hWnd, String* lpText, String* lpCaption, unsigned int uType);
```
  
## <a name="see-also"></a>Consulte también

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [Crear prototipos en código administrado](creating-prototypes-in-managed-code.md)
- [Ejemplos de invocación de plataforma](platform-invoke-examples.md)
- [Serialización de datos con invocación de plataforma](marshaling-data-with-platform-invoke.md)
