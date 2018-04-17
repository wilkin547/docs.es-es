---
title: Cálculo de referencias predeterminado para cadenas
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings, interop marshaling
- interop marshaling, strings
ms.assetid: 9baea3ce-27b3-4b4f-af98-9ad0f9467e6f
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 10f2c0e0e61190f571ae5bd4998f54d128448296
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="default-marshaling-for-strings"></a><span data-ttu-id="6cb02-102">Serialización predeterminada para cadenas</span><span class="sxs-lookup"><span data-stu-id="6cb02-102">Default Marshaling for Strings</span></span>
<span data-ttu-id="6cb02-103">Las clases <xref:System.String?displayProperty=nameWithType> y <xref:System.Text.StringBuilder?displayProperty=nameWithType> tienen un comportamiento de cálculo de referencias similar.</span><span class="sxs-lookup"><span data-stu-id="6cb02-103">Both the <xref:System.String?displayProperty=nameWithType> and <xref:System.Text.StringBuilder?displayProperty=nameWithType> classes have similar marshaling behavior.</span></span>  
  
 <span data-ttu-id="6cb02-104">Las referencias de las cadenas se calculan como un tipo `BSTR` de estilo COM o como una cadena terminada en NULL (una matriz de caracteres que termina con un carácter NULL).</span><span class="sxs-lookup"><span data-stu-id="6cb02-104">Strings are marshaled as a COM-style `BSTR` type or as a null-terminated string (a character array that ends with a null character).</span></span> <span data-ttu-id="6cb02-105">Las referencias de los caracteres dentro de la cadena se pueden calcular como ANSI o Unicode (el valor predeterminado en los sistemas Windows).</span><span class="sxs-lookup"><span data-stu-id="6cb02-105">The characters within the string can be marshaled as Unicode (the default on Windows systems) or ANSI.</span></span>  
  
 <span data-ttu-id="6cb02-106">En este tema se proporciona la siguiente información sobre la serialización de tipos de cadena:</span><span class="sxs-lookup"><span data-stu-id="6cb02-106">This topic provides the following information on marshaling string types:</span></span>  
  
