---
title: Cálculo de referencias predeterminado para cadenas
ms.date: 03/20/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings, interop marshaling
- interop marshaling, strings
ms.assetid: 9baea3ce-27b3-4b4f-af98-9ad0f9467e6f
ms.openlocfilehash: 49f2d871a42db484e20f0bfc35634a0e8b959c2e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123545"
---
# <a name="default-marshaling-for-strings"></a><span data-ttu-id="aa62e-102">Cálculo de referencias predeterminado para cadenas</span><span class="sxs-lookup"><span data-stu-id="aa62e-102">Default Marshaling for Strings</span></span>

<span data-ttu-id="aa62e-103">Las clases <xref:System.String?displayProperty=nameWithType> y <xref:System.Text.StringBuilder?displayProperty=nameWithType> tienen un comportamiento de serialización similar.</span><span class="sxs-lookup"><span data-stu-id="aa62e-103">Both the <xref:System.String?displayProperty=nameWithType> and <xref:System.Text.StringBuilder?displayProperty=nameWithType> classes have similar marshaling behavior.</span></span>

<span data-ttu-id="aa62e-104">Las referencias de las cadenas se calculan como un tipo `BSTR` de estilo COM o como una cadena terminada en NULL (una matriz de caracteres que termina con un carácter NULL).</span><span class="sxs-lookup"><span data-stu-id="aa62e-104">Strings are marshaled as a COM-style `BSTR` type or as a null-terminated string (a character array that ends with a null character).</span></span> <span data-ttu-id="aa62e-105">Las referencias de los caracteres dentro de la cadena se pueden calcular como ANSI o Unicode (el valor predeterminado en los sistemas Windows).</span><span class="sxs-lookup"><span data-stu-id="aa62e-105">The characters within the string can be marshaled as Unicode (the default on Windows systems) or ANSI.</span></span>

## <a name="strings-used-in-interfaces"></a><span data-ttu-id="aa62e-106">Cadenas usadas en interfaces</span><span class="sxs-lookup"><span data-stu-id="aa62e-106">Strings Used in Interfaces</span></span>

<span data-ttu-id="aa62e-107">En la siguiente tabla se muestran las opciones de cálculo de referencias para el tipo de datos de cadena cuando las referencias se calculan como un argumento de método a código no administrado.</span><span class="sxs-lookup"><span data-stu-id="aa62e-107">The following table shows the marshaling options for the string data type when marshaled as a method argument to unmanaged code.</span></span> <span data-ttu-id="aa62e-108">El atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> proporciona varios valores de enumeración <xref:System.Runtime.InteropServices.UnmanagedType> para calcular referencias de cadenas a interfaces COM.</span><span class="sxs-lookup"><span data-stu-id="aa62e-108">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal strings to COM interfaces.</span></span>

