---
title: 'Cómo: Llamar a las API de Windows (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
ms.openlocfilehash: de568c3273d4d040c6566136e5d59e2155b86f8b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33643645"
---
# <a name="how-to-call-windows-apis-visual-basic"></a><span data-ttu-id="63cd4-102">Cómo: Llamar a las API de Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="63cd4-102">How to: Call Windows APIs (Visual Basic)</span></span>
<span data-ttu-id="63cd4-103">En este ejemplo se define y se llama a la `MessageBox` función en user32.dll y, a continuación, se le pasa una cadena.</span><span class="sxs-lookup"><span data-stu-id="63cd4-103">This example defines and calls the `MessageBox` function in user32.dll and then passes a string to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63cd4-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="63cd4-104">Example</span></span>  
 [!code-vb[VbVbalrInterop#1](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-call-windows-apis_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="63cd4-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="63cd4-105">Compiling the Code</span></span>  
 <span data-ttu-id="63cd4-106">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="63cd4-106">This example requires:</span></span>  
  
-   <span data-ttu-id="63cd4-107">Una referencia al espacio de nombres <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="63cd4-107">A reference to the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="63cd4-108">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="63cd4-108">Robust Programming</span></span>  
 <span data-ttu-id="63cd4-109">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="63cd4-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="63cd4-110">El método no es estático, es abstracto o se ha definido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="63cd4-110">The method is not static, is abstract, or has been previously defined.</span></span> <span data-ttu-id="63cd4-111">El tipo principal es una interfaz o la longitud de *nombre* o *nombre dll* es cero.</span><span class="sxs-lookup"><span data-stu-id="63cd4-111">The parent type is an interface, or the length of *name* or *dllName* is zero.</span></span> <span data-ttu-id="63cd4-112">(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="63cd4-112">(<xref:System.ArgumentException>)</span></span>  
  
-   <span data-ttu-id="63cd4-113">El *nombre* o *nombre dll* es `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="63cd4-113">The *name* or *dllName* is `Nothing`.</span></span> <span data-ttu-id="63cd4-114">(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="63cd4-114">(<xref:System.ArgumentNullException>)</span></span>  
  
-   <span data-ttu-id="63cd4-115">Tipo contenedor que se ha creado anteriormente mediante `CreateType`.</span><span class="sxs-lookup"><span data-stu-id="63cd4-115">The containing type has been previously created using `CreateType`.</span></span> <span data-ttu-id="63cd4-116">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="63cd4-116">(<xref:System.InvalidOperationException>)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63cd4-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="63cd4-117">See Also</span></span>  
 [<span data-ttu-id="63cd4-118">Aproximación a la invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="63cd4-118">A Closer Look at Platform Invoke</span></span>](http://msdn.microsoft.com/library/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)  
 [<span data-ttu-id="63cd4-119">Ejemplos de invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="63cd4-119">Platform Invoke Examples</span></span>](../../../framework/interop/platform-invoke-examples.md)  
 [<span data-ttu-id="63cd4-120">Consumir funciones DLL no administradas</span><span class="sxs-lookup"><span data-stu-id="63cd4-120">Consuming Unmanaged DLL Functions</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md)  
 [<span data-ttu-id="63cd4-121">Definir un método con Reflection Emit</span><span class="sxs-lookup"><span data-stu-id="63cd4-121">Defining a Method with Reflection Emit</span></span>](http://msdn.microsoft.com/library/84fd3bf6-628f-41aa-83d9-b990cf926e81)  
 [<span data-ttu-id="63cd4-122">Tutorial: Llamar a las API de Windows</span><span class="sxs-lookup"><span data-stu-id="63cd4-122">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
 [<span data-ttu-id="63cd4-123">Interoperabilidad COM</span><span class="sxs-lookup"><span data-stu-id="63cd4-123">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)
