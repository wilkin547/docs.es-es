---
title: Procedimiento Llamadas a las API de Windows
ms.date: 07/20/2015
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
ms.openlocfilehash: 40b40c1a489d514c82cbccdeacda27900d9ec87d
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91083363"
---
# <a name="how-to-call-windows-apis-visual-basic"></a><span data-ttu-id="75e02-102">Cómo: Llamar a las API de Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="75e02-102">How to: Call Windows APIs (Visual Basic)</span></span>

<span data-ttu-id="75e02-103">En este ejemplo se define y `MessageBox` se llama a la función en user32.dll y, a continuación, se le pasa una cadena.</span><span class="sxs-lookup"><span data-stu-id="75e02-103">This example defines and calls the `MessageBox` function in user32.dll and then passes a string to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75e02-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="75e02-104">Example</span></span>  

 [!code-vb[VbVbalrInterop#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#1)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="75e02-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="75e02-105">Compile the code</span></span>  

 <span data-ttu-id="75e02-106">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="75e02-106">This example requires:</span></span>  
  
- <span data-ttu-id="75e02-107">Una referencia al espacio de nombres <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="75e02-107">A reference to the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="75e02-108">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="75e02-108">Robust Programming</span></span>  

 <span data-ttu-id="75e02-109">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="75e02-109">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="75e02-110">El método no es estático, es abstracto o se ha definido previamente.</span><span class="sxs-lookup"><span data-stu-id="75e02-110">The method is not static, is abstract, or has been previously defined.</span></span> <span data-ttu-id="75e02-111">El tipo primario es una interfaz o la longitud del *nombre* o *DllName* es cero.</span><span class="sxs-lookup"><span data-stu-id="75e02-111">The parent type is an interface, or the length of *name* or *dllName* is zero.</span></span> <span data-ttu-id="75e02-112">(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="75e02-112">(<xref:System.ArgumentException>)</span></span>  
  
- <span data-ttu-id="75e02-113">El *nombre* o *DllName* es `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="75e02-113">The *name* or *dllName* is `Nothing`.</span></span> <span data-ttu-id="75e02-114">(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="75e02-114">(<xref:System.ArgumentNullException>)</span></span>  
  
- <span data-ttu-id="75e02-115">Tipo contenedor que se ha creado anteriormente mediante `CreateType`.</span><span class="sxs-lookup"><span data-stu-id="75e02-115">The containing type has been previously created using `CreateType`.</span></span> <span data-ttu-id="75e02-116">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="75e02-116">(<xref:System.InvalidOperationException>)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75e02-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="75e02-117">See also</span></span>

- [<span data-ttu-id="75e02-118">Aproximación a la invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="75e02-118">A Closer Look at Platform Invoke</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [<span data-ttu-id="75e02-119">Ejemplos de invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="75e02-119">Platform Invoke Examples</span></span>](../../../framework/interop/platform-invoke-examples.md)
- [<span data-ttu-id="75e02-120">Consumir funciones DLL no administradas</span><span class="sxs-lookup"><span data-stu-id="75e02-120">Consuming Unmanaged DLL Functions</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md)
- <span data-ttu-id="75e02-121">[Definir un método con la emisión de la reflexión](/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="75e02-121">[Defining a Method with Reflection Emit](/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))</span></span>
- [<span data-ttu-id="75e02-122">Tutorial: Llamadas a las API de Windows</span><span class="sxs-lookup"><span data-stu-id="75e02-122">Walkthrough: Calling Windows APIs</span></span>](walkthrough-calling-windows-apis.md)
- [<span data-ttu-id="75e02-123">Interoperabilidad COM</span><span class="sxs-lookup"><span data-stu-id="75e02-123">COM Interop</span></span>](index.md)