|<span data-ttu-id="aa62e-109">Tipo de enumeración</span><span class="sxs-lookup"><span data-stu-id="aa62e-109">Enumeration type</span></span>|<span data-ttu-id="aa62e-110">Descripción de formato no administrado</span><span class="sxs-lookup"><span data-stu-id="aa62e-110">Description of unmanaged format</span></span>|
|----------------------|-------------------------------------|
|<span data-ttu-id="aa62e-111">`UnmanagedType.BStr` (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="aa62e-111">`UnmanagedType.BStr` (default)</span></span>|<span data-ttu-id="aa62e-112">`BSTR` de estilo COM con una longitud fija y caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="aa62e-112">A COM-style `BSTR` with a prefixed length and Unicode characters.</span></span>|
|`UnmanagedType.LPStr`|<span data-ttu-id="aa62e-113">Puntero a una matriz de caracteres Unicode terminada en NULL.</span><span class="sxs-lookup"><span data-stu-id="aa62e-113">A pointer to a null-terminated array of ANSI characters.</span></span>|
|`UnmanagedType.LPWStr`|<span data-ttu-id="aa62e-114">Puntero a una matriz de caracteres Unicode terminada en null.</span><span class="sxs-lookup"><span data-stu-id="aa62e-114">A pointer to a null-terminated array of Unicode characters.</span></span>|

<span data-ttu-id="aa62e-115">Esta tabla se aplica a <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="aa62e-115">This table applies to <xref:System.String>.</span></span> <span data-ttu-id="aa62e-116">Para <xref:System.Text.StringBuilder>, las únicas opciones permitidas son `UnmanagedType.LPStr` y `UnmanagedType.LPWStr`.</span><span class="sxs-lookup"><span data-stu-id="aa62e-116">For <xref:System.Text.StringBuilder>, the only options allowed are `UnmanagedType.LPStr` and `UnmanagedType.LPWStr`.</span></span>

<span data-ttu-id="aa62e-117">En el ejemplo siguiente se muestran las cadenas declaradas en la interfaz `IStringWorker`.</span><span class="sxs-lookup"><span data-stu-id="aa62e-117">The following example shows strings declared in the `IStringWorker` interface.</span></span>

```csharp
public interface IStringWorker
{
    void PassString1(string s);
    void PassString2([MarshalAs(UnmanagedType.BStr)] string s);
    void PassString3([MarshalAs(UnmanagedType.LPStr)] string s);
    void PassString4([MarshalAs(UnmanagedType.LPWStr)] string s);
    void PassStringRef1(ref string s);
    void PassStringRef2([MarshalAs(UnmanagedType.BStr)] ref string s);
    void PassStringRef3([MarshalAs(UnmanagedType.LPStr)] ref string s);
    void PassStringRef4([MarshalAs(UnmanagedType.LPWStr)] ref string s);
}
```

```vb
Public Interface IStringWorker
    Sub PassString1(s As String)
    Sub PassString2(<MarshalAs(UnmanagedType.BStr)> s As String)
    Sub PassString3(<MarshalAs(UnmanagedType.LPStr)> s As String)
    Sub PassString4(<MarshalAs(UnmanagedType.LPWStr)> s As String)
    Sub PassStringRef1(ByRef s As String)
    Sub PassStringRef2(<MarshalAs(UnmanagedType.BStr)> ByRef s As String)
    Sub PassStringRef3(<MarshalAs(UnmanagedType.LPStr)> ByRef s As String)
    Sub PassStringRef4(<MarshalAs(UnmanagedType.LPWStr)> ByRef s As String)
End Interface
```

<span data-ttu-id="aa62e-118">En el ejemplo siguiente se muestra la interfaz correspondiente descrita en una biblioteca de tipos.</span><span class="sxs-lookup"><span data-stu-id="aa62e-118">The following example shows the corresponding interface described in a type library.</span></span>

```cpp
interface IStringWorker : IDispatch
{
    HRESULT PassString1([in] BSTR s);
    HRESULT PassString2([in] BSTR s);
    HRESULT PassString3([in] LPStr s);
    HRESULT PassString4([in] LPWStr s);
    HRESULT PassStringRef1([in, out] BSTR *s);
    HRESULT PassStringRef2([in, out] BSTR *s);
    HRESULT PassStringRef3([in, out] LPStr *s);
    HRESULT PassStringRef4([in, out] LPWStr *s);
};
```

## <a name="strings-used-in-platform-invoke"></a><span data-ttu-id="aa62e-119">Cadenas usadas en la plataforma de invocación</span><span class="sxs-lookup"><span data-stu-id="aa62e-119">Strings Used in Platform Invoke</span></span>

<span data-ttu-id="aa62e-120">La invocación de plataforma copia los argumentos de cadena y los convierte del formato de .NET Framework (Unicode) al formato no administrado de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="aa62e-120">Platform invoke copies string arguments, converting from the .NET Framework format (Unicode) to the platform unmanaged format.</span></span> <span data-ttu-id="aa62e-121">Las cadenas son inmutables y no se vuelven a copiar desde la memoria no administrada a la memoria administrada cuando finaliza la llamada.</span><span class="sxs-lookup"><span data-stu-id="aa62e-121">Strings are immutable and are not copied back from unmanaged memory to managed memory when the call returns.</span></span>

<span data-ttu-id="aa62e-122">En la tabla siguiente se enumeran las opciones de cálculo de referencias cuando las referencias de cadenas se calculan como un argumento de método de una llamada de invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="aa62e-122">The following table lists the marshaling options for strings when marshaled as a method argument of a platform invoke call.</span></span> <span data-ttu-id="aa62e-123">El atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> proporciona varios valores de enumeración <xref:System.Runtime.InteropServices.UnmanagedType> para calcular referencias de cadenas.</span><span class="sxs-lookup"><span data-stu-id="aa62e-123">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal strings.</span></span>

|<span data-ttu-id="aa62e-124">Tipo de enumeración</span><span class="sxs-lookup"><span data-stu-id="aa62e-124">Enumeration type</span></span>|<span data-ttu-id="aa62e-125">Descripción de formato no administrado</span><span class="sxs-lookup"><span data-stu-id="aa62e-125">Description of unmanaged format</span></span>|
|----------------------|-------------------------------------|
|`UnmanagedType.AnsiBStr`|<span data-ttu-id="aa62e-126">`BSTR` de estilo COM con una longitud fija y caracteres ANSI.</span><span class="sxs-lookup"><span data-stu-id="aa62e-126">A COM-style `BSTR` with a prefixed length and ANSI characters.</span></span>|
|`UnmanagedType.BStr`|<span data-ttu-id="aa62e-127">`BSTR` de estilo COM con una longitud fija y caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="aa62e-127">A COM-style `BSTR` with a prefixed length and Unicode characters.</span></span>|
|<span data-ttu-id="aa62e-128">`UnmanagedType.LPStr` (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="aa62e-128">`UnmanagedType.LPStr` (default)</span></span>|<span data-ttu-id="aa62e-129">Puntero a una matriz de caracteres Unicode terminada en NULL.</span><span class="sxs-lookup"><span data-stu-id="aa62e-129">A pointer to a null-terminated array of ANSI characters.</span></span>|
|`UnmanagedType.LPTStr`|<span data-ttu-id="aa62e-130">Un puntero a una matriz terminada en NULL de caracteres dependientes de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="aa62e-130">A pointer to a null-terminated array of platform-dependent characters.</span></span>|
|`UnmanagedType.LPUTF8Str`|<span data-ttu-id="aa62e-131">Un puntero a una matriz terminada en NULL de caracteres codificados UTF-8.</span><span class="sxs-lookup"><span data-stu-id="aa62e-131">A pointer to a null-terminated array of UTF-8 encoded characters.</span></span>|
|`UnmanagedType.LPWStr`|<span data-ttu-id="aa62e-132">Puntero a una matriz de caracteres Unicode terminada en null.</span><span class="sxs-lookup"><span data-stu-id="aa62e-132">A pointer to a null-terminated array of Unicode characters.</span></span>|
|`UnmanagedType.TBStr`|<span data-ttu-id="aa62e-133">`BSTR` de estilo COM con una longitud fija y caracteres dependientes de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="aa62e-133">A COM-style `BSTR` with a prefixed length and platform-dependent characters.</span></span>|
|`VBByRefStr`|<span data-ttu-id="aa62e-134">Un valor que permite a Visual Basic .NET cambiar una cadena en código no administrado y reflejar los resultados en código administrado.</span><span class="sxs-lookup"><span data-stu-id="aa62e-134">A value that enables Visual Basic .NET to change a string in unmanaged code and have the results reflected in managed code.</span></span> <span data-ttu-id="aa62e-135">Este valor solo se admite con la invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="aa62e-135">This value is supported only for platform invoke.</span></span> <span data-ttu-id="aa62e-136">Se trata del valor predeterminado en Visual Basic para cadenas `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="aa62e-136">This is the default value in Visual Basic for `ByVal` strings.</span></span>|

<span data-ttu-id="aa62e-137">Esta tabla se aplica a <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="aa62e-137">This table applies to <xref:System.String>.</span></span> <span data-ttu-id="aa62e-138">Para <xref:System.Text.StringBuilder>, las únicas opciones permitidas son `LPStr`, `LPTStr` y `LPWStr`.</span><span class="sxs-lookup"><span data-stu-id="aa62e-138">For <xref:System.Text.StringBuilder>, the only options allowed are `LPStr`, `LPTStr`, and `LPWStr`.</span></span>

<span data-ttu-id="aa62e-139">La siguiente definición de tipo muestra el uso correcto de `MarshalAsAttribute` para llamadas de invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="aa62e-139">The following type definition shows the correct use of `MarshalAsAttribute` for platform invoke calls.</span></span>

```csharp
class StringLibAPI
{
    [DllImport("StringLib.dll")]
    public static extern void PassLPStr([MarshalAs(UnmanagedType.LPStr)] string s);
    [DllImport("StringLib.dll")]
    public static extern void PassLPWStr([MarshalAs(UnmanagedType.LPWStr)] string s);
    [DllImport("StringLib.dll")]
    public static extern void PassLPTStr([MarshalAs(UnmanagedType.LPTStr)] string s);
    [DllImport("StringLib.dll")]
    public static extern void PassLPUTF8Str([MarshalAs(UnmanagedType.LPUTF8Str)] string s);
    [DllImport("StringLib.dll")]
    public static extern void PassBStr([MarshalAs(UnmanagedType.BStr)] string s);
    [DllImport("StringLib.dll")]
    public static extern void PassAnsiBStr([MarshalAs(UnmanagedType.AnsiBStr)] string s);
    [DllImport("StringLib.dll")]
    public static extern void PassTBStr([MarshalAs(UnmanagedType.TBStr)] string s);
}
```

```vb
Class StringLibAPI
    Public Declare Auto Sub PassLPStr Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.LPStr)> s As String)
    Public Declare Auto Sub PassLPWStr Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.LPWStr)> s As String)
    Public Declare Auto Sub PassLPTStr Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.LPTStr)> s As String)
    Public Declare Auto Sub PassLPUTF8Str Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.LPUTF8Str)> s As String)
    Public Declare Auto Sub PassBStr Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.BStr)> s As String)
    Public Declare Auto Sub PassAnsiBStr Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.AnsiBStr)> s As String)
    Public Declare Auto Sub PassTBStr Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.TBStr)> s As String)
