---
title: Filtrar Llamar a las API de Windows (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
ms.openlocfilehash: 9eb667c8492c1e20b82e16ae8d640aee872969e5
ms.sourcegitcommit: facefcacd7ae2e5645e463bc841df213c505ffd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2019
ms.locfileid: "55738648"
---
# <a name="how-to-call-windows-apis-visual-basic"></a><span data-ttu-id="93d40-102">Filtrar Llamar a las API de Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="93d40-102">How to: Call Windows APIs (Visual Basic)</span></span>
<span data-ttu-id="93d40-103">En este ejemplo se define y se llama a la `MessageBox` función en user32.dll y, a continuación, se le pasa una cadena.</span><span class="sxs-lookup"><span data-stu-id="93d40-103">This example defines and calls the `MessageBox` function in user32.dll and then passes a string to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93d40-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="93d40-104">Example</span></span>  
 [!code-vb[VbVbalrInterop#1](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-call-windows-apis_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="93d40-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="93d40-105">Compiling the Code</span></span>  
 <span data-ttu-id="93d40-106">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="93d40-106">This example requires:</span></span>  
  
-   <span data-ttu-id="93d40-107">Una referencia al espacio de nombres <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="93d40-107">A reference to the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="93d40-108">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="93d40-108">Robust Programming</span></span>  
 <span data-ttu-id="93d40-109">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="93d40-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="93d40-110">El método no es estático, es abstracto o se ha definido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="93d40-110">The method is not static, is abstract, or has been previously defined.</span></span> <span data-ttu-id="93d40-111">El tipo primario es una interfaz o la longitud de *nombre* o *dllName* es cero.</span><span class="sxs-lookup"><span data-stu-id="93d40-111">The parent type is an interface, or the length of *name* or *dllName* is zero.</span></span> <span data-ttu-id="93d40-112">(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="93d40-112">(<xref:System.ArgumentException>)</span></span>  
  
-   <span data-ttu-id="93d40-113">El *nombre* o *dllName* es `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="93d40-113">The *name* or *dllName* is `Nothing`.</span></span> <span data-ttu-id="93d40-114">(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="93d40-114">(<xref:System.ArgumentNullException>)</span></span>  
  
-   <span data-ttu-id="93d40-115">Tipo contenedor que se ha creado anteriormente mediante `CreateType`.</span><span class="sxs-lookup"><span data-stu-id="93d40-115">The containing type has been previously created using `CreateType`.</span></span> <span data-ttu-id="93d40-116">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="93d40-116">(<xref:System.InvalidOperationException>)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93d40-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="93d40-117">See also</span></span>

- [<span data-ttu-id="93d40-118">Aproximación a la invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="93d40-118">A Closer Look at Platform Invoke</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [<span data-ttu-id="93d40-119">Ejemplos de invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="93d40-119">Platform Invoke Examples</span></span>](../../../framework/interop/platform-invoke-examples.md)
- [<span data-ttu-id="93d40-120">Consumir funciones DLL no administradas</span><span class="sxs-lookup"><span data-stu-id="93d40-120">Consuming Unmanaged DLL Functions</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md)
- <span data-ttu-id="93d40-121">[Definir un método con Reflection Emit](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="93d40-121">[Defining a Method with Reflection Emit](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))</span></span>
- [<span data-ttu-id="93d40-122">Tutorial: Llamar a las API de Windows</span><span class="sxs-lookup"><span data-stu-id="93d40-122">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
- [<span data-ttu-id="93d40-123">Interoperabilidad COM</span><span class="sxs-lookup"><span data-stu-id="93d40-123">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)
