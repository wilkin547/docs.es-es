---
title: Crear prototipos en código administrado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- prototypes in managed code
- COM interop, DLL functions
- unmanaged functions
- platform invoke, creating prototypes
- COM interop, platform invoke
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- platform invoke, object fields
- DLL functions
- object fields in platform invoke
ms.assetid: ecdcf25d-cae3-4f07-a2b6-8397ac6dc42d
ms.openlocfilehash: 712040c3482b51c4dafe0ee87fdda8cd848fb7fc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123614"
---
# <a name="creating-prototypes-in-managed-code"></a>Crear prototipos en código administrado
En este tema se describe cómo acceder a funciones no administradas y presenta varios campos de atributo que anotan la definición de método en el código administrado. Para obtener ejemplos que muestran cómo construir declaraciones basadas en .NET para usarse con la invocación de plataforma, vea [Serialización de datos con invocación de plataforma](marshaling-data-with-platform-invoke.md).  
  
 Antes de poder acceder a una función DLL no administrada desde código administrado, deberá conocer el nombre de la función y el nombre del archivo DLL que la exporta. Con esta información, puede empezar a escribir la definición administrada de una función no administrada que se implementa en un archivo DLL. Además, puede ajustar la manera en que la invocación de plataforma crea la función y calcula las referencias de los datos desde y hacia la función.  
  
> [!NOTE]
> Las funciones de la API de Windows que asignan una cadena permiten liberar la cadena mediante un método como `LocalFree`. La invocación de plataforma controla estos parámetros de forma diferente. Para las llamadas de invocación de plataforma, haga que el parámetro sea del tipo `IntPtr` en lugar del tipo `String`. Use los métodos que proporciona la clase <xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType> para convertir el tipo a una cadena manualmente y liberarla manualmente.  
  
## <a name="declaration-basics"></a>Conceptos básicos de declaración  
 Las definiciones administradas de funciones no administradas dependen del lenguaje, como puede ver en los ejemplos siguientes. Para obtener ejemplos de código más completos, vea [Ejemplos de invocación de plataforma](platform-invoke-examples.md).  
  
```vb
Friend Class NativeMethods
    Friend Declare Auto Function MessageBox Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
End Class
```
  
 Para aplicar los campos <xref:System.Runtime.InteropServices.DllImportAttribute.BestFitMapping?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.CallingConvention?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError?displayProperty=nameWithType> o <xref:System.Runtime.InteropServices.DllImportAttribute.ThrowOnUnmappableChar?displayProperty=nameWithType> a una declaración de Visual Basic, debe usar el atributo <xref:System.Runtime.InteropServices.DllImportAttribute> en lugar de la instrucción `Declare`.  
  
```vb
Imports System.Runtime.InteropServices

Friend Class NativeMethods
    <DllImport("user32.dll", CharSet:=CharSet.Auto)>
    Friend Shared Function MessageBox(
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
    End Function
End Class
```
  
```csharp
using System;
using System.Runtime.InteropServices;

internal static class NativeMethods
{
    [DllImport("user32.dll")]
    internal static extern int MessageBox(
        IntPtr hWnd, string lpText, string lpCaption, uint uType);
}
```
  
```cpp
using namespace System;
using namespace System::Runtime::InteropServices;

[DllImport("user32.dll")]
extern "C" int MessageBox(
    IntPtr hWnd, String* lpText, String* lpCaption, unsigned int uType);
```
  
## <a name="adjusting-the-definition"></a>Ajustar la definición  
 Tanto si se establece explícitamente como si no, los campos de atributo definen el comportamiento del código administrado. La invocación de plataforma funciona según los valores predeterminados establecidos en diversos campos que existen como metadatos en un ensamblado. Puede modificar este comportamiento predeterminado ajustando los valores de uno o más campos. En muchos casos, se usa <xref:System.Runtime.InteropServices.DllImportAttribute> para establecer un valor.  
  
 En la tabla siguiente se muestra el conjunto completo de campos de atributo que pertenecen a la invocación de plataforma. Para cada campo, la tabla incluye el valor predeterminado y un vínculo a información sobre cómo usar estos campos para definir funciones DLL no administradas.  
  