End Class
```

## <a name="strings-used-in-structures"></a><span data-ttu-id="aa62e-140">Cadenas usadas en estructuras</span><span class="sxs-lookup"><span data-stu-id="aa62e-140">Strings Used in Structures</span></span>

<span data-ttu-id="aa62e-141">Las cadenas son miembros válidos de las estructuras; sin embargo, los búferes <xref:System.Text.StringBuilder> no son válidos en las estructuras.</span><span class="sxs-lookup"><span data-stu-id="aa62e-141">Strings are valid members of structures; however, <xref:System.Text.StringBuilder> buffers are invalid in structures.</span></span> <span data-ttu-id="aa62e-142">En la tabla siguiente se muestran las opciones de serialización para el tipo de datos <xref:System.String> cuando el tipo se serializa como campo.</span><span class="sxs-lookup"><span data-stu-id="aa62e-142">The following table shows the marshaling options for the <xref:System.String> data type when the type is marshaled as a field.</span></span> <span data-ttu-id="aa62e-143">El atributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> proporciona varios valores de enumeración <xref:System.Runtime.InteropServices.UnmanagedType> para calcular referencias de cadenas a un campo.</span><span class="sxs-lookup"><span data-stu-id="aa62e-143">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal strings to a field.</span></span>

|<span data-ttu-id="aa62e-144">Tipo de enumeración</span><span class="sxs-lookup"><span data-stu-id="aa62e-144">Enumeration type</span></span>|<span data-ttu-id="aa62e-145">Descripción de formato no administrado</span><span class="sxs-lookup"><span data-stu-id="aa62e-145">Description of unmanaged format</span></span>|
|----------------------|-------------------------------------|
|`UnmanagedType.BStr`|<span data-ttu-id="aa62e-146">`BSTR` de estilo COM con una longitud fija y caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="aa62e-146">A COM-style `BSTR` with a prefixed length and Unicode characters.</span></span>|
|<span data-ttu-id="aa62e-147">`UnmanagedType.LPStr` (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="aa62e-147">`UnmanagedType.LPStr` (default)</span></span>|<span data-ttu-id="aa62e-148">Puntero a una matriz de caracteres Unicode terminada en NULL.</span><span class="sxs-lookup"><span data-stu-id="aa62e-148">A pointer to a null-terminated array of ANSI characters.</span></span>|
|`UnmanagedType.LPTStr`|<span data-ttu-id="aa62e-149">Un puntero a una matriz terminada en NULL de caracteres dependientes de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="aa62e-149">A pointer to a null-terminated array of platform-dependent characters.</span></span>|
|`UnmanagedType.LPUTF8Str`|<span data-ttu-id="aa62e-150">Un puntero a una matriz terminada en NULL de caracteres codificados UTF-8.</span><span class="sxs-lookup"><span data-stu-id="aa62e-150">A pointer to a null-terminated array of UTF-8 encoded characters.</span></span>|
|`UnmanagedType.LPWStr`|<span data-ttu-id="aa62e-151">Puntero a una matriz de caracteres Unicode terminada en null.</span><span class="sxs-lookup"><span data-stu-id="aa62e-151">A pointer to a null-terminated array of Unicode characters.</span></span>|
|`UnmanagedType.ByValTStr`|<span data-ttu-id="aa62e-152">Una matriz de longitud fija de caracteres; el tipo de la matriz se determina por el juego de caracteres de la estructura contenedora.</span><span class="sxs-lookup"><span data-stu-id="aa62e-152">A fixed-length array of characters; the array's type is determined by the character set of the containing structure.</span></span>|

<span data-ttu-id="aa62e-153">El tipo `ByValTStr` se usa para matrices de caracteres de longitud fija insertadas que aparecen dentro de una estructura.</span><span class="sxs-lookup"><span data-stu-id="aa62e-153">The `ByValTStr` type is used for inline, fixed-length character arrays that appear within a structure.</span></span> <span data-ttu-id="aa62e-154">Otros tipos se aplican a referencias de cadenas incluidas en estructuras que contienen punteros a cadenas.</span><span class="sxs-lookup"><span data-stu-id="aa62e-154">Other types apply to string references contained within structures that contain pointers to strings.</span></span>

<span data-ttu-id="aa62e-155">El argumento `CharSet` del <xref:System.Runtime.InteropServices.StructLayoutAttribute> que se aplica a la estructura contenedora determina el formato de caracteres de las cadenas en las estructuras.</span><span class="sxs-lookup"><span data-stu-id="aa62e-155">The `CharSet` argument of the <xref:System.Runtime.InteropServices.StructLayoutAttribute> that is applied to the containing structure determines the character format of strings in structures.</span></span> <span data-ttu-id="aa62e-156">Las siguientes estructuras de ejemplo contienen referencias de cadena y cadenas insertadas, así como caracteres ANSI, Unicode y dependientes de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="aa62e-156">The following example structures contain string references and inline strings, as well as ANSI, Unicode, and platform-dependent characters.</span></span> <span data-ttu-id="aa62e-157">La representación de estas estructuras en una biblioteca de tipos se muestra en el siguiente código C++:</span><span class="sxs-lookup"><span data-stu-id="aa62e-157">The representation of these structures in a type library is shown in the following C++ code:</span></span>

```cpp
struct StringInfoA
{
    char *  f1;
    char    f2[256];
};

