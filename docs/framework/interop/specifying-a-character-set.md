---
title: Especificar un juego de caracteres
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- platform invoke, attribute fields
- attribute fields in platform invoke, CharSet
- CharSet field
ms.assetid: a8347eb1-295f-46b9-8a78-63331f9ecc50
ms.openlocfilehash: 0db1cd8d75b45f6d718168793c873e5867028269
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125173"
---
# <a name="specifying-a-character-set"></a><span data-ttu-id="236cf-102">Especificar un juego de caracteres</span><span class="sxs-lookup"><span data-stu-id="236cf-102">Specifying a Character Set</span></span>
<span data-ttu-id="236cf-103">El campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> controla la serialización de cadenas y determina cómo la invocación de plataforma busca nombres de función en un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="236cf-103">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field controls string marshaling and determines how platform invoke finds function names in a DLL.</span></span> <span data-ttu-id="236cf-104">En este tema se describen ambos comportamientos.</span><span class="sxs-lookup"><span data-stu-id="236cf-104">This topic describes both behaviors.</span></span>  
  
 <span data-ttu-id="236cf-105">Algunas API exportan dos versiones de las funciones que toman argumentos de cadena: la versión estrecha (ANSI) y la versión ancha (Unicode).</span><span class="sxs-lookup"><span data-stu-id="236cf-105">Some APIs export two versions of functions that take string arguments: narrow (ANSI) and wide (Unicode).</span></span> <span data-ttu-id="236cf-106">La API de Windows, por ejemplo, incluye los siguientes nombres de punto de entrada para la función **MessageBox**:</span><span class="sxs-lookup"><span data-stu-id="236cf-106">The Windows API, for instance, includes the following entry-point names for the **MessageBox** function:</span></span>  
  
- <span data-ttu-id="236cf-107">**MessageBoxA**</span><span class="sxs-lookup"><span data-stu-id="236cf-107">**MessageBoxA**</span></span>  
  
     <span data-ttu-id="236cf-108">Proporciona el formato ANSI de caracteres de 1 byte, que se distingue por una "A" anexada al nombre del punto de entrada.</span><span class="sxs-lookup"><span data-stu-id="236cf-108">Provides 1-byte character ANSI formatting, distinguished by an "A" appended to the entry-point name.</span></span> <span data-ttu-id="236cf-109">Las llamadas a **MessageBoxA** siempre serializan las cadenas en formato ANSI.</span><span class="sxs-lookup"><span data-stu-id="236cf-109">Calls to **MessageBoxA** always marshal strings in ANSI format.</span></span>  
  
- <span data-ttu-id="236cf-110">**MessageBoxW**</span><span class="sxs-lookup"><span data-stu-id="236cf-110">**MessageBoxW**</span></span>  
  
     <span data-ttu-id="236cf-111">Proporciona el formato Unicode de caracteres de 2 bytes, que se distingue por una "W" anexada al nombre del punto de entrada.</span><span class="sxs-lookup"><span data-stu-id="236cf-111">Provides 2-byte character Unicode formatting, distinguished by a "W" appended to the entry-point name.</span></span> <span data-ttu-id="236cf-112">Las llamadas a **MessageBoxW** siempre serializan las cadenas en formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="236cf-112">Calls to **MessageBoxW** always marshal strings in Unicode format.</span></span>  
  