|Campo|Descripción|  
|-----------|-----------------|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.BestFitMapping>|Habilita o deshabilita la asignación con ajuste perfecto.|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.CallingConvention>|Especifica la convención de llamada que se usará al pasar argumentos de método. El valor predeterminado es `WinAPI`, que corresponde a `__stdcall` para las plataformas de 32 bits basadas en Intel.|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.CharSet>|Controla la eliminación de nombres y la forma en que deben calcularse las referencias de los argumentos de cadena a la función. De manera predeterminada, es `CharSet.Ansi`.|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>|Especifica el punto de entrada DLL al que se debe llamar.|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling>|Controla si un punto de entrada debe modificarse para que coincida con el juego de caracteres. El valor predeterminado varía según el lenguaje de programación.|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig>|Controla si la firma del método administrado debería transformarse en una firma no administrada que devuelve un resultado HRESULT y tiene un argumento adicional [out, retval] para el valor devuelto.<br /><br /> El valor predeterminado es `true` (la firma no debe transformarse).|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError>|Permite al llamador usar la función `Marshal.GetLastWin32Error` de la API para determinar si se produjo un error al ejecutar el método. En Visual Basic, el valor predeterminado es `true`; en C# y C++, el valor predeterminado es `false`.|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.ThrowOnUnmappableChar>|Controla el inicio de una excepción cuando un carácter Unicode que no se puede asignar se convierte en un carácter ANSI "?".|  
  
 Para obtener información de referencia detallada, vea <xref:System.Runtime.InteropServices.DllImportAttribute>.  
  
## <a name="platform-invoke-security-considerations"></a>Consideraciones sobre la seguridad de la invocación de plataforma  
 Los miembros `Assert`, `Deny` y `PermitOnly` de la enumeración <xref:System.Security.Permissions.SecurityAction> se conocen como *modificadores del recorrido de la pila*. Estos miembros se omiten si se usan como atributos declarativos en declaraciones de invocación de plataforma e instrucciones del lenguaje de definición de interfaz (IDL) COM.  
  
### <a name="platform-invoke-examples"></a>Ejemplos de invocación de plataforma  
 Los ejemplos de invocación de plataforma de esta sección muestran el uso del atributo `RegistryPermission` con los modificadores del recorrido de la pila.  
  
 En el ejemplo siguiente se omiten los modificadores <xref:System.Security.Permissions.SecurityAction>`Assert`, `Deny` y `PermitOnly`.  
  
```csharp  
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
[RegistryPermission(SecurityAction.Assert, Unrestricted = true)]  
    private static extern bool CallRegistryPermissionAssert();  
  
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
[RegistryPermission(SecurityAction.Deny, Unrestricted = true)]  
    private static extern bool CallRegistryPermissionDeny();  
  
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
[RegistryPermission(SecurityAction.PermitOnly, Unrestricted = true)]  
    private static extern bool CallRegistryPermissionDeny();  
```  
  
 Sin embargo, el modificador `Demand` se acepta en el siguiente ejemplo.  
  
```csharp
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
[RegistryPermission(SecurityAction.Demand, Unrestricted = true)]  
    private static extern bool CallRegistryPermissionDeny();  
```  
  
 Los modificadores <xref:System.Security.Permissions.SecurityAction> funcionan correctamente si se colocan en una clase que contiene (encapsula) la llamada de invocación de plataforma.  
  
```cpp  
      [RegistryPermission(SecurityAction.Demand, Unrestricted = true)]  
public ref class PInvokeWrapper  
{  
public:  
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
    private static extern bool CallRegistryPermissionDeny();  
};  
```  
  