struct StringInfoW
{
    WCHAR * f1;
    WCHAR   f2[256];
    BSTR    f3;
};

struct StringInfoT
{
    TCHAR * f1;
    TCHAR   f2[256];
};
```

<span data-ttu-id="aa62e-158">En el ejemplo siguiente se muestra cómo usar el <xref:System.Runtime.InteropServices.MarshalAsAttribute> para definir la misma estructura en diferentes formatos.</span><span class="sxs-lookup"><span data-stu-id="aa62e-158">The following example shows how to use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> to define the same structure in different formats.</span></span>

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Ansi)]
struct StringInfoA
{
    [MarshalAs(UnmanagedType.LPStr)] public string f1;
    [MarshalAs(UnmanagedType.ByValTStr, SizeConst = 256)] public string f2;
}

[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Unicode)]
struct StringInfoW
{
    [MarshalAs(UnmanagedType.LPWStr)] public string f1;
    [MarshalAs(UnmanagedType.ByValTStr, SizeConst = 256)] public string f2;
    [MarshalAs(UnmanagedType.BStr)] public string f3;
}

[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Auto)]
struct StringInfoT
{
    [MarshalAs(UnmanagedType.LPTStr)] public string f1;
    [MarshalAs(UnmanagedType.ByValTStr, SizeConst = 256)] public string f2;
}
```

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

