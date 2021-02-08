---
description: 'Más información acerca de: interfaz ISymUnmanagedAsyncMethodPropertiesWriter'
title: ISymUnmanagedAsyncMethodPropertiesWriter (Interfaz)
ms.date: 03/30/2017
ms.assetid: caa71820-8058-4b6a-93a2-25ee757d92d3
ms.openlocfilehash: 4c8b1bc037485e22160af28b59d751859a157499
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790196"
---
# <a name="isymunmanagedasyncmethodpropertieswriter-interface"></a><span data-ttu-id="b92d5-103">ISymUnmanagedAsyncMethodPropertiesWriter (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b92d5-103">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>

<span data-ttu-id="b92d5-104">Permite definir información de método asincrónico opcional para cada símbolo de método.</span><span class="sxs-lookup"><span data-stu-id="b92d5-104">Allows you to define optional async method information for each method symbol.</span></span> <span data-ttu-id="b92d5-105">Siempre se usa con un método abierto; es decir, entre las llamadas al [método openmethod (](isymunmanagedwriter-openmethod-method.md) y al [método CloseMethod (](isymunmanagedwriter-closemethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="b92d5-105">Always use with an opened method; that is, between calls to the [OpenMethod Method](isymunmanagedwriter-openmethod-method.md) and the [CloseMethod Method](isymunmanagedwriter-closemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b92d5-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b92d5-106">Syntax</span></span>  
  
```idl  
[object,uuid(FC073774-1739-4232-BD56-A027294BEC15),pointer_default(unique)]interface ISymUnmanagedAsyncMethodPropertiesWriter : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="b92d5-107">Métodos</span><span class="sxs-lookup"><span data-stu-id="b92d5-107">Methods</span></span>  

 <span data-ttu-id="b92d5-108">Esta interfaz contiene los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="b92d5-108">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="b92d5-109">Método</span><span class="sxs-lookup"><span data-stu-id="b92d5-109">Method</span></span>|<span data-ttu-id="b92d5-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="b92d5-110">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b92d5-111">Método DefineAsyncStepInfo</span><span class="sxs-lookup"><span data-stu-id="b92d5-111">DefineAsyncStepInfo Method</span></span>](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)|<span data-ttu-id="b92d5-112">Defina un grupo de operaciones de espera asincrónica en el método actual.</span><span class="sxs-lookup"><span data-stu-id="b92d5-112">Define a group of async await operations in the current method.</span></span><br /><br /> <span data-ttu-id="b92d5-113">Cada desplazamiento yield coincide con una instrucción return de Await, que identifica un posible rendimiento.</span><span class="sxs-lookup"><span data-stu-id="b92d5-113">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="b92d5-114">Cada `breakpointMethod` / `breakpointOffset` par identifica dónde se reanudará la operación asincrónica; puede estar en un método diferente.</span><span class="sxs-lookup"><span data-stu-id="b92d5-114">Each `breakpointMethod`/`breakpointOffset` pair identifies where the asynchronous operation will resume; it may be in a different method.</span></span>|  
|[<span data-ttu-id="b92d5-115">Método DefineCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="b92d5-115">DefineCatchHandlerILOffset Method</span></span>](isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)|<span data-ttu-id="b92d5-116">Establece el desplazamiento IL para el controlador Catch generado por el compilador que ajusta un método asincrónico.</span><span class="sxs-lookup"><span data-stu-id="b92d5-116">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span><br /><br /> <span data-ttu-id="b92d5-117">El depurador usa el desplazamiento IL de la captura generada para controlar la detección como si se tratara de código que no es de usuario, aunque puede producirse en un método de código de usuario.</span><span class="sxs-lookup"><span data-stu-id="b92d5-117">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code, even though it may occur in a user code method.</span></span> <span data-ttu-id="b92d5-118">En concreto, se utiliza en respuesta a un evento de excepción **CatchHandlerFound** .</span><span class="sxs-lookup"><span data-stu-id="b92d5-118">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>|  
|[<span data-ttu-id="b92d5-119">Método DefineKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="b92d5-119">DefineKickoffMethod Method</span></span>](isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)|<span data-ttu-id="b92d5-120">Establece el método de inicio que inicia la operación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="b92d5-120">Sets the starting method that initiates the async operation.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b92d5-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b92d5-121">Requirements</span></span>  

 <span data-ttu-id="b92d5-122">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="b92d5-122">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b92d5-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="b92d5-123">See also</span></span>

- [<span data-ttu-id="b92d5-124">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="b92d5-124">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
