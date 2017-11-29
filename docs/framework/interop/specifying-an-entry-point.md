---
title: Especificar un punto de entrada
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- EntryPoint field
- platform invoke, attribute fields
- attribute fields in platform invoke, EntryPoint
ms.assetid: d1247f08-0965-416a-b978-e0b50652dfe3
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7406e256acaea0c535c222386c529c4087bbdc6f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="specifying-an-entry-point"></a><span data-ttu-id="021a9-102">Especificar un punto de entrada</span><span class="sxs-lookup"><span data-stu-id="021a9-102">Specifying an Entry Point</span></span>
<span data-ttu-id="021a9-103">Un punto de entrada identifica la ubicación de una función en un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="021a9-103">An entry point identifies the location of a function in a DLL.</span></span> <span data-ttu-id="021a9-104">En un proyecto administrado, el nombre original o el punto de entrada ordinal de una función de destino identifica dicha función dentro de los límites de la interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="021a9-104">Within a managed project, the original name or ordinal entry point of a target function identifies that function across the interoperation boundary.</span></span> <span data-ttu-id="021a9-105">Además, puede asignarle otro nombre al punto de entrada, lo que supone en realidad un cambio de nombre de la función.</span><span class="sxs-lookup"><span data-stu-id="021a9-105">Further, you can map the entry point to a different name, effectively renaming the function.</span></span>  
  
 <span data-ttu-id="021a9-106">A continuación, se muestra una lista de las razones que pueden existir para desear cambiarle el nombre a una función de un archivo DLL:</span><span class="sxs-lookup"><span data-stu-id="021a9-106">Following is a list of possible reasons to rename a DLL function:</span></span>  
  
-   <span data-ttu-id="021a9-107">Para no utilizar nombres de función de la API que distinguen mayúsculas de minúsculas</span><span class="sxs-lookup"><span data-stu-id="021a9-107">To avoid using case-sensitive API function names</span></span>  
  
-   <span data-ttu-id="021a9-108">Para cumplir los estándares de nomenclatura existentes</span><span class="sxs-lookup"><span data-stu-id="021a9-108">To comply with existing naming standards</span></span>  
  
-   <span data-ttu-id="021a9-109">Para incluir funciones que toman tipos de datos distintos (declarando varias versiones de la misma función de un archivo DLL)</span><span class="sxs-lookup"><span data-stu-id="021a9-109">To accommodate functions that take different data types (by declaring multiple versions of the same DLL function)</span></span>  
  
-   <span data-ttu-id="021a9-110">Para simplificar el uso de las API que contienen versiones ANSI y Unicode</span><span class="sxs-lookup"><span data-stu-id="021a9-110">To simplify using APIs that contain ANSI and Unicode versions</span></span>  
  
 <span data-ttu-id="021a9-111">En este tema se muestra la forma de cambiar el nombre de una función de un archivo DLL en código administrado.</span><span class="sxs-lookup"><span data-stu-id="021a9-111">This topic demonstrates how to rename a DLL function in managed code.</span></span>  
  
## <a name="renaming-a-function-in-visual-basic"></a><span data-ttu-id="021a9-112">Cambiar el nombre de una función en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="021a9-112">Renaming a Function in Visual Basic</span></span>  
 <span data-ttu-id="021a9-113">Visual Basic usa la palabra clave **Function** en la instrucción **Declare** para establecer el campo <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="021a9-113">Visual Basic uses the **Function** keyword in the **Declare** statement to set the <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> field.</span></span> <span data-ttu-id="021a9-114">En el siguiente ejemplo muestra una declaración básica.</span><span class="sxs-lookup"><span data-stu-id="021a9-114">The following example shows a basic declaration.</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
  
Public Class Win32  
    Declare Auto Function MessageBox Lib "user32.dll" _  
       (ByVal hWnd As Integer, ByVal txt As String,_  
       ByVal caption As String, ByVal Typ As Integer) As Integer  
