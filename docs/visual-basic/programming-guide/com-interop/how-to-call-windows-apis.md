---
title: "Cómo: Llamar a las API de Windows (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a219e031cdd36c713db8dcee6cc1da3849c9cf93
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-windows-apis-visual-basic"></a><span data-ttu-id="9ecf1-102">Cómo: Llamar a las API de Windows (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9ecf1-102">How to: Call Windows APIs (Visual Basic)</span></span>
<span data-ttu-id="9ecf1-103">En este ejemplo se define y se llama a la `MessageBox` función en user32.dll y, a continuación, se le pasa una cadena.</span><span class="sxs-lookup"><span data-stu-id="9ecf1-103">This example defines and calls the `MessageBox` function in user32.dll and then passes a string to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ecf1-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9ecf1-104">Example</span></span>  
 [!code-vb[VbVbalrInterop#1](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-call-windows-apis_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9ecf1-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="9ecf1-105">Compiling the Code</span></span>  
 <span data-ttu-id="9ecf1-106">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="9ecf1-106">This example requires:</span></span>  
  
-   <span data-ttu-id="9ecf1-107">Una referencia al espacio de nombres <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="9ecf1-107">A reference to the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="9ecf1-108">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="9ecf1-108">Robust Programming</span></span>  
 <span data-ttu-id="9ecf1-109">Las condiciones siguientes pueden provocar una excepción:</span><span class="sxs-lookup"><span data-stu-id="9ecf1-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="9ecf1-110">El método no es estático, es abstracto o se ha definido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9ecf1-110">The method is not static, is abstract, or has been previously defined.</span></span> <span data-ttu-id="9ecf1-111">El tipo principal es una interfaz o la longitud de *nombre* o *nombre dll* es cero.</span><span class="sxs-lookup"><span data-stu-id="9ecf1-111">The parent type is an interface, or the length of *name* or *dllName* is zero.</span></span> <span data-ttu-id="9ecf1-112">(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="9ecf1-112">(<xref:System.ArgumentException>)</span></span>  
  
-   <span data-ttu-id="9ecf1-113">El *nombre* o *nombre dll* es `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="9ecf1-113">The *name* or *dllName* is `Nothing`.</span></span> <span data-ttu-id="9ecf1-114">(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="9ecf1-114">(<xref:System.ArgumentNullException>)</span></span>  
  
-   <span data-ttu-id="9ecf1-115">Tipo contenedor que se ha creado anteriormente mediante `CreateType`.</span><span class="sxs-lookup"><span data-stu-id="9ecf1-115">The containing type has been previously created using `CreateType`.</span></span> <span data-ttu-id="9ecf1-116">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="9ecf1-116">(<xref:System.InvalidOperationException>)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ecf1-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ecf1-117">See Also</span></span>  
 [<span data-ttu-id="9ecf1-118">Invocación de un vistazo más cerca de la plataforma</span><span class="sxs-lookup"><span data-stu-id="9ecf1-118">A Closer Look at Platform Invoke</span></span>](http://msdn.microsoft.com/en-us/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)  
 [<span data-ttu-id="9ecf1-119">Ejemplos de invocación de plataforma</span><span class="sxs-lookup"><span data-stu-id="9ecf1-119">Platform Invoke Examples</span></span>](../../../framework/interop/platform-invoke-examples.md)  
 [<span data-ttu-id="9ecf1-120">Consumir funciones DLL no administradas</span><span class="sxs-lookup"><span data-stu-id="9ecf1-120">Consuming Unmanaged DLL Functions</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md)  
 [<span data-ttu-id="9ecf1-121">Definir un método con Reflection Emit</span><span class="sxs-lookup"><span data-stu-id="9ecf1-121">Defining a Method with Reflection Emit</span></span>](http://msdn.microsoft.com/en-us/84fd3bf6-628f-41aa-83d9-b990cf926e81)  
 [<span data-ttu-id="9ecf1-122">Tutorial: Llamar a las API de Windows</span><span class="sxs-lookup"><span data-stu-id="9ecf1-122">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
 [<span data-ttu-id="9ecf1-123">Interoperabilidad COM</span><span class="sxs-lookup"><span data-stu-id="9ecf1-123">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)
