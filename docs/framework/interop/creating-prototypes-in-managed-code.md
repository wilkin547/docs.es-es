---
title: Crear prototipos en código administrado
description: Cree prototipos en código administrado de .NET, de modo que pueda acceder a funciones no administradas y usar campos de atributos que anotan la definición del método en el código administrado.
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
ms.openlocfilehash: 76b1a87c4513fdee21c5c3d5eba533b11e022e3a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622164"
---
# <a name="creating-prototypes-in-managed-code"></a><span data-ttu-id="868fa-103">Crear prototipos en código administrado</span><span class="sxs-lookup"><span data-stu-id="868fa-103">Creating Prototypes in Managed Code</span></span>
<span data-ttu-id="868fa-104">En este tema se describe cómo acceder a funciones no administradas y presenta varios campos de atributo que anotan la definición de método en el código administrado.</span><span class="sxs-lookup"><span data-stu-id="868fa-104">This topic describes how to access unmanaged functions and introduces several attribute fields that annotate method definition in managed code.</span></span> <span data-ttu-id="868fa-105">Para obtener ejemplos que muestran cómo construir declaraciones basadas en .NET para usarse con la invocación de plataforma, vea [Serialización de datos con invocación de plataforma](marshaling-data-with-platform-invoke.md).</span><span class="sxs-lookup"><span data-stu-id="868fa-105">For examples that demonstrate how to construct .NET-based declarations to be used with platform invoke, see [Marshaling Data with Platform Invoke](marshaling-data-with-platform-invoke.md).</span></span>  
  
 <span data-ttu-id="868fa-106">Antes de poder acceder a una función DLL no administrada desde código administrado, deberá conocer el nombre de la función y el nombre del archivo DLL que la exporta.</span><span class="sxs-lookup"><span data-stu-id="868fa-106">Before you can access an unmanaged DLL function from managed code, you need to know the name of the function and the name of the DLL that exports it.</span></span> <span data-ttu-id="868fa-107">Con esta información, puede empezar a escribir la definición administrada de una función no administrada que se implementa en un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="868fa-107">With this information, you can begin to write the managed definition for an unmanaged function that is implemented in a DLL.</span></span> <span data-ttu-id="868fa-108">Además, puede ajustar la manera en que la invocación de plataforma crea la función y calcula las referencias de los datos desde y hacia la función.</span><span class="sxs-lookup"><span data-stu-id="868fa-108">Furthermore, you can adjust the way that platform invoke creates the function and marshals data to and from the function.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="868fa-109">Las funciones de la API de Windows que asignan una cadena permiten liberar la cadena mediante un método como `LocalFree`.</span><span class="sxs-lookup"><span data-stu-id="868fa-109">Windows API functions that allocate a string enable you to free the string by using a method such as `LocalFree`.</span></span> <span data-ttu-id="868fa-110">La invocación de plataforma controla estos parámetros de forma diferente.</span><span class="sxs-lookup"><span data-stu-id="868fa-110">Platform invoke handles such parameters differently.</span></span> <span data-ttu-id="868fa-111">Para las llamadas de invocación de plataforma, haga que el parámetro sea del tipo `IntPtr` en lugar del tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="868fa-111">For platform invoke calls, make the parameter an `IntPtr` type instead of a `String` type.</span></span> <span data-ttu-id="868fa-112">Use los métodos que proporciona la clase <xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType> para convertir el tipo a una cadena manualmente y liberarla manualmente.</span><span class="sxs-lookup"><span data-stu-id="868fa-112">Use methods that are provided by the <xref:System.Runtime.InteropServices.Marshal?displayProperty=nameWithType> class to convert the type to a string manually and free it manually.</span></span>  
  
## <a name="declaration-basics"></a><span data-ttu-id="868fa-113">Conceptos básicos de declaración</span><span class="sxs-lookup"><span data-stu-id="868fa-113">Declaration Basics</span></span>  
 <span data-ttu-id="868fa-114">Las definiciones administradas de funciones no administradas dependen del lenguaje, como puede ver en los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="868fa-114">Managed definitions to unmanaged functions are language-dependent, as you can see in the following examples.</span></span> <span data-ttu-id="868fa-115">Para obtener ejemplos de código más completos, vea [Ejemplos de invocación de plataforma](platform-invoke-examples.md).</span><span class="sxs-lookup"><span data-stu-id="868fa-115">For more complete code examples, see [Platform Invoke Examples](platform-invoke-examples.md).</span></span>  
  
