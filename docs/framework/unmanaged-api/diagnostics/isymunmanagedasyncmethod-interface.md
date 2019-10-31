---
title: ISymUnmanagedAsyncMethod (Interfaz)
ms.date: 03/30/2017
ms.assetid: f2de5224-fd91-45de-9e58-bc600c6d22f1
ms.openlocfilehash: 0b8adba9dbffbdc47bb526cef9aad3ffa4b48065
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129224"
---
# <a name="isymunmanagedasyncmethod-interface"></a><span data-ttu-id="cb646-102">ISymUnmanagedAsyncMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cb646-102">ISymUnmanagedAsyncMethod Interface</span></span>
<span data-ttu-id="cb646-103">Esta interfaz es el complemento de lectura de la [interfaz ISymUnmanagedAsyncMethodPropertiesWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span><span class="sxs-lookup"><span data-stu-id="cb646-103">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb646-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cb646-104">Syntax</span></span>  
  
```idl  
[object,uuid(B20D55B3-532E-4906-87E7-25BD5734ABD2),pointer_default(unique)]interface ISymUnmanagedAsyncMethod : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="cb646-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="cb646-105">Methods</span></span>  
 <span data-ttu-id="cb646-106">Esta interfaz contiene los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="cb646-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="cb646-107">Método</span><span class="sxs-lookup"><span data-stu-id="cb646-107">Method</span></span>|<span data-ttu-id="cb646-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="cb646-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cb646-109">GetAsyncStepInfo (método)</span><span class="sxs-lookup"><span data-stu-id="cb646-109">GetAsyncStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfo-method.md)|<span data-ttu-id="cb646-110">Consulte [método defineasyncstepinfo (](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="cb646-110">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="cb646-111">GetAsyncStepInfoCount (método)</span><span class="sxs-lookup"><span data-stu-id="cb646-111">GetAsyncStepInfoCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfocount-method.md)|<span data-ttu-id="cb646-112">Consulte [método defineasyncstepinfo (](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="cb646-112">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="cb646-113">GetCatchHandlerILOffset (método)</span><span class="sxs-lookup"><span data-stu-id="cb646-113">GetCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getcatchhandleriloffset-method.md)|<span data-ttu-id="cb646-114">Consulte [método definecatchhandleriloffset (](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="cb646-114">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="cb646-115">GetKickoffMethod (método)</span><span class="sxs-lookup"><span data-stu-id="cb646-115">GetKickoffMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getkickoffmethod-method.md)|<span data-ttu-id="cb646-116">Consulte [método definekickoffmethod (](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="cb646-116">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>|  
|[<span data-ttu-id="cb646-117">HasCatchHandlerILOffset (método)</span><span class="sxs-lookup"><span data-stu-id="cb646-117">HasCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-hascatchhandleriloffset-method.md)|<span data-ttu-id="cb646-118">Consulte [método definecatchhandleriloffset (](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="cb646-118">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="cb646-119">IsAsyncMethod (método)</span><span class="sxs-lookup"><span data-stu-id="cb646-119">IsAsyncMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-isasyncmethod-method.md)|<span data-ttu-id="cb646-120">Comprueba si el método tiene información asincrónica o no.</span><span class="sxs-lookup"><span data-stu-id="cb646-120">Checks if the method has async information or not.</span></span><br /><br /> <span data-ttu-id="cb646-121">Si este método devuelve `FALSE`, no es válido llamar a ningún otro método de esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="cb646-121">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="cb646-122">Todos devolverán `E_UNEXPECTED` en este caso.</span><span class="sxs-lookup"><span data-stu-id="cb646-122">They will all return `E_UNEXPECTED` in this case.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cb646-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cb646-123">Requirements</span></span>  
 <span data-ttu-id="cb646-124">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="cb646-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb646-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb646-125">See also</span></span>

- [<span data-ttu-id="cb646-126">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="cb646-126">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