## <a name="fixed-length-string-buffers"></a><span data-ttu-id="aa62e-159">Búferes de cadenas de longitud fija</span><span class="sxs-lookup"><span data-stu-id="aa62e-159">Fixed-Length String Buffers</span></span>

<span data-ttu-id="aa62e-160">En algunas circunstancias, se debe pasar un búfer de caracteres de longitud fija a código no administrado para su manipulación.</span><span class="sxs-lookup"><span data-stu-id="aa62e-160">In some circumstances, a fixed-length character buffer must be passed into unmanaged code to be manipulated.</span></span> <span data-ttu-id="aa62e-161">En este caso no basta con pasar una cadena porque el destinatario no puede modificar el contenido del búfer que se pasa.</span><span class="sxs-lookup"><span data-stu-id="aa62e-161">Simply passing a string does not work in this case because the callee cannot modify the contents of the passed buffer.</span></span> <span data-ttu-id="aa62e-162">Aunque la cadena se pase por referencia, no hay ninguna manera de inicializar el búfer con un tamaño determinado.</span><span class="sxs-lookup"><span data-stu-id="aa62e-162">Even if the string is passed by reference, there is no way to initialize the buffer to a given size.</span></span>

<span data-ttu-id="aa62e-163">La solución consiste en pasar un búfer <xref:System.Text.StringBuilder> como argumento en lugar de un <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="aa62e-163">The solution is to pass a <xref:System.Text.StringBuilder> buffer as the argument instead of a <xref:System.String>.</span></span> <span data-ttu-id="aa62e-164">El destinatario puede desreferenciar y modificar un `StringBuilder`, siempre que no exceda la capacidad del `StringBuilder`.</span><span class="sxs-lookup"><span data-stu-id="aa62e-164">A `StringBuilder` can be dereferenced and modified by the callee, provided it does not exceed the capacity of the `StringBuilder`.</span></span> <span data-ttu-id="aa62e-165">También puede inicializarse con una longitud fija.</span><span class="sxs-lookup"><span data-stu-id="aa62e-165">It can also be initialized to a fixed length.</span></span> <span data-ttu-id="aa62e-166">Por ejemplo, si inicializa un búfer `StringBuilder` con una capacidad de `N`, el contador de referencias proporcionará un búfer con un tamaño de (`N`+ 1) caracteres.</span><span class="sxs-lookup"><span data-stu-id="aa62e-166">For example, if you initialize a `StringBuilder` buffer to a capacity of `N`, the marshaler provides a buffer of size (`N`+1) characters.</span></span> <span data-ttu-id="aa62e-167">\+ 1 tiene en cuenta el hecho de que la cadena no administrada tiene un terminador NULL mientras que `StringBuilder` no.</span><span class="sxs-lookup"><span data-stu-id="aa62e-167">The +1 accounts for the fact that the unmanaged string has a null terminator while `StringBuilder` does not.</span></span>