```vb
Friend Class NativeMethods
    Friend Declare Auto Function MessageBox Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
End Class
```
  
 <span data-ttu-id="868fa-116">Para aplicar los campos <xref:System.Runtime.InteropServices.DllImportAttribute.BestFitMapping?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.CallingConvention?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError?displayProperty=nameWithType> o <xref:System.Runtime.InteropServices.DllImportAttribute.ThrowOnUnmappableChar?displayProperty=nameWithType> a una declaración de Visual Basic, debe usar el atributo <xref:System.Runtime.InteropServices.DllImportAttribute> en lugar de la instrucción `Declare`.</span><span class="sxs-lookup"><span data-stu-id="868fa-116">To apply the <xref:System.Runtime.InteropServices.DllImportAttribute.BestFitMapping?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.CallingConvention?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig?displayProperty=nameWithType>, <xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError?displayProperty=nameWithType>, or <xref:System.Runtime.InteropServices.DllImportAttribute.ThrowOnUnmappableChar?displayProperty=nameWithType> fields to a Visual Basic declaration, you must use the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute instead of the `Declare` statement.</span></span>  
  
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
  
## <a name="adjusting-the-definition"></a><span data-ttu-id="868fa-117">Ajustar la definición</span><span class="sxs-lookup"><span data-stu-id="868fa-117">Adjusting the Definition</span></span>  
 <span data-ttu-id="868fa-118">Tanto si se establece explícitamente como si no, los campos de atributo definen el comportamiento del código administrado.</span><span class="sxs-lookup"><span data-stu-id="868fa-118">Whether you set them explicitly or not, attribute fields are at work defining the behavior of managed code.</span></span> <span data-ttu-id="868fa-119">La invocación de plataforma funciona según los valores predeterminados establecidos en diversos campos que existen como metadatos en un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="868fa-119">Platform invoke operates according to the default values set on various fields that exist as metadata in an assembly.</span></span> <span data-ttu-id="868fa-120">Puede modificar este comportamiento predeterminado ajustando los valores de uno o más campos.</span><span class="sxs-lookup"><span data-stu-id="868fa-120">You can alter this default behavior by adjusting the values of one or more fields.</span></span> <span data-ttu-id="868fa-121">En muchos casos, se usa <xref:System.Runtime.InteropServices.DllImportAttribute> para establecer un valor.</span><span class="sxs-lookup"><span data-stu-id="868fa-121">In many cases, you use the <xref:System.Runtime.InteropServices.DllImportAttribute> to set a value.</span></span>  
  
 <span data-ttu-id="868fa-122">En la tabla siguiente se muestra el conjunto completo de campos de atributo que pertenecen a la invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="868fa-122">The following table lists the complete set of attribute fields that pertain to platform invoke.</span></span> <span data-ttu-id="868fa-123">Para cada campo, la tabla incluye el valor predeterminado y un vínculo a información sobre cómo usar estos campos para definir funciones DLL no administradas.</span><span class="sxs-lookup"><span data-stu-id="868fa-123">For each field, the table includes the default value and a link to information on how to use these fields to define unmanaged DLL functions.</span></span>  
  
