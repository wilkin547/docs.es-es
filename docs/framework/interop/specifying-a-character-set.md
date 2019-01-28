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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45810390ced8584ea7b37908a9e4af8d3da73f34
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549855"
---
# <a name="specifying-a-character-set"></a><span data-ttu-id="e5211-102">Especificar un juego de caracteres</span><span class="sxs-lookup"><span data-stu-id="e5211-102">Specifying a Character Set</span></span>
<span data-ttu-id="e5211-103">El campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> controla la serialización de cadenas y determina cómo la invocación de plataforma busca nombres de función en un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="e5211-103">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field controls string marshaling and determines how platform invoke finds function names in a DLL.</span></span> <span data-ttu-id="e5211-104">En este tema se describen ambos comportamientos.</span><span class="sxs-lookup"><span data-stu-id="e5211-104">This topic describes both behaviors.</span></span>  
  
 <span data-ttu-id="e5211-105">Algunas API exportan dos versiones de las funciones que toman argumentos de cadena: la versión estrecha (ANSI) y la versión ancha (Unicode).</span><span class="sxs-lookup"><span data-stu-id="e5211-105">Some APIs export two versions of functions that take string arguments: narrow (ANSI) and wide (Unicode).</span></span> <span data-ttu-id="e5211-106">La API Win32, por ejemplo, incluye los siguientes nombres de punto de entrada para la función **MessageBox**:</span><span class="sxs-lookup"><span data-stu-id="e5211-106">The Win32 API, for instance, includes the following entry-point names for the **MessageBox** function:</span></span>  
  
-   <span data-ttu-id="e5211-107">**MessageBoxA**</span><span class="sxs-lookup"><span data-stu-id="e5211-107">**MessageBoxA**</span></span>  
  
     <span data-ttu-id="e5211-108">Proporciona el formato ANSI de caracteres de 1 byte, que se distingue por una "A" anexada al nombre del punto de entrada.</span><span class="sxs-lookup"><span data-stu-id="e5211-108">Provides 1-byte character ANSI formatting, distinguished by an "A" appended to the entry-point name.</span></span> <span data-ttu-id="e5211-109">Las llamadas a **MessageBoxA** siempre serializan las cadenas en formato ANSI, como es habitual en las plataformas Windows 95 y Windows 98.</span><span class="sxs-lookup"><span data-stu-id="e5211-109">Calls to **MessageBoxA** always marshal strings in ANSI format, as is common on Windows 95 and Windows 98 platforms.</span></span>  
  
-   <span data-ttu-id="e5211-110">**MessageBoxW**</span><span class="sxs-lookup"><span data-stu-id="e5211-110">**MessageBoxW**</span></span>  
  
     <span data-ttu-id="e5211-111">Proporciona el formato Unicode de caracteres de 2 bytes, que se distingue por una "W" anexada al nombre del punto de entrada.</span><span class="sxs-lookup"><span data-stu-id="e5211-111">Provides 2-byte character Unicode formatting, distinguished by a "W" appended to the entry-point name.</span></span> <span data-ttu-id="e5211-112">Las llamadas a **MessageBoxW** siempre serializan las cadenas en formato Unicode, como es habitual en las plataformas Windows NT, Windows 2000 y Windows XP.</span><span class="sxs-lookup"><span data-stu-id="e5211-112">Calls to **MessageBoxW** always marshal strings in Unicode format, as is common on Windows NT, Windows 2000, and Windows XP platforms.</span></span>  
  