<span data-ttu-id="aa62e-168">Por ejemplo, la función de API [`GetWindowText`](/windows/desktop/api/winuser/nf-winuser-getwindowtextw) de Windows (que se define en *winuser.h*) requiere que el autor de llamada pase un búfer de caracteres de longitud fija en el que la función escribe el texto de la ventana.</span><span class="sxs-lookup"><span data-stu-id="aa62e-168">For example, the Windows [`GetWindowText`](/windows/desktop/api/winuser/nf-winuser-getwindowtextw) API function (defined in *winuser.h*) requires that the caller pass a fixed-length character buffer to which the function writes the window's text.</span></span> <span data-ttu-id="aa62e-169">`LpString` apunta a un búfer asignado por el llamador de tamaño `nMaxCount`.</span><span class="sxs-lookup"><span data-stu-id="aa62e-169">`LpString` points to a caller-allocated buffer of size `nMaxCount`.</span></span> <span data-ttu-id="aa62e-170">Se espera que el llamador asigne el búfer y establezca el argumento `nMaxCount` en el tamaño del búfer asignado.</span><span class="sxs-lookup"><span data-stu-id="aa62e-170">The caller is expected to allocate the buffer and set the `nMaxCount` argument to the size of the allocated buffer.</span></span> <span data-ttu-id="aa62e-171">En el ejemplo siguiente se muestra la declaración de la función `GetWindowText`, tal y como se define en *winuser.h*.</span><span class="sxs-lookup"><span data-stu-id="aa62e-171">The following example shows the `GetWindowText` function declaration as defined in *winuser.h*.</span></span>