End Class  
```  
  
 <span data-ttu-id="021a9-115">Es posible reemplazar el punto de entrada **MessageBox** por **MsgBox** incluyendo la palabra clave **Alias** en la definición, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="021a9-115">You can replace the **MessageBox** entry point with **MsgBox** by including the **Alias** keyword in your definition, as shown in the following example.</span></span> <span data-ttu-id="021a9-116">En los dos ejemplos, la palabra clave **Auto** elimina la necesidad de especificar la versión del juego de caracteres del punto de entrada.</span><span class="sxs-lookup"><span data-stu-id="021a9-116">In both examples the **Auto** keyword eliminates the need to specify the character-set version of the entry point.</span></span> <span data-ttu-id="021a9-117">Para obtener más información sobre cómo seleccionar un juego de caracteres, vea [Specifying a Character Set](../../../docs/framework/interop/specifying-a-character-set.md) (Especificar un juego de caracteres).</span><span class="sxs-lookup"><span data-stu-id="021a9-117">For more information about selecting a character set, see [Specifying a Character Set](../../../docs/framework/interop/specifying-a-character-set.md).</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
  
Public Class Win32  
    Declare Auto Function MsgBox Lib "user32.dll" _  
       Alias "MessageBox" (ByVal hWnd As Integer, ByVal txt As String,_  
       ByVal caption As String, ByVal Typ As Integer) As Integer  
End Class  
```  
  
## <a name="renaming-a-function-in-c-and-c"></a><span data-ttu-id="021a9-118">Cambiar el nombre de una función en C# y C++</span><span class="sxs-lookup"><span data-stu-id="021a9-118">Renaming a Function in C# and C++</span></span>  
 <span data-ttu-id="021a9-119">Puede utilizar el campo <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> para especificar una función DLL por nombre u ordinal.</span><span class="sxs-lookup"><span data-stu-id="021a9-119">You can use the <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> field to specify a DLL function by name or ordinal.</span></span> <span data-ttu-id="021a9-120">Si el nombre de la función en la definición del método es el mismo que el punto de entrada en el archivo DLL, no es necesario identificar la función de forma explícita con el campo **EntryPoint**.</span><span class="sxs-lookup"><span data-stu-id="021a9-120">If the name of the function in your method definition is the same as the entry point in the DLL, you do not have to explicitly identify the function with the **EntryPoint** field.</span></span> <span data-ttu-id="021a9-121">En caso contrario, utilice una de las siguientes formas de atributo para indicar un nombre u ordinal:</span><span class="sxs-lookup"><span data-stu-id="021a9-121">Otherwise, use one of the following attribute forms to indicate a name or ordinal:</span></span>  
  
```  
[DllImport("dllname", EntryPoint="Functionname")]  
[DllImport("dllname", EntryPoint="#123")]  
```  
  
 <span data-ttu-id="021a9-122">Tenga en cuenta que los ordinales deben ir precedidos del símbolo de libra esterlina (#).</span><span class="sxs-lookup"><span data-stu-id="021a9-122">Notice that you must prefix an ordinal with the pound sign (#).</span></span>  
  
 <span data-ttu-id="021a9-123">En el siguiente ejemplo se muestra cómo reemplazar **MessageBoxA** por **MsgBox** en el código usando el campo **EntryPoint**.</span><span class="sxs-lookup"><span data-stu-id="021a9-123">The following example demonstrates how to replace **MessageBoxA** with **MsgBox** in your code by using the **EntryPoint** field.</span></span>  
  
```csharp  
using System.Runtime.InteropServices;  
  
public class Win32 {  
    [DllImport("user32.dll", EntryPoint="MessageBoxA")]  
    public static extern int MsgBox(int hWnd, String text, String caption,  
                                    uint type);  
}  
```  
  
```cpp  
using namespace System::Runtime::InteropServices;  
  
typedef void* HWND;  
[DllImport("user32", EntryPoint="MessageBoxA")]  
extern "C" int MsgBox(HWND hWnd,  
                      String*  pText,  
                      String*  pCaption,  
                      unsigned int uType);  
```  
  
## <a name="see-also"></a><span data-ttu-id="021a9-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="021a9-124">See Also</span></span>  
 <xref:System.Runtime.InteropServices.DllImportAttribute>  
 [<span data-ttu-id="021a9-125">Crear prototipos en código administrado</span><span class="sxs-lookup"><span data-stu-id="021a9-125">Creating Prototypes in Managed Code</span></span>](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)  
 [<span data-ttu-id="021a9-126">Ejemplos de invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="021a9-126">Platform Invoke Examples</span></span>](../../../docs/framework/interop/platform-invoke-examples.md)  
 [<span data-ttu-id="021a9-127">Serialización de datos con invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="021a9-127">Marshaling Data with Platform Invoke</span></span>](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)
