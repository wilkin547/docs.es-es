---
title: Procedimiento Llamadas a las API de Windows
ms.date: 07/20/2015
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
ms.openlocfilehash: 2c3bb599b79575180eb2b0ec89453f01901f94c0
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396848"
---
# <a name="how-to-call-windows-apis-visual-basic"></a><span data-ttu-id="29743-102">Cómo: Llamar a las API de Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="29743-102">How to: Call Windows APIs (Visual Basic)</span></span>
<span data-ttu-id="29743-103">En este ejemplo se define y `MessageBox` se llama a la función en user32. dll y, a continuación, se le pasa una cadena.</span><span class="sxs-lookup"><span data-stu-id="29743-103">This example defines and calls the `MessageBox` function in user32.dll and then passes a string to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29743-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="29743-104">Example</span></span>  
 [!code-vb[VbVbalrInterop#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#1)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="29743-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="29743-105">Compile the code</span></span>  
 <span data-ttu-id="29743-106">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="29743-106">This example requires:</span></span>  
  
- <span data-ttu-id="29743-107">Una referencia al espacio de nombres <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="29743-107">A reference to the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="29743-108">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="29743-108">Robust Programming</span></span>  
 <span data-ttu-id="29743-109">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="29743-109">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="29743-110">El método no es estático, es abstracto o se ha definido previamente.</span><span class="sxs-lookup"><span data-stu-id="29743-110">The method is not static, is abstract, or has been previously defined.</span></span> <span data-ttu-id="29743-111">El tipo primario es una interfaz o la longitud del *nombre* o *DllName* es cero.</span><span class="sxs-lookup"><span data-stu-id="29743-111">The parent type is an interface, or the length of *name* or *dllName* is zero.</span></span> <span data-ttu-id="29743-112">(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="29743-112">(<xref:System.ArgumentException>)</span></span>  
  
- <span data-ttu-id="29743-113">El *nombre* o *DllName* es `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="29743-113">The *name* or *dllName* is `Nothing`.</span></span> <span data-ttu-id="29743-114">(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="29743-114">(<xref:System.ArgumentNullException>)</span></span>  
  
- <span data-ttu-id="29743-115">Tipo contenedor que se ha creado anteriormente mediante `CreateType`.</span><span class="sxs-lookup"><span data-stu-id="29743-115">The containing type has been previously created using `CreateType`.</span></span> <span data-ttu-id="29743-116">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="29743-116">(<xref:System.InvalidOperationException>)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29743-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="29743-117">See also</span></span>

- [<span data-ttu-id="29743-118">Una visión más detallada de la invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="29743-118">A Closer Look at Platform Invoke</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [<span data-ttu-id="29743-119">Ejemplos de invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="29743-119">Platform Invoke Examples</span></span>](../../../framework/interop/platform-invoke-examples.md)
- [<span data-ttu-id="29743-120">Consumir funciones DLL no administradas</span><span class="sxs-lookup"><span data-stu-id="29743-120">Consuming Unmanaged DLL Functions</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md)
- <span data-ttu-id="29743-121">[Definir un método con la emisión de la reflexión](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="29743-121">[Defining a Method with Reflection Emit](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))</span></span>
- [<span data-ttu-id="29743-122">Tutorial: Llamadas a las API de Windows</span><span class="sxs-lookup"><span data-stu-id="29743-122">Walkthrough: Calling Windows APIs</span></span>](walkthrough-calling-windows-apis.md)
- [<span data-ttu-id="29743-123">Interoperabilidad COM</span><span class="sxs-lookup"><span data-stu-id="29743-123">COM Interop</span></span>](index.md)