-   [<span data-ttu-id="6cb02-107">Cadenas usadas en interfaces</span><span class="sxs-lookup"><span data-stu-id="6cb02-107">Strings Used in Interfaces</span></span>](#cpcondefaultmarshalingforstringsanchor1)  
  
-   [<span data-ttu-id="6cb02-108">Cadenas usadas en la invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="6cb02-108">Strings Used in Platform Invoke</span></span>](#cpcondefaultmarshalingforstringsanchor5)  
  
-   [<span data-ttu-id="6cb02-109">Cadenas usadas en estructuras</span><span class="sxs-lookup"><span data-stu-id="6cb02-109">Strings Used in Structures</span></span>](#cpcondefaultmarshalingforstringsanchor2)  
  
-   [<span data-ttu-id="6cb02-110">Búferes de cadenas de longitud fija</span><span class="sxs-lookup"><span data-stu-id="6cb02-110">Fixed-Length String Buffers</span></span>](#cpcondefaultmarshalingforstringsanchor3)  
  
<a name="cpcondefaultmarshalingforstringsanchor1"></a>

## <a name="strings-used-in-interfaces"></a><span data-ttu-id="6cb02-111">Cadenas usadas en interfaces</span><span class="sxs-lookup"><span data-stu-id="6cb02-111">Strings Used in Interfaces</span></span>  
 <span data-ttu-id="6cb02-112">En la siguiente tabla se muestran las opciones de cálculo de referencias para el tipo de datos de cadena cuando las referencias se calculan como un argumento de método a código no administrado.</span><span class="sxs-lookup"><span data-stu-id="6cb02-112">The following table shows the marshaling options for the string data type when marshaled as a method argument to unmanaged code.</span></span> <span data-ttu-id="6cb02-113">El atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> proporciona varios valores de enumeración <xref:System.Runtime.InteropServices.UnmanagedType> para calcular referencias de cadenas a interfaces COM.</span><span class="sxs-lookup"><span data-stu-id="6cb02-113">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal strings to COM interfaces.</span></span>  
  
|<span data-ttu-id="6cb02-114">Tipo de enumeración</span><span class="sxs-lookup"><span data-stu-id="6cb02-114">Enumeration type</span></span>|<span data-ttu-id="6cb02-115">Descripción del formato no administrado</span><span class="sxs-lookup"><span data-stu-id="6cb02-115">Description of unmanaged format</span></span>|  
|----------------------|-------------------------------------|  
|<span data-ttu-id="6cb02-116">`UnmanagedType.BStr` (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="6cb02-116">`UnmanagedType.BStr` (default)</span></span>|<span data-ttu-id="6cb02-117">`BSTR` de estilo COM con una longitud fija y caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="6cb02-117">A COM-style `BSTR` with a prefixed length and Unicode characters.</span></span>|  
|`UnmanagedType.LPStr`|<span data-ttu-id="6cb02-118">Puntero a una matriz de caracteres Unicode terminada en NULL.</span><span class="sxs-lookup"><span data-stu-id="6cb02-118">A pointer to a null-terminated array of ANSI characters.</span></span>|  
|`UnmanagedType.LPWStr`|<span data-ttu-id="6cb02-119">Puntero a una matriz de caracteres Unicode terminada en null.</span><span class="sxs-lookup"><span data-stu-id="6cb02-119">A pointer to a null-terminated array of Unicode characters.</span></span>|  
  
 <span data-ttu-id="6cb02-120">Esta tabla se aplica a cadenas.</span><span class="sxs-lookup"><span data-stu-id="6cb02-120">This table applies to strings.</span></span> <span data-ttu-id="6cb02-121">Sin embargo, para <xref:System.Text.StringBuilder>, las únicas opciones permitidas son `UnmanagedType.LPStr` y `UnmanagedType.LPWStr`.</span><span class="sxs-lookup"><span data-stu-id="6cb02-121">However, for <xref:System.Text.StringBuilder>, the only options allowed are `UnmanagedType.LPStr` and `UnmanagedType.LPWStr`.</span></span>  
  
 <span data-ttu-id="6cb02-122">En el ejemplo siguiente se muestran las cadenas declaradas en la interfaz `IStringWorker`.</span><span class="sxs-lookup"><span data-stu-id="6cb02-122">The following example shows strings declared in the `IStringWorker` interface.</span></span>  
  
```cpp  
public interface IStringWorker {  
void PassString1(String s);  
void PassString2([MarshalAs(UnmanagedType.BStr)]String s);  
void PassString3([MarshalAs(UnmanagedType.LPStr)]String s);  
void PassString4([MarshalAs(UnmanagedType.LPWStr)]String s);  
void PassStringRef1(ref String s);  
void PassStringRef2([MarshalAs(UnmanagedType.BStr)]ref String s);  
void PassStringRef3([MarshalAs(UnmanagedType.LPStr)]ref String s);  
void PassStringRef4([MarshalAs(UnmanagedType.LPWStr)]ref String s);  
);
```

<span data-ttu-id="6cb02-123">En el ejemplo siguiente se muestra la interfaz correspondiente descrita en una biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="6cb02-123">The following example shows the corresponding interface described in a type library.</span></span>

```
[…]  
interface IStringWorker : IDispatch {  
HRESULT PassString1([in] BSTR s);  
HRESULT PassString2([in] BSTR s);  
HRESULT PassString3([in] LPStr s);  
HRESULT PassString4([in] LPWStr s);  
HRESULT PassStringRef1([in, out] BSTR *s);  
HRESULT PassStringRef2([in, out] BSTR *s);  
HRESULT PassStringRef3([in, out] LPStr *s);  
HRESULT PassStringRef4([in, out] LPWStr *s);  
);
```

<a name="cpcondefaultmarshalingforstringsanchor5"></a>

## <a name="strings-used-in-platform-invoke"></a><span data-ttu-id="6cb02-124">Cadenas usadas en la plataforma de invocación</span><span class="sxs-lookup"><span data-stu-id="6cb02-124">Strings Used in Platform Invoke</span></span>  
 <span data-ttu-id="6cb02-125">La invocación de plataforma copia los argumentos de cadena y los convierte del formato de .NET Framework (Unicode) al formato no administrado de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="6cb02-125">Platform invoke copies string arguments, converting from the .NET Framework format (Unicode) to the platform unmanaged format.</span></span> <span data-ttu-id="6cb02-126">Las cadenas son inmutables y no se vuelven a copiar desde la memoria no administrada a la memoria administrada cuando finaliza la llamada.</span><span class="sxs-lookup"><span data-stu-id="6cb02-126">Strings are immutable and are not copied back from unmanaged memory to managed memory when the call returns.</span></span>  
  
 <span data-ttu-id="6cb02-127">En la tabla siguiente se enumeran las opciones de cálculo de referencias cuando las referencias de cadenas se calculan como un argumento de método de una llamada de invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="6cb02-127">The following table lists the marshaling options for strings when marshaled as a method argument of a platform invoke call.</span></span> <span data-ttu-id="6cb02-128">El atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> proporciona varios valores de enumeración <xref:System.Runtime.InteropServices.UnmanagedType> para calcular referencias de cadenas.</span><span class="sxs-lookup"><span data-stu-id="6cb02-128">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal strings.</span></span>  
  
|<span data-ttu-id="6cb02-129">Tipo de enumeración</span><span class="sxs-lookup"><span data-stu-id="6cb02-129">Enumeration type</span></span>|<span data-ttu-id="6cb02-130">Descripción de formato no administrado</span><span class="sxs-lookup"><span data-stu-id="6cb02-130">Description of unmanaged format</span></span>|  
|----------------------|-------------------------------------|  
|`UnmanagedType.AnsiBStr`|<span data-ttu-id="6cb02-131">`BSTR` de estilo COM con una longitud fija y caracteres ANSI.</span><span class="sxs-lookup"><span data-stu-id="6cb02-131">A COM-style `BSTR` with a prefixed length and ANSI characters.</span></span>|  
|`UnmanagedType.BStr`|<span data-ttu-id="6cb02-132">`BSTR` de estilo COM con una longitud fija y caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="6cb02-132">A COM-style `BSTR` with a prefixed length and Unicode characters.</span></span>|  
|`UnmanagedType.LPStr`|<span data-ttu-id="6cb02-133">Puntero a una matriz de caracteres Unicode terminada en NULL.</span><span class="sxs-lookup"><span data-stu-id="6cb02-133">A pointer to a null-terminated array of ANSI characters.</span></span>|  
|`UnmanagedType.LPTStr`|<span data-ttu-id="6cb02-134">Un puntero a una matriz terminada en NULL de caracteres dependientes de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="6cb02-134">A pointer to a null-terminated array of platform-dependent characters.</span></span>|  
|`UnmanagedType.LPWStr`|<span data-ttu-id="6cb02-135">Puntero a una matriz de caracteres Unicode terminada en null.</span><span class="sxs-lookup"><span data-stu-id="6cb02-135">A pointer to a null-terminated array of Unicode characters.</span></span>|  
|`UnmanagedType.TBStr`|<span data-ttu-id="6cb02-136">`BSTR` de estilo COM con una longitud fija y caracteres dependientes de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="6cb02-136">A COM-style `BSTR` with a prefixed length and platform-dependent characters.</span></span>|  
|`VBByRefStr`|<span data-ttu-id="6cb02-137">Un valor que permite a Visual Basic .NET cambiar una cadena del código no administrado y reflejar los resultados en el código administrado.</span><span class="sxs-lookup"><span data-stu-id="6cb02-137">A value that enables Visual Basic .NET to change a string in unmanaged code, and have the results reflected in managed code.</span></span> <span data-ttu-id="6cb02-138">Este valor solo se admite con la invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="6cb02-138">This value is supported only for platform invoke.</span></span> <span data-ttu-id="6cb02-139">Este es el valor predeterminado en Visual Basic para las cadenas `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="6cb02-139">This is default value in Visual Basic for `ByVal` strings.</span></span>|  
  
 <span data-ttu-id="6cb02-140">Esta tabla se aplica a cadenas.</span><span class="sxs-lookup"><span data-stu-id="6cb02-140">This table applies to strings.</span></span> <span data-ttu-id="6cb02-141">Sin embargo, para <xref:System.Text.StringBuilder>, las únicas opciones permitidas son `LPStr`, `LPTStr` y `LPWStr`.</span><span class="sxs-lookup"><span data-stu-id="6cb02-141">However, for <xref:System.Text.StringBuilder>, the only options allowed are `LPStr`, `LPTStr`, and `LPWStr`.</span></span>  
  
 <span data-ttu-id="6cb02-142">La siguiente definición de tipo muestra el uso correcto de `MarshalAsAttribute` para llamadas de invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="6cb02-142">The following type definition shows the correct use of `MarshalAsAttribute` for platform invoke calls.</span></span>  
  
```vb  
Class StringLibAPI      
Public Declare Auto Sub PassLPStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.LPStr)> s As String)      
Public Declare Auto Sub PassLPWStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.LPWStr)> s As String)      
Public Declare Auto Sub PassLPTStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.LPTStr)> s As String)      
Public Declare Auto Sub PassBStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.BStr)> s As String)      
Public Declare Auto Sub PassAnsiBStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.AnsiBStr)> s As String)      
Public Declare Auto Sub PassTBStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.TBStr)> s As String)  
End Class  
```

```csharp
class StringLibAPI {  
[DllImport("StringLib.Dll")]  
public static extern void PassLPStr([MarshalAs(UnmanagedType.LPStr)]  
String s);  
[DllImport("StringLib.Dll")]  
public static extern void   
PassLPWStr([MarshalAs(UnmanagedType.LPWStr)]String s);  
[DllImport("StringLib.Dll")]  
public static extern void   
PassLPTStr([MarshalAs(UnmanagedType.LPTStr)]String s);  
[DllImport("StringLib.Dll")]  
public static extern void PassBStr([MarshalAs(UnmanagedType.BStr)]  
String s);  
[DllImport("StringLib.Dll")]  
public static extern void   
PassAnsiBStr([MarshalAs(UnmanagedType.AnsiBStr)]String s);  
[DllImport("StringLib.Dll")]  
public static extern void PassTBStr([MarshalAs(UnmanagedType.TBStr)]  
String s);  
}  
```  
  
<a name="cpcondefaultmarshalingforstringsanchor2"></a>   
## <a name="strings-used-in-structures"></a><span data-ttu-id="6cb02-143">Cadenas usadas en estructuras</span><span class="sxs-lookup"><span data-stu-id="6cb02-143">Strings Used in Structures</span></span>  
 <span data-ttu-id="6cb02-144">Las cadenas son miembros válidos de las estructuras; sin embargo, los búferes <xref:System.Text.StringBuilder> no son válidos en las estructuras.</span><span class="sxs-lookup"><span data-stu-id="6cb02-144">Strings are valid members of structures; however, <xref:System.Text.StringBuilder> buffers are invalid in structures.</span></span> <span data-ttu-id="6cb02-145">En la siguiente tabla se muestran las opciones de cálculo de referencias para el tipo de datos de cadena cuando las referencias del tipo se calculan como un campo.</span><span class="sxs-lookup"><span data-stu-id="6cb02-145">The following table shows the marshaling options for the string data type when the type is marshaled as a field.</span></span> <span data-ttu-id="6cb02-146">El atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> proporciona varios valores de enumeración <xref:System.Runtime.InteropServices.UnmanagedType> para calcular referencias de cadenas a un campo.</span><span class="sxs-lookup"><span data-stu-id="6cb02-146">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal strings to a field.</span></span>  
  
|<span data-ttu-id="6cb02-147">Tipo de enumeración</span><span class="sxs-lookup"><span data-stu-id="6cb02-147">Enumeration type</span></span>|<span data-ttu-id="6cb02-148">Descripción de formato no administrado</span><span class="sxs-lookup"><span data-stu-id="6cb02-148">Description of unmanaged format</span></span>|  
|----------------------|-------------------------------------|  
|`UnmanagedType.BStr`|<span data-ttu-id="6cb02-149">`BSTR` de estilo COM con una longitud fija y caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="6cb02-149">A COM-style `BSTR` with a prefixed length and Unicode characters.</span></span>|  
|`UnmanagedType.LPStr`|<span data-ttu-id="6cb02-150">Puntero a una matriz de caracteres Unicode terminada en NULL.</span><span class="sxs-lookup"><span data-stu-id="6cb02-150">A pointer to a null-terminated array of ANSI characters.</span></span>|  
|`UnmanagedType.LPTStr`|<span data-ttu-id="6cb02-151">Un puntero a una matriz terminada en NULL de caracteres dependientes de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="6cb02-151">A pointer to a null-terminated array of platform-dependent characters.</span></span>|  
|`UnmanagedType.LPWStr`|<span data-ttu-id="6cb02-152">Puntero a una matriz de caracteres Unicode terminada en null.</span><span class="sxs-lookup"><span data-stu-id="6cb02-152">A pointer to a null-terminated array of Unicode characters.</span></span>|  
|`UnmanagedType.ByValTStr`|<span data-ttu-id="6cb02-153">Una matriz de longitud fija de caracteres; el tipo de la matriz se determina por el juego de caracteres de la estructura contenedora.</span><span class="sxs-lookup"><span data-stu-id="6cb02-153">A fixed-length array of characters; the array's type is determined by the character set of the containing structure.</span></span>|  
  
 <span data-ttu-id="6cb02-154">El tipo `ByValTStr` se usa para matrices de caracteres de longitud fija insertadas que aparecen dentro de una estructura.</span><span class="sxs-lookup"><span data-stu-id="6cb02-154">The `ByValTStr` type is used for inline, fixed-length character arrays that appear within a structure.</span></span> <span data-ttu-id="6cb02-155">Otros tipos se aplican a referencias de cadenas incluidas en estructuras que contienen punteros a cadenas.</span><span class="sxs-lookup"><span data-stu-id="6cb02-155">Other types apply to string references contained within structures that contain pointers to strings.</span></span>  
  
 <span data-ttu-id="6cb02-156">El argumento `CharSet` del atributo <xref:System.Runtime.InteropServices.StructLayoutAttribute> que se aplica a la estructura contenedora determina el formato de carácter de las cadenas en las estructuras.</span><span class="sxs-lookup"><span data-stu-id="6cb02-156">The `CharSet` argument of the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute that is applied to the containing structure determines the character format of strings in structures.</span></span> <span data-ttu-id="6cb02-157">Las siguientes estructuras de ejemplo contienen referencias de cadena y cadenas insertadas, así como caracteres ANSI, Unicode y dependientes de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="6cb02-157">The following example structures contain string references and inline strings, as well as ANSI, Unicode, and platform-dependent characters.</span></span>  
  
### <a name="type-library-representation"></a><span data-ttu-id="6cb02-158">Representación de la biblioteca de tipos</span><span class="sxs-lookup"><span data-stu-id="6cb02-158">Type Library Representation</span></span>  
  
```
struct StringInfoA {  
   char *    f1;  
   char      f2[256];  
};  
struct StringInfoW {  
   WCHAR *   f1;  
   WCHAR     f2[256];  
   BSTR      f3;  
};  
struct StringInfoT {  
   TCHAR *   f1;  
   TCHAR     f2[256];  
};  
```  
  
 <span data-ttu-id="6cb02-159">En el ejemplo de código siguiente se muestra cómo usar el atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> para definir la misma estructura en diferentes formatos.</span><span class="sxs-lookup"><span data-stu-id="6cb02-159">The following code example shows how to use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to define the same structure in different formats.</span></span>  
  
```vb  
<StructLayout(LayoutKind.Sequential, CharSet := CharSet.Ansi)> _  
Structure StringInfoA  
<MarshalAs(UnmanagedType.LPStr)> Public f1 As String  
<MarshalAs(UnmanagedType.ByValTStr, SizeConst := 256)> _  
Public f2 As String  
End Structure  
<StructLayout(LayoutKind.Sequential, CharSet := CharSet.Unicode)> _  
Structure StringInfoW  
<MarshalAs(UnmanagedType.LPWStr)> Public f1 As String  
<MarshalAs(UnmanagedType.ByValTStr, SizeConst := 256)> _  
Public f2 As String  
<MarshalAs(UnmanagedType.BStr)> Public f3 As String  
End Structure  
<StructLayout(LayoutKind.Sequential, CharSet := CharSet.Auto)> _  
Structure StringInfoT  
<MarshalAs(UnmanagedType.LPTStr)> Public f1 As String  
<MarshalAs(UnmanagedType.ByValTStr, SizeConst := 256)> _  
Public f2 As String  
End Structure  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential, CharSet=CharSet.Ansi)]  
struct StringInfoA {  
   [MarshalAs(UnmanagedType.LPStr)] public String f1;  
   [MarshalAs(UnmanagedType.ByValTStr, SizeConst=256)] public String f2;  
}  
[StructLayout(LayoutKind.Sequential, CharSet=CharSet.Unicode)]  
struct StringInfoW {  
   [MarshalAs(UnmanagedType.LPWStr)] public String f1;  
   [MarshalAs(UnmanagedType.ByValTStr, SizeConst=256)] public String f2;  
   [MarshalAs(UnmanagedType.BStr)] public String f3;  
}  
[StructLayout(LayoutKind.Sequential, CharSet=CharSet.Auto)]  
struct StringInfoT {  
   [MarshalAs(UnmanagedType.LPTStr)] public String f1;  
   [MarshalAs(UnmanagedType.ByValTStr, SizeConst=256)] public String f2;  
}  
```  
  
<a name="cpcondefaultmarshalingforstringsanchor3"></a>   
## <a name="fixed-length-string-buffers"></a><span data-ttu-id="6cb02-160">Búferes de cadenas de longitud fija</span><span class="sxs-lookup"><span data-stu-id="6cb02-160">Fixed-Length String Buffers</span></span>  
 <span data-ttu-id="6cb02-161">En algunas circunstancias, se debe pasar un búfer de caracteres de longitud fija a código no administrado para su manipulación.</span><span class="sxs-lookup"><span data-stu-id="6cb02-161">In some circumstances, a fixed-length character buffer must be passed into unmanaged code to be manipulated.</span></span> <span data-ttu-id="6cb02-162">En este caso no basta con pasar una cadena porque el destinatario no puede modificar el contenido del búfer que se pasa.</span><span class="sxs-lookup"><span data-stu-id="6cb02-162">Simply passing a string does not work in this case because the callee cannot modify the contents of the passed buffer.</span></span> <span data-ttu-id="6cb02-163">Aunque la cadena se pase por referencia, no hay ninguna manera de inicializar el búfer con un tamaño determinado.</span><span class="sxs-lookup"><span data-stu-id="6cb02-163">Even if the string is passed by reference, there is no way to initialize the buffer to a given size.</span></span>  
  
 <span data-ttu-id="6cb02-164">La solución consiste en pasar un búfer <xref:System.Text.StringBuilder> como argumento en lugar de una cadena.</span><span class="sxs-lookup"><span data-stu-id="6cb02-164">The solution is to pass a <xref:System.Text.StringBuilder> buffer as the argument instead of a string.</span></span> <span data-ttu-id="6cb02-165">El destinatario puede desreferenciar y modificar un `StringBuilder`, siempre que no exceda la capacidad del `StringBuilder`.</span><span class="sxs-lookup"><span data-stu-id="6cb02-165">A `StringBuilder` can be dereferenced and modified by the callee, provided it does not exceed the capacity of the `StringBuilder`.</span></span> <span data-ttu-id="6cb02-166">También puede inicializarse con una longitud fija.</span><span class="sxs-lookup"><span data-stu-id="6cb02-166">It can also be initialized to a fixed length.</span></span> <span data-ttu-id="6cb02-167">Por ejemplo, si inicializa un búfer `StringBuilder` con una capacidad de `N`, el contador de referencias proporcionará un búfer con un tamaño de (`N`+ 1) caracteres.</span><span class="sxs-lookup"><span data-stu-id="6cb02-167">For example, if you initialize a `StringBuilder` buffer to a capacity of `N`, the marshaler provides a buffer of size (`N`+1) characters.</span></span> <span data-ttu-id="6cb02-168">+ 1 tiene en cuenta el hecho de que la cadena no administrada tiene un terminador NULL mientras que `StringBuilder` no.</span><span class="sxs-lookup"><span data-stu-id="6cb02-168">The +1 accounts for the fact that the unmanaged string has a null terminator while `StringBuilder` does not.</span></span>  
  
 <span data-ttu-id="6cb02-169">Por ejemplo, la función `GetWindowText` de la API Win32 de Microsoft (definida en Windows.h) es un búfer de caracteres de longitud fija que debe pasarse a código no administrado para su manipulación.</span><span class="sxs-lookup"><span data-stu-id="6cb02-169">For example, the Microsoft Win32 API `GetWindowText` function (defined in Windows.h) is a fixed-length character buffer that must be passed into unmanaged code to be manipulated.</span></span> <span data-ttu-id="6cb02-170">`LpString` apunta a un búfer asignado por el llamador de tamaño `nMaxCount`.</span><span class="sxs-lookup"><span data-stu-id="6cb02-170">`LpString` points to a caller-allocated buffer of size `nMaxCount`.</span></span> <span data-ttu-id="6cb02-171">Se espera que el llamador asigne el búfer y establezca el argumento `nMaxCount` en el tamaño del búfer asignado.</span><span class="sxs-lookup"><span data-stu-id="6cb02-171">The caller is expected to allocate the buffer and set the `nMaxCount` argument to the size of the allocated buffer.</span></span> <span data-ttu-id="6cb02-172">El siguiente código muestra la declaración de función `GetWindowText`, tal y como se define en Windows.h.</span><span class="sxs-lookup"><span data-stu-id="6cb02-172">The following code shows the `GetWindowText` function declaration as defined in Windows.h.</span></span>  
  
```  
int GetWindowText(  
HWND hWnd,        // Handle to window or control.  
LPTStr lpString,  // Text buffer.  
int nMaxCount     // Maximum number of characters to copy.  
);  
```  
  
 <span data-ttu-id="6cb02-173">El destinatario puede desreferenciar y modificar un `StringBuilder`, siempre que no exceda la capacidad del `StringBuilder`.</span><span class="sxs-lookup"><span data-stu-id="6cb02-173">A `StringBuilder` can be dereferenced and modified by the callee, provided it does not exceed the capacity of the `StringBuilder`.</span></span> <span data-ttu-id="6cb02-174">En el ejemplo de código siguiente se muestra cómo inicializar `StringBuilder` con una longitud fija.</span><span class="sxs-lookup"><span data-stu-id="6cb02-174">The following code example demonstrates how `StringBuilder` can be initialized to a fixed length.</span></span>  
  
```vb  
Public Class Win32API  
Public Declare Auto Sub GetWindowText Lib "User32.Dll" _  
(h As Integer, s As StringBuilder, nMaxCount As Integer)  
End Class  
Public Class Window  
   Friend h As Integer ' Friend handle to Window.  
   Public Function GetText() As String  
      Dim sb As New StringBuilder(256)  
      Win32API.GetWindowText(h, sb, sb.Capacity + 1)  
   Return sb.ToString()  
   End Function  
