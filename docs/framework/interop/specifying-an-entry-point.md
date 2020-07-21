---
title: Especificar un punto de entrada
description: Aprenda a especificar un punto de entrada, que identifica la ubicación de una función en un archivo DLL. Puede cambiar el nombre de la función si asigna el punto de entrada a otro nombre.
ms.date: 03/30/2017
helpviewer_keywords:
- EntryPoint field
- platform invoke, attribute fields
- attribute fields in platform invoke, EntryPoint
ms.assetid: d1247f08-0965-416a-b978-e0b50652dfe3
ms.openlocfilehash: 5628c54103410d127c2f9c4f56e1c6f897ada754
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/13/2020
ms.locfileid: "86282026"
---
# <a name="specifying-an-entry-point"></a><span data-ttu-id="b0c06-104">Especificar un punto de entrada</span><span class="sxs-lookup"><span data-stu-id="b0c06-104">Specifying an Entry Point</span></span>

<span data-ttu-id="b0c06-105">Un punto de entrada identifica la ubicación de una función en un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="b0c06-105">An entry point identifies the location of a function in a DLL.</span></span> <span data-ttu-id="b0c06-106">En un proyecto administrado, el nombre original o el punto de entrada ordinal de una función de destino identifica dicha función dentro de los límites de la interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="b0c06-106">Within a managed project, the original name or ordinal entry point of a target function identifies that function across the interoperation boundary.</span></span> <span data-ttu-id="b0c06-107">Además, puede asignarle otro nombre al punto de entrada, lo que supone en realidad un cambio de nombre de la función.</span><span class="sxs-lookup"><span data-stu-id="b0c06-107">Further, you can map the entry point to a different name, effectively renaming the function.</span></span>  
  
 <span data-ttu-id="b0c06-108">En la lista siguiente se muestran los motivos posible para cambiar el nombre de una función DLL:</span><span class="sxs-lookup"><span data-stu-id="b0c06-108">The following is a list of possible reasons to rename a DLL function:</span></span>  
  
- <span data-ttu-id="b0c06-109">Para no utilizar nombres de función de la API que distinguen mayúsculas de minúsculas</span><span class="sxs-lookup"><span data-stu-id="b0c06-109">To avoid using case-sensitive API function names</span></span>  
  
- <span data-ttu-id="b0c06-110">Para cumplir los estándares de nomenclatura existentes</span><span class="sxs-lookup"><span data-stu-id="b0c06-110">To comply with existing naming standards</span></span>  
  
- <span data-ttu-id="b0c06-111">Para incluir funciones que toman tipos de datos distintos (declarando varias versiones de la misma función de un archivo DLL)</span><span class="sxs-lookup"><span data-stu-id="b0c06-111">To accommodate functions that take different data types (by declaring multiple versions of the same DLL function)</span></span>  
  
- <span data-ttu-id="b0c06-112">Para simplificar el uso de las API que contienen versiones ANSI y Unicode</span><span class="sxs-lookup"><span data-stu-id="b0c06-112">To simplify using APIs that contain ANSI and Unicode versions</span></span>  
  
 <span data-ttu-id="b0c06-113">En este tema se muestra la forma de cambiar el nombre de una función de un archivo DLL en código administrado.</span><span class="sxs-lookup"><span data-stu-id="b0c06-113">This topic demonstrates how to rename a DLL function in managed code.</span></span>  
  
## <a name="renaming-a-function-in-visual-basic"></a><span data-ttu-id="b0c06-114">Cambiar el nombre de una función en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b0c06-114">Renaming a Function in Visual Basic</span></span>  

<span data-ttu-id="b0c06-115">Visual Basic usa la palabra clave **Function** en la instrucción **Declare** para establecer el campo <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b0c06-115">Visual Basic uses the **Function** keyword in the **Declare** statement to set the <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> field.</span></span> <span data-ttu-id="b0c06-116">En el siguiente ejemplo muestra una declaración básica.</span><span class="sxs-lookup"><span data-stu-id="b0c06-116">The following example shows a basic declaration.</span></span>  
  