## <a name="string-marshaling-and-name-matching"></a><span data-ttu-id="236cf-113">Serialización de cadenas y coincidencia de nombres</span><span class="sxs-lookup"><span data-stu-id="236cf-113">String Marshaling and Name Matching</span></span>  
 <span data-ttu-id="236cf-114">El campo `CharSet` acepta los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="236cf-114">The `CharSet` field accepts the following values:</span></span>  
  
 <span data-ttu-id="236cf-115"><xref:System.Runtime.InteropServices.CharSet.Ansi> (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="236cf-115"><xref:System.Runtime.InteropServices.CharSet.Ansi> (default value)</span></span>  
  
- <span data-ttu-id="236cf-116">Serialización de cadenas</span><span class="sxs-lookup"><span data-stu-id="236cf-116">String marshaling</span></span>  
  
     <span data-ttu-id="236cf-117">La invocación de plataforma serializa las cadenas del formato administrado (Unicode) al formato ANSI.</span><span class="sxs-lookup"><span data-stu-id="236cf-117">Platform invoke marshals strings from their managed format (Unicode) to ANSI format.</span></span>  
  
- <span data-ttu-id="236cf-118">Coincidencia de nombres</span><span class="sxs-lookup"><span data-stu-id="236cf-118">Name matching</span></span>  
  
     <span data-ttu-id="236cf-119">Cuando el campo <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType> es `true`, como sucede de forma predeterminada en Visual Basic, la invocación de plataforma solo busca el nombre que se especifique.</span><span class="sxs-lookup"><span data-stu-id="236cf-119">When the <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType> field is `true`, as it is by default in Visual Basic, platform invoke searches only for the name you specify.</span></span> <span data-ttu-id="236cf-120">Por ejemplo, si especifica **MessageBox**, la invocación de plataforma busca **MessageBox** y se produce un error si no encuentra el término exacto.</span><span class="sxs-lookup"><span data-stu-id="236cf-120">For example, if you specify **MessageBox**, platform invoke searches for **MessageBox** and fails when it cannot locate the exact spelling.</span></span>  
  
     <span data-ttu-id="236cf-121">Si el campo `ExactSpelling` es `false`, como sucede de forma predeterminada en C++ y C#, la invocación de plataforma busca primero el alias no alterado (**MessageBox**) y, luego, el nombre alterado (**MessageBoxA**) en el caso de que no se encuentre el alias no alterado.</span><span class="sxs-lookup"><span data-stu-id="236cf-121">When the `ExactSpelling` field is `false`, as it is by default in C++ and C#, platform invoke searches for the unmangled alias first (**MessageBox**), then the mangled name (**MessageBoxA**) if the unmangled alias is not found.</span></span> <span data-ttu-id="236cf-122">Tenga en cuenta que el comportamiento de la coincidencia de nombres en formato ANSI difiere del comportamiento de la coincidencia de nombres en formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="236cf-122">Notice that ANSI name-matching behavior differs from Unicode name-matching behavior.</span></span>  
  
 <xref:System.Runtime.InteropServices.CharSet.Unicode>  
  
- <span data-ttu-id="236cf-123">Serialización de cadenas</span><span class="sxs-lookup"><span data-stu-id="236cf-123">String marshaling</span></span>  
  
     <span data-ttu-id="236cf-124">La invocación de plataforma copia las cadenas del formato administrado (Unicode) al formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="236cf-124">Platform invoke copies strings from their managed format (Unicode) to Unicode format.</span></span>  
  
- <span data-ttu-id="236cf-125">Coincidencia de nombres</span><span class="sxs-lookup"><span data-stu-id="236cf-125">Name matching</span></span>  
  
     <span data-ttu-id="236cf-126">Cuando el campo `ExactSpelling` es `true`, como sucede de forma predeterminada en Visual Basic, la invocación de plataforma solo busca el nombre que se especifique.</span><span class="sxs-lookup"><span data-stu-id="236cf-126">When the `ExactSpelling` field is `true`, as it is by default in Visual Basic, platform invoke searches only for the name you specify.</span></span> <span data-ttu-id="236cf-127">Por ejemplo, si especifica **MessageBox**, la invocación de plataforma busca **MessageBox** y se produce un error si no encuentra el término exacto.</span><span class="sxs-lookup"><span data-stu-id="236cf-127">For example, if you specify **MessageBox**, platform invoke searches for **MessageBox** and fails if it cannot locate the exact spelling.</span></span>  
  
     <span data-ttu-id="236cf-128">Si el campo `ExactSpelling` es `false`, como sucede de forma predeterminada en C++ y C#, la invocación de plataforma busca primero el alias alterado (**MessageBoxW**) y, luego, el nombre no alterado (**MessageBox**) en el caso de que no se encuentre el alias alterado.</span><span class="sxs-lookup"><span data-stu-id="236cf-128">When the `ExactSpelling` field is `false`, as it is by default in C++ and C#, platform invoke searches for the mangled name first (**MessageBoxW**), then the unmangled alias (**MessageBox**) if the mangled name is not found.</span></span> <span data-ttu-id="236cf-129">Tenga en cuenta que el comportamiento de la coincidencia de nombres en formato Unicode difiere del comportamiento de la coincidencia de nombres en formato ANSI.</span><span class="sxs-lookup"><span data-stu-id="236cf-129">Notice that Unicode name-matching behavior differs from ANSI name-matching behavior.</span></span>  
  
 <xref:System.Runtime.InteropServices.CharSet.Auto>  
  
- <span data-ttu-id="236cf-130">La invocación de plataforma elige entre los formatos ANSI y Unicode en tiempo de ejecución en función de la plataforma de destino.</span><span class="sxs-lookup"><span data-stu-id="236cf-130">Platform invoke chooses between ANSI and Unicode formats at run time, based on the target platform.</span></span>  
  
## <a name="specifying-a-character-set-in-visual-basic"></a><span data-ttu-id="236cf-131">Especificar un juego de caracteres en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="236cf-131">Specifying a Character Set in Visual Basic</span></span>  
 <span data-ttu-id="236cf-132">En el ejemplo siguiente se declara la función **MessageBox** tres veces, cada una de ellas con un comportamiento de juego de caracteres diferente.</span><span class="sxs-lookup"><span data-stu-id="236cf-132">The following example declares the **MessageBox** function three times, each time with different character-set behavior.</span></span> <span data-ttu-id="236cf-133">Para especificar un comportamiento de juego de caracteres en Visual Basic, agregue la palabra clave **Ansi**, **Unicode** o **Auto** a la instrucción de declaración.</span><span class="sxs-lookup"><span data-stu-id="236cf-133">You can specify character-set behavior in Visual Basic by adding the **Ansi**, **Unicode**, or **Auto** keyword to the declaration statement.</span></span>  
  
 <span data-ttu-id="236cf-134">Si omite la palabra clave del juego de caracteres, tal y como se hace en la primera instrucción de la declaración, el campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> establece como valor predeterminado el juego de caracteres ANSI.</span><span class="sxs-lookup"><span data-stu-id="236cf-134">If you omit the character-set keyword, as is done in the first declaration statement, the <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field defaults to the ANSI character set.</span></span> <span data-ttu-id="236cf-135">En la segunda y tercera instrucciones del ejemplo se especifica explícitamente un juego de caracteres con una palabra clave.</span><span class="sxs-lookup"><span data-stu-id="236cf-135">The second and third statements in the example explicitly specify a character set with a keyword.</span></span>  
  
```vb
Friend Class NativeMethods
    Friend Declare Function MessageBoxA Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer

    Friend Declare Unicode Function MessageBoxW Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer

    Friend Declare Auto Function MessageBox Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
End Class
```
  
## <a name="specifying-a-character-set-in-c-and-c"></a><span data-ttu-id="236cf-136">Especificar un juego de caracteres en C# y C++</span><span class="sxs-lookup"><span data-stu-id="236cf-136">Specifying a Character Set in C# and C++</span></span>  
 <span data-ttu-id="236cf-137">El campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> identifica el juego de caracteres subyacente como ANSI o Unicode.</span><span class="sxs-lookup"><span data-stu-id="236cf-137">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field identifies the underlying character set as ANSI or Unicode.</span></span> <span data-ttu-id="236cf-138">El juego de caracteres controla cómo se deben serializar los argumentos de cadena en un método.</span><span class="sxs-lookup"><span data-stu-id="236cf-138">The character set controls how string arguments to a method should be marshaled.</span></span> <span data-ttu-id="236cf-139">Use uno de los formatos siguientes para indicar el juego de caracteres:</span><span class="sxs-lookup"><span data-stu-id="236cf-139">Use one of the following forms to indicate the character set:</span></span>  
  
```csharp
[DllImport("DllName", CharSet = CharSet.Ansi)]
[DllImport("DllName", CharSet = CharSet.Unicode)]
[DllImport("DllName", CharSet = CharSet.Auto)]
```
  
```cpp
[DllImport("DllName", CharSet = CharSet::Ansi)]
[DllImport("DllName", CharSet = CharSet::Unicode)]
[DllImport("DllName", CharSet = CharSet::Auto)]
```
  
 <span data-ttu-id="236cf-140">En el ejemplo siguiente se muestran tres definiciones administradas de la función **MessageBox** con atributos para especificar un juego de caracteres.</span><span class="sxs-lookup"><span data-stu-id="236cf-140">The following example shows three managed definitions of the **MessageBox** function attributed to specify a character set.</span></span> <span data-ttu-id="236cf-141">En la primera definición, debido a su omisión, el campo `CharSet` establece como valor predeterminado el juego de caracteres ANSI.</span><span class="sxs-lookup"><span data-stu-id="236cf-141">In the first definition, by its omission, the `CharSet` field defaults to the ANSI character set.</span></span>  
  
```csharp  
using System;
using System.Runtime.InteropServices;

internal static class NativeMethods
{
    [DllImport("user32.dll")]
    internal static extern int MessageBoxA(
        IntPtr hWnd, string lpText, string lpCaption, uint uType);

    [DllImport("user32.dll", CharSet = CharSet.Unicode)]
    internal static extern int MessageBoxW(
        IntPtr hWnd, string lpText, string lpCaption, uint uType);

    [DllImport("user32.dll", CharSet = CharSet.Auto)]
    internal static extern int MessageBox(
        IntPtr hWnd, string lpText, string lpCaption, uint uType);
}
```  
  
```cpp
typedef void* HWND;

// Can use MessageBox or MessageBoxA.
[DllImport("user32")]
extern "C" int MessageBox(
    HWND hWnd, String* lpText, String* lpCaption, unsigned int uType);

// Can use MessageBox or MessageBoxW.
[DllImport("user32", CharSet = CharSet::Unicode)]
extern "C" int MessageBoxW(
    HWND hWnd, String* lpText, String* lpCaption, unsigned int uType);

// Must use MessageBox.
[DllImport("user32", CharSet = CharSet::Auto)]
extern "C" int MessageBox(
    HWND hWnd, String* lpText, String* lpCaption, unsigned int uType);
```
  
## <a name="see-also"></a><span data-ttu-id="236cf-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="236cf-142">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [<span data-ttu-id="236cf-143">Crear prototipos en código administrado</span><span class="sxs-lookup"><span data-stu-id="236cf-143">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="236cf-144">Ejemplos de invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="236cf-144">Platform Invoke Examples</span></span>](platform-invoke-examples.md)
- [<span data-ttu-id="236cf-145">Serialización de datos con invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="236cf-145">Marshaling Data with Platform Invoke</span></span>](marshaling-data-with-platform-invoke.md)
