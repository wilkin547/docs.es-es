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
# <a name="specifying-an-entry-point"></a><span data-ttu-id="06635-102">Especificar un punto de entrada</span><span class="sxs-lookup"><span data-stu-id="06635-102">Specifying an Entry Point</span></span>

<span data-ttu-id="06635-103">Un punto de entrada identifica la ubicación de una función en un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="06635-103">An entry point identifies the location of a function in a DLL.</span></span> <span data-ttu-id="06635-104">En un proyecto administrado, el nombre original o el punto de entrada ordinal de una función de destino identifica dicha función dentro de los límites de la interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="06635-104">Within a managed project, the original name or ordinal entry point of a target function identifies that function across the interoperation boundary.</span></span> <span data-ttu-id="06635-105">Además, puede asignarle otro nombre al punto de entrada, lo que supone en realidad un cambio de nombre de la función.</span><span class="sxs-lookup"><span data-stu-id="06635-105">Further, you can map the entry point to a different name, effectively renaming the function.</span></span>  
  
 <span data-ttu-id="06635-106">La siguiente es una lista de posibles razones para cambiar el nombre de una función DLL:</span><span class="sxs-lookup"><span data-stu-id="06635-106">The following is a list of possible reasons to rename a DLL function:</span></span>  
  
- <span data-ttu-id="06635-107">Para no utilizar nombres de función de la API que distinguen mayúsculas de minúsculas</span><span class="sxs-lookup"><span data-stu-id="06635-107">To avoid using case-sensitive API function names</span></span>  
  
- <span data-ttu-id="06635-108">Para cumplir los estándares de nomenclatura existentes</span><span class="sxs-lookup"><span data-stu-id="06635-108">To comply with existing naming standards</span></span>  
  
- <span data-ttu-id="06635-109">Para incluir funciones que toman tipos de datos distintos (declarando varias versiones de la misma función de un archivo DLL)</span><span class="sxs-lookup"><span data-stu-id="06635-109">To accommodate functions that take different data types (by declaring multiple versions of the same DLL function)</span></span>  
  
- <span data-ttu-id="06635-110">Para simplificar el uso de las API que contienen versiones ANSI y Unicode</span><span class="sxs-lookup"><span data-stu-id="06635-110">To simplify using APIs that contain ANSI and Unicode versions</span></span>  
  
 <span data-ttu-id="06635-111">En este tema se muestra la forma de cambiar el nombre de una función de un archivo DLL en código administrado.</span><span class="sxs-lookup"><span data-stu-id="06635-111">This topic demonstrates how to rename a DLL function in managed code.</span></span>  
  
## <a name="renaming-a-function-in-visual-basic"></a><span data-ttu-id="06635-112">Cambiar el nombre de una función en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="06635-112">Renaming a Function in Visual Basic</span></span>  

<span data-ttu-id="06635-113">Visual Basic usa la palabra clave **Function** en la instrucción **Declare** para establecer el campo <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="06635-113">Visual Basic uses the **Function** keyword in the **Declare** statement to set the <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> field.</span></span> <span data-ttu-id="06635-114">En el siguiente ejemplo muestra una declaración básica.</span><span class="sxs-lookup"><span data-stu-id="06635-114">The following example shows a basic declaration.</span></span>  
  
```vb
Friend Class NativeMethods
    Friend Declare Auto Function MessageBox Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
End Class
```
  
<span data-ttu-id="06635-115">Es posible reemplazar el punto de entrada **MessageBox** por **MsgBox** incluyendo la palabra clave **Alias** en la definición, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="06635-115">You can replace the **MessageBox** entry point with **MsgBox** by including the **Alias** keyword in your definition, as shown in the following example.</span></span> <span data-ttu-id="06635-116">En los dos ejemplos, la palabra clave **Auto** elimina la necesidad de especificar la versión del juego de caracteres del punto de entrada.</span><span class="sxs-lookup"><span data-stu-id="06635-116">In both examples the **Auto** keyword eliminates the need to specify the character-set version of the entry point.</span></span> <span data-ttu-id="06635-117">Para obtener más información sobre cómo seleccionar un juego de caracteres, vea [Specifying a Character Set](specifying-a-character-set.md) (Especificar un juego de caracteres).</span><span class="sxs-lookup"><span data-stu-id="06635-117">For more information about selecting a character set, see [Specifying a Character Set](specifying-a-character-set.md).</span></span>  
  
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
  
## <a name="renaming-a-function-in-c-and-c"></a><span data-ttu-id="06635-118">Cambiar el nombre de una función en C# y C++</span><span class="sxs-lookup"><span data-stu-id="06635-118">Renaming a Function in C# and C++</span></span>  
 <span data-ttu-id="06635-119">Puede utilizar el campo <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> para especificar una función DLL por nombre u ordinal.</span><span class="sxs-lookup"><span data-stu-id="06635-119">You can use the <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> field to specify a DLL function by name or ordinal.</span></span> <span data-ttu-id="06635-120">Si el nombre de la función en la definición del método es el mismo que el punto de entrada en el archivo DLL, no es necesario identificar la función de forma explícita con el campo **EntryPoint**.</span><span class="sxs-lookup"><span data-stu-id="06635-120">If the name of the function in your method definition is the same as the entry point in the DLL, you do not have to explicitly identify the function with the **EntryPoint** field.</span></span> <span data-ttu-id="06635-121">En caso contrario, utilice una de las siguientes formas de atributo para indicar un nombre u ordinal:</span><span class="sxs-lookup"><span data-stu-id="06635-121">Otherwise, use one of the following attribute forms to indicate a name or ordinal:</span></span>  
  
```csharp
[DllImport("DllName", EntryPoint = "Functionname")]
[DllImport("DllName", EntryPoint = "#123")]
```
  
 <span data-ttu-id="06635-122">Tenga en cuenta que los ordinales deben ir precedidos del símbolo de libra esterlina (#).</span><span class="sxs-lookup"><span data-stu-id="06635-122">Notice that you must prefix an ordinal with the pound sign (#).</span></span>  
  
 <span data-ttu-id="06635-123">En el siguiente ejemplo se muestra cómo reemplazar **MessageBoxA** por **MsgBox** en el código usando el campo **EntryPoint**.</span><span class="sxs-lookup"><span data-stu-id="06635-123">The following example demonstrates how to replace **MessageBoxA** with **MsgBox** in your code by using the **EntryPoint** field.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="06635-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="06635-124">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [<span data-ttu-id="06635-125">Crear prototipos en código administrado</span><span class="sxs-lookup"><span data-stu-id="06635-125">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="06635-126">Ejemplos de invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="06635-126">Platform Invoke Examples</span></span>](platform-invoke-examples.md)
- [<span data-ttu-id="06635-127">Serialización de datos con invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="06635-127">Marshaling Data with Platform Invoke</span></span>](marshaling-data-with-platform-invoke.md)