```csharp  
[RegistryPermission(SecurityAction.Demand, Unrestricted = true)]  
class PInvokeWrapper  
{  
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
    private static extern bool CallRegistryPermissionDeny();  
}  
```  
  
 Los modificadores <xref:System.Security.Permissions.SecurityAction> también funcionan correctamente en un escenario anidado en el que se colocan en el llamador de la llamada de invocación de plataforma:  
  
```cpp  
      {  
public ref class PInvokeWrapper  
public:  
    [DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
    private static extern bool CallRegistryPermissionDeny();  
  
    [RegistryPermission(SecurityAction.Demand, Unrestricted = true)]  
    public static bool CallRegistryPermission()  
    {  
     return CallRegistryPermissionInternal();  
    }  
};  
```  
  
```csharp  
class PInvokeScenario  
{  
    [DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
    private static extern bool CallRegistryPermissionInternal();  
  
    [RegistryPermission(SecurityAction.Assert, Unrestricted = true)]  
    public static bool CallRegistryPermission()  
    {  
     return CallRegistryPermissionInternal();  
    }  
}  
```  
  
#### <a name="com-interop-examples"></a>Ejemplos de interoperabilidad COM  
 Los ejemplos de interoperabilidad COM de esta sección muestran el uso del atributo `RegistryPermission` con los modificadores del recorrido de la pila.  
  
 Las siguientes declaraciones de interfaz de interoperabilidad COM omiten los modificadores `Assert`, `Deny` y `PermitOnly`, de forma similar a los ejemplos de invocación de plataforma de la sección anterior.  
  
```csharp
[ComImport, Guid("12345678-43E6-43c9-9A13-47F40B338DE0")]  
interface IAssertStubsItf  
{  
[RegistryPermission(SecurityAction.Assert, Unrestricted = true)]  
    bool CallRegistryPermission();  
[FileIOPermission(SecurityAction.Assert, Unrestricted = true)]  
    bool CallFileIoPermission();  
}  
  
[ComImport, Guid("12345678-43E6-43c9-9A13-47F40B338DE0")]  
interface IDenyStubsItf  
{  
[RegistryPermission(SecurityAction.Deny, Unrestricted = true)]  
    bool CallRegistryPermission();  
[FileIOPermission(SecurityAction.Deny, Unrestricted = true)]  
    bool CallFileIoPermission();  
}  
  
[ComImport, Guid("12345678-43E6-43c9-9A13-47F40B338DE0")]  
interface IAssertStubsItf  
{  
[RegistryPermission(SecurityAction.PermitOnly, Unrestricted = true)]  
    bool CallRegistryPermission();  
[FileIOPermission(SecurityAction.PermitOnly, Unrestricted = true)]  
    bool CallFileIoPermission();  
}  
```  
  
 Además, el modificador `Demand` no se acepta en escenarios de declaración de interfaz de interoperabilidad COM, tal y como se muestra en el ejemplo siguiente.  
  
```csharp  
[ComImport, Guid("12345678-43E6-43c9-9A13-47F40B338DE0")]  
interface IDemandStubsItf  
{  
[RegistryPermission(SecurityAction.Demand, Unrestricted = true)]  
    bool CallRegistryPermission();  
[FileIOPermission(SecurityAction.Demand, Unrestricted = true)]  
    bool CallFileIoPermission();  
}  
```  
  
## <a name="see-also"></a>Vea también

- [Consumir funciones DLL no administradas](consuming-unmanaged-dll-functions.md)
- [Especificar un punto de entrada](specifying-an-entry-point.md)
- [Especificar un juego de caracteres](specifying-a-character-set.md)
- [Ejemplos de invocación de plataforma](platform-invoke-examples.md)
- [Consideraciones de seguridad de la invocación de plataforma](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb397754(v=vs.100))
- [Identificar funciones en archivos DLL](identifying-functions-in-dlls.md)
- [Creación de una clase para contener funciones de archivos DLL](creating-a-class-to-hold-dll-functions.md)
- [Llamar a una función DLL](calling-a-dll-function.md)