```vb
Friend Class NativeMethods
    Friend Declare Auto Function MessageBox Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
End Class
```
  
<span data-ttu-id="b0c06-117">Es posible reemplazar el punto de entrada **MessageBox** por **MsgBox** incluyendo la palabra clave **Alias** en la definición, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="b0c06-117">You can replace the **MessageBox** entry point with **MsgBox** by including the **Alias** keyword in your definition, as shown in the following example.</span></span> <span data-ttu-id="b0c06-118">En los dos ejemplos, la palabra clave **Auto** elimina la necesidad de especificar la versión del juego de caracteres del punto de entrada.</span><span class="sxs-lookup"><span data-stu-id="b0c06-118">In both examples the **Auto** keyword eliminates the need to specify the character-set version of the entry point.</span></span> <span data-ttu-id="b0c06-119">Para obtener más información sobre cómo seleccionar un juego de caracteres, vea [Specifying a Character Set](specifying-a-character-set.md) (Especificar un juego de caracteres).</span><span class="sxs-lookup"><span data-stu-id="b0c06-119">For more information about selecting a character set, see [Specifying a Character Set](specifying-a-character-set.md).</span></span>  
  
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
  
## <a name="renaming-a-function-in-c-and-c"></a><span data-ttu-id="b0c06-120">Cambiar el nombre de una función en C# y C++</span><span class="sxs-lookup"><span data-stu-id="b0c06-120">Renaming a Function in C# and C++</span></span>  
 <span data-ttu-id="b0c06-121">Puede utilizar el campo <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> para especificar una función DLL por nombre u ordinal.</span><span class="sxs-lookup"><span data-stu-id="b0c06-121">You can use the <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> field to specify a DLL function by name or ordinal.</span></span> <span data-ttu-id="b0c06-122">Si el nombre de la función en la definición del método es el mismo que el punto de entrada en el archivo DLL, no es necesario identificar la función de forma explícita con el campo **EntryPoint**.</span><span class="sxs-lookup"><span data-stu-id="b0c06-122">If the name of the function in your method definition is the same as the entry point in the DLL, you do not have to explicitly identify the function with the **EntryPoint** field.</span></span> <span data-ttu-id="b0c06-123">En caso contrario, utilice una de las siguientes formas de atributo para indicar un nombre u ordinal:</span><span class="sxs-lookup"><span data-stu-id="b0c06-123">Otherwise, use one of the following attribute forms to indicate a name or ordinal:</span></span>  
  
```csharp
[DllImport("DllName", EntryPoint = "Functionname")]
[DllImport("DllName", EntryPoint = "#123")]
```
  
 <span data-ttu-id="b0c06-124">Tenga en cuenta que los ordinales deben ir precedidos del símbolo de libra esterlina (#).</span><span class="sxs-lookup"><span data-stu-id="b0c06-124">Notice that you must prefix an ordinal with the pound sign (#).</span></span>  
  
 <span data-ttu-id="b0c06-125">En el siguiente ejemplo se muestra cómo reemplazar **MessageBoxA** por **MsgBox** en el código usando el campo **EntryPoint**.</span><span class="sxs-lookup"><span data-stu-id="b0c06-125">The following example demonstrates how to replace **MessageBoxA** with **MsgBox** in your code by using the **EntryPoint** field.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b0c06-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0c06-126">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [<span data-ttu-id="b0c06-127">Crear prototipos en código administrado</span><span class="sxs-lookup"><span data-stu-id="b0c06-127">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="b0c06-128">Ejemplos de invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="b0c06-128">Platform Invoke Examples</span></span>](platform-invoke-examples.md)
- [<span data-ttu-id="b0c06-129">Serialización de datos con invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="b0c06-129">Marshaling Data with Platform Invoke</span></span>](marshaling-data-with-platform-invoke.md)