## <a name="string-marshaling-and-name-matching"></a><span data-ttu-id="e5211-113">Serialización de cadenas y coincidencia de nombres</span><span class="sxs-lookup"><span data-stu-id="e5211-113">String Marshaling and Name Matching</span></span>  
 <span data-ttu-id="e5211-114">El campo **CharSet** acepta los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="e5211-114">The **CharSet** field accepts the following values:</span></span>  
  
 <span data-ttu-id="e5211-115">**CharSet.Ansi** (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="e5211-115">**CharSet.Ansi** (default value)</span></span>  
  
-   <span data-ttu-id="e5211-116">Serialización de cadenas</span><span class="sxs-lookup"><span data-stu-id="e5211-116">String marshaling</span></span>  
  
     <span data-ttu-id="e5211-117">La invocación de plataforma serializa las cadenas del formato administrado (Unicode) al formato ANSI.</span><span class="sxs-lookup"><span data-stu-id="e5211-117">Platform invoke marshals strings from their managed format (Unicode) to ANSI format.</span></span>  
  
-   <span data-ttu-id="e5211-118">Coincidencia de nombres</span><span class="sxs-lookup"><span data-stu-id="e5211-118">Name matching</span></span>  
  
     <span data-ttu-id="e5211-119">Cuando el campo <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType> es **true**, como sucede de forma predeterminada en [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], la invocación de plataforma solo busca el nombre que especifique.</span><span class="sxs-lookup"><span data-stu-id="e5211-119">When the <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType> field is **true**, as it is by default in [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], platform invoke searches only for the name you specify.</span></span> <span data-ttu-id="e5211-120">Por ejemplo, si especifica **MessageBox**, la invocación de plataforma busca **MessageBox** y se produce un error si no encuentra el término exacto.</span><span class="sxs-lookup"><span data-stu-id="e5211-120">For example, if you specify **MessageBox**, platform invoke searches for **MessageBox** and fails when it cannot locate the exact spelling.</span></span>  
  
     <span data-ttu-id="e5211-121">Si el campo **ExactSpelling** es **false**, como sucede de forma predeterminada en C++ y C#, la invocación de plataforma busca primero el alias no alterado (**MessageBox**) y, luego, el nombre alterado (**MessageBoxA**) en el caso de que no se encuentre el alias no alterado.</span><span class="sxs-lookup"><span data-stu-id="e5211-121">When the **ExactSpelling** field is **false**, as it is by default in C++ and C#, platform invoke searches for the unmangled alias first (**MessageBox**), then the mangled name (**MessageBoxA**) if the unmangled alias is not found.</span></span> <span data-ttu-id="e5211-122">Tenga en cuenta que el comportamiento de la coincidencia de nombres en formato ANSI difiere del comportamiento de la coincidencia de nombres en formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="e5211-122">Notice that ANSI name-matching behavior differs from Unicode name-matching behavior.</span></span>  
  
 <span data-ttu-id="e5211-123">**CharSet.Unicode**</span><span class="sxs-lookup"><span data-stu-id="e5211-123">**CharSet.Unicode**</span></span>  
  
-   <span data-ttu-id="e5211-124">Serialización de cadenas</span><span class="sxs-lookup"><span data-stu-id="e5211-124">String marshaling</span></span>  
  
     <span data-ttu-id="e5211-125">La invocación de plataforma copia las cadenas del formato administrado (Unicode) al formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="e5211-125">Platform invoke copies strings from their managed format (Unicode) to Unicode format.</span></span>  
  
-   <span data-ttu-id="e5211-126">Coincidencia de nombres</span><span class="sxs-lookup"><span data-stu-id="e5211-126">Name matching</span></span>  
  
     <span data-ttu-id="e5211-127">Cuando el campo **ExactSpelling** es **true**, como sucede de forma predeterminada en [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], la invocación de plataforma solo busca el nombre que especifique.</span><span class="sxs-lookup"><span data-stu-id="e5211-127">When the **ExactSpelling** field is **true**, as it is by default in [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], platform invoke searches only for the name you specify.</span></span> <span data-ttu-id="e5211-128">Por ejemplo, si especifica **MessageBox**, la invocación de plataforma busca **MessageBox** y se produce un error si no encuentra el término exacto.</span><span class="sxs-lookup"><span data-stu-id="e5211-128">For example, if you specify **MessageBox**, platform invoke searches for **MessageBox** and fails if it cannot locate the exact spelling.</span></span>  
  
     <span data-ttu-id="e5211-129">Si el campo **ExactSpelling** es **false**, como sucede de forma predeterminada en C++ y C#, la invocación de plataforma busca primero el alias alterado (**MessageBoxW**) y, luego, el nombre no alterado (**MessageBox**) en el caso de que no se encuentre el alias alterado.</span><span class="sxs-lookup"><span data-stu-id="e5211-129">When the **ExactSpelling** field is **false**, as it is by default in C++ and C#, platform invoke searches for the mangled name first (**MessageBoxW**), then the unmangled alias (**MessageBox**) if the mangled name is not found.</span></span> <span data-ttu-id="e5211-130">Tenga en cuenta que el comportamiento de la coincidencia de nombres en formato Unicode difiere del comportamiento de la coincidencia de nombres en formato ANSI.</span><span class="sxs-lookup"><span data-stu-id="e5211-130">Notice that Unicode name-matching behavior differs from ANSI name-matching behavior.</span></span>  
  
 <span data-ttu-id="e5211-131">**CharSet.Auto**</span><span class="sxs-lookup"><span data-stu-id="e5211-131">**CharSet.Auto**</span></span>  
  
-   <span data-ttu-id="e5211-132">La invocación de plataforma elige entre los formatos ANSI y Unicode en tiempo de ejecución en función de la plataforma de destino.</span><span class="sxs-lookup"><span data-stu-id="e5211-132">Platform invoke chooses between ANSI and Unicode formats at run time, based on the target platform.</span></span>  
  
## <a name="specifying-a-character-set-in-visual-basic"></a><span data-ttu-id="e5211-133">Especificar un juego de caracteres en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e5211-133">Specifying a Character Set in Visual Basic</span></span>  
 <span data-ttu-id="e5211-134">En el ejemplo siguiente se declara la función **MessageBox** tres veces, cada una de ellas con un comportamiento de juego de caracteres diferente.</span><span class="sxs-lookup"><span data-stu-id="e5211-134">The following example declares the **MessageBox** function three times, each time with different character-set behavior.</span></span> <span data-ttu-id="e5211-135">Para especificar un comportamiento de juego de caracteres en Visual Basic, agregue la palabra clave **Ansi**, **Unicode** o **Auto** a la instrucción de declaración.</span><span class="sxs-lookup"><span data-stu-id="e5211-135">You can specify character-set behavior in Visual Basic by adding the **Ansi**, **Unicode**, or **Auto** keyword to the declaration statement.</span></span>  
  
 <span data-ttu-id="e5211-136">Si omite la palabra clave del juego de caracteres, tal y como se hace en la primera instrucción de la declaración, el campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> establece como valor predeterminado el juego de caracteres ANSI.</span><span class="sxs-lookup"><span data-stu-id="e5211-136">If you omit the character-set keyword, as is done in the first declaration statement, the <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field defaults to the ANSI character set.</span></span> <span data-ttu-id="e5211-137">En la segunda y tercera instrucciones del ejemplo se especifica explícitamente un juego de caracteres con una palabra clave.</span><span class="sxs-lookup"><span data-stu-id="e5211-137">The second and third statements in the example explicitly specify a character set with a keyword.</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
  
Public Class Win32  
   Declare Function MessageBoxA Lib "user32.dll"(ByVal hWnd As Integer, _  
       ByVal txt As String, ByVal caption As String, _  
       ByVal Typ As Integer) As Integer  
  
   Declare Unicode Function MessageBoxW Lib "user32.dll" _  
       (ByVal hWnd As Integer, ByVal txt As String, _  
        ByVal caption As String, ByVal Typ As Integer) As Integer  
  
   Declare Auto Function MessageBox Lib "user32.dll" _  
       (ByVal hWnd As Integer, ByVal txt As String, _  
        ByVal caption As String, ByVal Typ As Integer) As Integer  
End Class  
```  
  
## <a name="specifying-a-character-set-in-c-and-c"></a><span data-ttu-id="e5211-138">Especificar un juego de caracteres en C# y C++</span><span class="sxs-lookup"><span data-stu-id="e5211-138">Specifying a Character Set in C# and C++</span></span>  
 <span data-ttu-id="e5211-139">El campo <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> identifica el juego de caracteres subyacente como ANSI o Unicode.</span><span class="sxs-lookup"><span data-stu-id="e5211-139">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field identifies the underlying character set as ANSI or Unicode.</span></span> <span data-ttu-id="e5211-140">El juego de caracteres controla cómo se deben serializar los argumentos de cadena en un método.</span><span class="sxs-lookup"><span data-stu-id="e5211-140">The character set controls how string arguments to a method should be marshaled.</span></span> <span data-ttu-id="e5211-141">Use uno de los formatos siguientes para indicar el juego de caracteres:</span><span class="sxs-lookup"><span data-stu-id="e5211-141">Use one of the following forms to indicate the character set:</span></span>  
  
```csharp  
[DllImport("dllname", CharSet=CharSet.Ansi)]  
[DllImport("dllname", CharSet=CharSet.Unicode)]  
[DllImport("dllname", CharSet=CharSet.Auto)]  
```  
  
```cpp  
[DllImport("dllname", CharSet=CharSet::Ansi)]  
[DllImport("dllname", CharSet=CharSet::Unicode)]  
[DllImport("dllname", CharSet=CharSet::Auto)]  
```  
  
 <span data-ttu-id="e5211-142">En el ejemplo siguiente se muestran tres definiciones administradas de la función **MessageBox** con atributos para especificar un juego de caracteres.</span><span class="sxs-lookup"><span data-stu-id="e5211-142">The following example shows three managed definitions of the **MessageBox** function attributed to specify a character set.</span></span> <span data-ttu-id="e5211-143">En la primera definición, debido a su omisión, el campo **CharSet** establece como valor predeterminado el juego de caracteres ANSI.</span><span class="sxs-lookup"><span data-stu-id="e5211-143">In the first definition, by its omission, the **CharSet** field defaults to the ANSI character set.</span></span>  
  
```csharp  
[DllImport("user32.dll")]  
    public static extern int MessageBoxA(int hWnd, String text,   
        String caption, uint type);  
[DllImport("user32.dll", CharSet=CharSet.Unicode)]  
    public static extern int MessageBoxW(int hWnd, String text,   
        String caption, uint type);  
[DllImport("user32.dll", CharSet=CharSet.Auto)]  
    public static extern int MessageBox(int hWnd, String text,   
        String caption, uint type);  
```  
  
```cpp  
typedef void* HWND;  
  
//Can use MessageBox or MessageBoxA.  
[DllImport("user32")]  
extern "C" int MessageBox(HWND hWnd,  
                          String* pText,  
                          String* pCaption,  
                          unsigned int uType);  
  
//Can use MessageBox or MessageBoxW.  
[DllImport("user32", CharSet=CharSet::Unicode)]  
extern "C" int MessageBoxW(HWND hWnd,  
                          String* pText,  
                          String* pCaption,  
                          unsigned int uType);  
  
//Must use MessageBox.  
[DllImport("user32", CharSet=CharSet::Auto)]  
extern "C" int MessageBox(HWND hWnd,  
                          String* pText,  
                          String* pCaption,  
                          unsigned int uType);  
```  
  
## <a name="see-also"></a><span data-ttu-id="e5211-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5211-144">See also</span></span>
- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [<span data-ttu-id="e5211-145">Crear prototipos en código administrado</span><span class="sxs-lookup"><span data-stu-id="e5211-145">Creating Prototypes in Managed Code</span></span>](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="e5211-146">Ejemplos de invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="e5211-146">Platform Invoke Examples</span></span>](../../../docs/framework/interop/platform-invoke-examples.md)
- [<span data-ttu-id="e5211-147">Serialización de datos con invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="e5211-147">Marshaling Data with Platform Invoke</span></span>](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)
