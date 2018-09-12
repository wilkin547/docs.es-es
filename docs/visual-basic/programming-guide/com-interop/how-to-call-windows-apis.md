---
title: 'Cómo: Llamar a las API de Windows (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
ms.openlocfilehash: 081f4242ef5883a8b25b8819ba3aff835b1e6ac7
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44208275"
---
# <a name="how-to-call-windows-apis-visual-basic"></a><span data-ttu-id="99578-102">Cómo: Llamar a las API de Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99578-102">How to: Call Windows APIs (Visual Basic)</span></span>
<span data-ttu-id="99578-103">En este ejemplo se define y se llama a la `MessageBox` función en user32.dll y, a continuación, se le pasa una cadena.</span><span class="sxs-lookup"><span data-stu-id="99578-103">This example defines and calls the `MessageBox` function in user32.dll and then passes a string to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99578-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="99578-104">Example</span></span>  
 [!code-vb[VbVbalrInterop#1](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-call-windows-apis_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="99578-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="99578-105">Compiling the Code</span></span>  
 <span data-ttu-id="99578-106">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="99578-106">This example requires:</span></span>  
  
-   <span data-ttu-id="99578-107">Una referencia al espacio de nombres <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="99578-107">A reference to the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="99578-108">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="99578-108">Robust Programming</span></span>  
 <span data-ttu-id="99578-109">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="99578-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="99578-110">El método no es estático, es abstracto o se ha definido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="99578-110">The method is not static, is abstract, or has been previously defined.</span></span> <span data-ttu-id="99578-111">El tipo primario es una interfaz o la longitud de *nombre* o *dllName* es cero.</span><span class="sxs-lookup"><span data-stu-id="99578-111">The parent type is an interface, or the length of *name* or *dllName* is zero.</span></span> <span data-ttu-id="99578-112">(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="99578-112">(<xref:System.ArgumentException>)</span></span>  
  
-   <span data-ttu-id="99578-113">El *nombre* o *dllName* es `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="99578-113">The *name* or *dllName* is `Nothing`.</span></span> <span data-ttu-id="99578-114">(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="99578-114">(<xref:System.ArgumentNullException>)</span></span>  
  
-   <span data-ttu-id="99578-115">Tipo contenedor que se ha creado anteriormente mediante `CreateType`.</span><span class="sxs-lookup"><span data-stu-id="99578-115">The containing type has been previously created using `CreateType`.</span></span> <span data-ttu-id="99578-116">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="99578-116">(<xref:System.InvalidOperationException>)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99578-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="99578-117">See also</span></span>

- [<span data-ttu-id="99578-118">Aproximación a la invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="99578-118">A Closer Look at Platform Invoke</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)  
- [<span data-ttu-id="99578-119">Ejemplos de invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="99578-119">Platform Invoke Examples</span></span>](../../../framework/interop/platform-invoke-examples.md)  
- [<span data-ttu-id="99578-120">Consumir funciones DLL no administradas</span><span class="sxs-lookup"><span data-stu-id="99578-120">Consuming Unmanaged DLL Functions</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md)  
- [<span data-ttu-id="99578-121">Definir un método con Reflection Emit</span><span class="sxs-lookup"><span data-stu-id="99578-121">Defining a Method with Reflection Emit</span></span>](https://msdn.microsoft.com/library/84fd3bf6-628f-41aa-83d9-b990cf926e81)  
- [<span data-ttu-id="99578-122">Tutorial: Llamar a las API de Windows</span><span class="sxs-lookup"><span data-stu-id="99578-122">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
- [<span data-ttu-id="99578-123">Interoperabilidad COM</span><span class="sxs-lookup"><span data-stu-id="99578-123">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)