End Class  
```  
  
```csharp  
public class Win32API {  
[DllImport("User32.Dll")]  
public static extern void GetWindowText(int h, StringBuilder s,   
int nMaxCount);  
}  
public class Window {  
   internal int h;        // Internal handle to Window.  
   public String GetText() {  
      StringBuilder sb = new StringBuilder(256);  
      Win32API.GetWindowText(h, sb, sb.Capacity + 1);  
   return sb.ToString();  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="6cb02-175">Vea también</span><span class="sxs-lookup"><span data-stu-id="6cb02-175">See Also</span></span>  
 [<span data-ttu-id="6cb02-176">Comportamiento predeterminado del cálculo de referencias</span><span class="sxs-lookup"><span data-stu-id="6cb02-176">Default Marshaling Behavior</span></span>](default-marshaling-behavior.md)  
 [<span data-ttu-id="6cb02-177">Tipos que pueden o que no pueden transferirse en bloque de bits</span><span class="sxs-lookup"><span data-stu-id="6cb02-177">Blittable and Non-Blittable Types</span></span>](blittable-and-non-blittable-types.md)  
 <span data-ttu-id="6cb02-178">[Atributos direccionales](https://msdn.microsoft.com/library/241ac5b5-928e-4969-8f58-1dbc048f9ea2(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="6cb02-178">[Directional Attributes](https://msdn.microsoft.com/library/241ac5b5-928e-4969-8f58-1dbc048f9ea2(v=vs.100))</span></span>  
 [<span data-ttu-id="6cb02-179">Copiar y fijar</span><span class="sxs-lookup"><span data-stu-id="6cb02-179">Copying and Pinning</span></span>](copying-and-pinning.md)