```cpp
int GetWindowText(
    HWND hWnd,        // Handle to window or control.
    LPTStr lpString,  // Text buffer.
    int nMaxCount     // Maximum number of characters to copy.
);
```

<span data-ttu-id="aa62e-172">El destinatario puede desreferenciar y modificar un `StringBuilder`, siempre que no exceda la capacidad del `StringBuilder`.</span><span class="sxs-lookup"><span data-stu-id="aa62e-172">A `StringBuilder` can be dereferenced and modified by the callee, provided it does not exceed the capacity of the `StringBuilder`.</span></span> <span data-ttu-id="aa62e-173">En el ejemplo de código siguiente se muestra cómo inicializar `StringBuilder` con una longitud fija.</span><span class="sxs-lookup"><span data-stu-id="aa62e-173">The following code example demonstrates how `StringBuilder` can be initialized to a fixed length.</span></span>

```csharp
using System;
using System.Runtime.InteropServices;
using System.Text;

internal static class NativeMethods
{
    [DllImport("User32.dll")]
    internal static extern void GetWindowText(IntPtr hWnd, StringBuilder lpString, int nMaxCount);
}

public class Window
{
    internal IntPtr h;        // Internal handle to Window.
    public String GetText()
    {
        StringBuilder sb = new StringBuilder(256);
        NativeMethods.GetWindowText(h, sb, sb.Capacity + 1);
        return sb.ToString();
    }
}
```

```vb
Imports System.Text

Friend Class NativeMethods
    Friend Declare Auto Sub GetWindowText Lib "User32.dll" _
        (hWnd As IntPtr, lpString As StringBuilder, nMaxCount As Integer)
End Class

Public Class Window
    Friend h As IntPtr ' Friend handle to Window.
    Public Function GetText() As String
        Dim sb As New StringBuilder(256)
        NativeMethods.GetWindowText(h, sb, sb.Capacity + 1)
        Return sb.ToString()
   End Function
End Class
```

## <a name="see-also"></a><span data-ttu-id="aa62e-174">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa62e-174">See also</span></span>

- [<span data-ttu-id="aa62e-175">Comportamiento predeterminado del cálculo de referencias</span><span class="sxs-lookup"><span data-stu-id="aa62e-175">Default Marshaling Behavior</span></span>](default-marshaling-behavior.md)
- [<span data-ttu-id="aa62e-176">Serialización de cadenas</span><span class="sxs-lookup"><span data-stu-id="aa62e-176">Marshaling Strings</span></span>](marshaling-strings.md)
- [<span data-ttu-id="aa62e-177">Tipos que pueden o que no pueden transferirse en bloque de bits</span><span class="sxs-lookup"><span data-stu-id="aa62e-177">Blittable and Non-Blittable Types</span></span>](blittable-and-non-blittable-types.md)
- <span data-ttu-id="aa62e-178">[Atributos direccionales](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="aa62e-178">[Directional Attributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span></span>
- [<span data-ttu-id="aa62e-179">Copiar y fijar</span><span class="sxs-lookup"><span data-stu-id="aa62e-179">Copying and Pinning</span></span>](copying-and-pinning.md)
