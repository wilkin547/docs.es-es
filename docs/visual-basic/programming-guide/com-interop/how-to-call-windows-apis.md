---
description: 'Más información acerca de cómo: llamar a las API de Windows (Visual Basic)'
title: Procedimiento Llamadas a las API de Windows
ms.date: 07/20/2015
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
ms.openlocfilehash: ec25df3715b1f8a4612c1575b5f7192d0a133c4b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100464916"
---
# <a name="how-to-call-windows-apis-visual-basic"></a><span data-ttu-id="9446e-103">Cómo: Llamar a las API de Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9446e-103">How to: Call Windows APIs (Visual Basic)</span></span>

<span data-ttu-id="9446e-104">En este ejemplo se define y `MessageBox` se llama a la función en user32.dll y, a continuación, se le pasa una cadena.</span><span class="sxs-lookup"><span data-stu-id="9446e-104">This example defines and calls the `MessageBox` function in user32.dll and then passes a string to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9446e-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9446e-105">Example</span></span>  

 [!code-vb[VbVbalrInterop#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#1)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="9446e-106">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="9446e-106">Compile the code</span></span>  

 <span data-ttu-id="9446e-107">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="9446e-107">This example requires:</span></span>  
  
- <span data-ttu-id="9446e-108">Una referencia al espacio de nombres <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="9446e-108">A reference to the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="9446e-109">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="9446e-109">Robust Programming</span></span>  

 <span data-ttu-id="9446e-110">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="9446e-110">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="9446e-111">El método no es estático, es abstracto o se ha definido previamente.</span><span class="sxs-lookup"><span data-stu-id="9446e-111">The method is not static, is abstract, or has been previously defined.</span></span> <span data-ttu-id="9446e-112">El tipo primario es una interfaz o la longitud del *nombre* o *DllName* es cero.</span><span class="sxs-lookup"><span data-stu-id="9446e-112">The parent type is an interface, or the length of *name* or *dllName* is zero.</span></span> <span data-ttu-id="9446e-113">(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="9446e-113">(<xref:System.ArgumentException>)</span></span>  
  
- <span data-ttu-id="9446e-114">El *nombre* o *DllName* es `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="9446e-114">The *name* or *dllName* is `Nothing`.</span></span> <span data-ttu-id="9446e-115">(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="9446e-115">(<xref:System.ArgumentNullException>)</span></span>  
  
- <span data-ttu-id="9446e-116">Tipo contenedor que se ha creado anteriormente mediante `CreateType`.</span><span class="sxs-lookup"><span data-stu-id="9446e-116">The containing type has been previously created using `CreateType`.</span></span> <span data-ttu-id="9446e-117">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="9446e-117">(<xref:System.InvalidOperationException>)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9446e-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9446e-118">See also</span></span>

- [<span data-ttu-id="9446e-119">Aproximación a la invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="9446e-119">A Closer Look at Platform Invoke</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [<span data-ttu-id="9446e-120">Ejemplos de invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="9446e-120">Platform Invoke Examples</span></span>](../../../framework/interop/platform-invoke-examples.md)
- [<span data-ttu-id="9446e-121">Consumir funciones DLL no administradas</span><span class="sxs-lookup"><span data-stu-id="9446e-121">Consuming Unmanaged DLL Functions</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md)
- <span data-ttu-id="9446e-122">[Definir un método con la emisión de la reflexión](/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9446e-122">[Defining a Method with Reflection Emit](/previous-versions/dotnet/netframework-4.0/w63y4d4f(v=vs.100))</span></span>
- [<span data-ttu-id="9446e-123">Tutorial: Llamadas a las API de Windows</span><span class="sxs-lookup"><span data-stu-id="9446e-123">Walkthrough: Calling Windows APIs</span></span>](walkthrough-calling-windows-apis.md)
- [<span data-ttu-id="9446e-124">Interoperabilidad COM</span><span class="sxs-lookup"><span data-stu-id="9446e-124">COM Interop</span></span>](index.md)