|<span data-ttu-id="868fa-124">Campo</span><span class="sxs-lookup"><span data-stu-id="868fa-124">Field</span></span>|<span data-ttu-id="868fa-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="868fa-125">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.BestFitMapping>|<span data-ttu-id="868fa-126">Habilita o deshabilita la asignación con ajuste perfecto.</span><span class="sxs-lookup"><span data-stu-id="868fa-126">Enables or disables best-fit mapping.</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.CallingConvention>|<span data-ttu-id="868fa-127">Especifica la convención de llamada que se usará al pasar argumentos de método.</span><span class="sxs-lookup"><span data-stu-id="868fa-127">Specifies the calling convention to use in passing method arguments.</span></span> <span data-ttu-id="868fa-128">El valor predeterminado es `WinAPI`, que corresponde a `__stdcall` para las plataformas de 32 bits basadas en Intel.</span><span class="sxs-lookup"><span data-stu-id="868fa-128">The default is `WinAPI`, which corresponds to `__stdcall` for the 32-bit Intel-based platforms.</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.CharSet>|<span data-ttu-id="868fa-129">Controla la eliminación de nombres y la forma en que deben calcularse las referencias de los argumentos de cadena a la función.</span><span class="sxs-lookup"><span data-stu-id="868fa-129">Controls name mangling and the way that string arguments should be marshaled to the function.</span></span> <span data-ttu-id="868fa-130">De manera predeterminada, es `CharSet.Ansi`.</span><span class="sxs-lookup"><span data-stu-id="868fa-130">The default is `CharSet.Ansi`.</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>|<span data-ttu-id="868fa-131">Especifica el punto de entrada DLL al que se debe llamar.</span><span class="sxs-lookup"><span data-stu-id="868fa-131">Specifies the DLL entry point to be called.</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling>|<span data-ttu-id="868fa-132">Controla si un punto de entrada debe modificarse para que coincida con el juego de caracteres.</span><span class="sxs-lookup"><span data-stu-id="868fa-132">Controls whether an entry point should be modified to correspond to the character set.</span></span> <span data-ttu-id="868fa-133">El valor predeterminado varía según el lenguaje de programación.</span><span class="sxs-lookup"><span data-stu-id="868fa-133">The default value varies by programming language.</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig>|<span data-ttu-id="868fa-134">Controla si la firma del método administrado debería transformarse en una firma no administrada que devuelve un resultado HRESULT y tiene un argumento adicional [out, retval] para el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="868fa-134">Controls whether the managed method signature should be transformed into an unmanaged signature that returns an HRESULT and has an additional [out, retval] argument for the return value.</span></span><br /><br /> <span data-ttu-id="868fa-135">El valor predeterminado es `true` (la firma no debe transformarse).</span><span class="sxs-lookup"><span data-stu-id="868fa-135">The default is `true` (the signature should not be transformed).</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError>|<span data-ttu-id="868fa-136">Permite al llamador usar la función `Marshal.GetLastWin32Error` de la API para determinar si se produjo un error al ejecutar el método.</span><span class="sxs-lookup"><span data-stu-id="868fa-136">Enables the caller to use the `Marshal.GetLastWin32Error` API function to determine whether an error occurred while executing the method.</span></span> <span data-ttu-id="868fa-137">En Visual Basic, el valor predeterminado es `true`; en C# y C++, el valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="868fa-137">In Visual Basic, the default is `true`; in C# and C++, the default is `false`.</span></span>|  
|<xref:System.Runtime.InteropServices.DllImportAttribute.ThrowOnUnmappableChar>|<span data-ttu-id="868fa-138">Controla el inicio de una excepción cuando un carácter Unicode que no se puede asignar se convierte en un carácter ANSI "?".</span><span class="sxs-lookup"><span data-stu-id="868fa-138">Controls throwing of an exception on an unmappable Unicode character that is converted to an ANSI "?" character.</span></span>|  
  
 <span data-ttu-id="868fa-139">Para obtener información de referencia detallada, vea <xref:System.Runtime.InteropServices.DllImportAttribute>.</span><span class="sxs-lookup"><span data-stu-id="868fa-139">For detailed reference information, see <xref:System.Runtime.InteropServices.DllImportAttribute>.</span></span>  
  
## <a name="platform-invoke-security-considerations"></a><span data-ttu-id="868fa-140">Consideraciones sobre la seguridad de la invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="868fa-140">Platform invoke security considerations</span></span>  
 <span data-ttu-id="868fa-141">Los miembros `Assert`, `Deny` y `PermitOnly` de la enumeración <xref:System.Security.Permissions.SecurityAction> se conocen como *modificadores del recorrido de la pila*.</span><span class="sxs-lookup"><span data-stu-id="868fa-141">The `Assert`, `Deny`, and `PermitOnly` members of the <xref:System.Security.Permissions.SecurityAction> enumeration are referred to as *stack walk modifiers*.</span></span> <span data-ttu-id="868fa-142">Estos miembros se omiten si se usan como atributos declarativos en declaraciones de invocación de plataforma e instrucciones del lenguaje de definición de interfaz (IDL) COM.</span><span class="sxs-lookup"><span data-stu-id="868fa-142">These members are ignored if they are used as declarative attributes on platform invoke declarations and COM Interface Definition Language (IDL) statements.</span></span>  
  
### <a name="platform-invoke-examples"></a><span data-ttu-id="868fa-143">Ejemplos de invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="868fa-143">Platform Invoke Examples</span></span>  
 <span data-ttu-id="868fa-144">Los ejemplos de invocación de plataforma de esta sección muestran el uso del atributo `RegistryPermission` con los modificadores del recorrido de la pila.</span><span class="sxs-lookup"><span data-stu-id="868fa-144">The platform invoke samples in this section illustrate the use of the `RegistryPermission` attribute with the stack walk modifiers.</span></span>  
  
 <span data-ttu-id="868fa-145">En el ejemplo siguiente se omiten los modificadores <xref:System.Security.Permissions.SecurityAction>`Assert`, `Deny` y `PermitOnly`.</span><span class="sxs-lookup"><span data-stu-id="868fa-145">In the following example, the <xref:System.Security.Permissions.SecurityAction>`Assert`, `Deny`, and `PermitOnly` modifiers are ignored.</span></span>  
  
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
  
 <span data-ttu-id="868fa-146">Sin embargo, el modificador `Demand` se acepta en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="868fa-146">However, the `Demand` modifier in the following example is accepted.</span></span>  
  
```csharp
[DllImport("MyClass.dll", EntryPoint = "CallRegistryPermission")]  
[RegistryPermission(SecurityAction.Demand, Unrestricted = true)]  
    private static extern bool CallRegistryPermissionDeny();  
```  
  
 <span data-ttu-id="868fa-147">Los modificadores <xref:System.Security.Permissions.SecurityAction> funcionan correctamente si se colocan en una clase que contiene (encapsula) la llamada de invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="868fa-147"><xref:System.Security.Permissions.SecurityAction> modifiers do work correctly if they are placed on a class that contains (wraps) the platform invoke call.</span></span>  
  
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
  
 <span data-ttu-id="868fa-148">Los modificadores <xref:System.Security.Permissions.SecurityAction> también funcionan correctamente en un escenario anidado en el que se colocan en el llamador de la llamada de invocación de plataforma:</span><span class="sxs-lookup"><span data-stu-id="868fa-148"><xref:System.Security.Permissions.SecurityAction> modifiers also work correctly in a nested scenario where they are placed on the caller of the platform invoke call:</span></span>  
  
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
  
#### <a name="com-interop-examples"></a><span data-ttu-id="868fa-149">Ejemplos de interoperabilidad COM</span><span class="sxs-lookup"><span data-stu-id="868fa-149">COM Interop Examples</span></span>  
 <span data-ttu-id="868fa-150">Los ejemplos de interoperabilidad COM de esta sección muestran el uso del atributo `RegistryPermission` con los modificadores del recorrido de la pila.</span><span class="sxs-lookup"><span data-stu-id="868fa-150">The COM interop samples in this section illustrate the use of the `RegistryPermission` attribute with the stack walk modifiers.</span></span>  
  
 <span data-ttu-id="868fa-151">Las siguientes declaraciones de interfaz de interoperabilidad COM omiten los modificadores `Assert`, `Deny` y `PermitOnly`, de forma similar a los ejemplos de invocación de plataforma de la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="868fa-151">The following COM interop interface declarations ignore the `Assert`, `Deny`, and `PermitOnly` modifiers, similarly to the platform invoke examples in the previous section.</span></span>  
  
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
  
 <span data-ttu-id="868fa-152">Además, el modificador `Demand` no se acepta en escenarios de declaración de interfaz de interoperabilidad COM, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="868fa-152">Additionally, the `Demand` modifier is not accepted in COM interop interface declaration scenarios, as shown in the following example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="868fa-153">Vea también</span><span class="sxs-lookup"><span data-stu-id="868fa-153">See also</span></span>

- [<span data-ttu-id="868fa-154">Consumir funciones DLL no administradas</span><span class="sxs-lookup"><span data-stu-id="868fa-154">Consuming Unmanaged DLL Functions</span></span>](consuming-unmanaged-dll-functions.md)
- [<span data-ttu-id="868fa-155">Especificar un punto de entrada</span><span class="sxs-lookup"><span data-stu-id="868fa-155">Specifying an Entry Point</span></span>](specifying-an-entry-point.md)
- [<span data-ttu-id="868fa-156">Especificar un juego de caracteres</span><span class="sxs-lookup"><span data-stu-id="868fa-156">Specifying a Character Set</span></span>](specifying-a-character-set.md)
- [<span data-ttu-id="868fa-157">Ejemplos de invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="868fa-157">Platform Invoke Examples</span></span>](platform-invoke-examples.md)
- <span data-ttu-id="868fa-158">[Consideraciones de seguridad de la invocación de plataforma](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb397754(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="868fa-158">[Platform Invoke Security Considerations](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb397754(v=vs.100))</span></span>
- [<span data-ttu-id="868fa-159">Identificar funciones en archivos DLL</span><span class="sxs-lookup"><span data-stu-id="868fa-159">Identifying Functions in DLLs</span></span>](identifying-functions-in-dlls.md)
- [<span data-ttu-id="868fa-160">Creación de una clase para contener funciones de archivos DLL</span><span class="sxs-lookup"><span data-stu-id="868fa-160">Creating a Class to Hold DLL Functions</span></span>](creating-a-class-to-hold-dll-functions.md)
- [<span data-ttu-id="868fa-161">Llamar a una función DLL</span><span class="sxs-lookup"><span data-stu-id="868fa-161">Calling a DLL Function</span></span>](calling-a-dll-function.md)
