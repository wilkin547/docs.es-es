---
title: ISymUnmanagedAsyncMethod (Interfaz)
ms.date: 03/30/2017
ms.assetid: f2de5224-fd91-45de-9e58-bc600c6d22f1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd524446cd9fd5cf9c067ab5778a654ed000ffb3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59179808"
---
# <a name="isymunmanagedasyncmethod-interface"></a><span data-ttu-id="0c1d8-102">ISymUnmanagedAsyncMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0c1d8-102">ISymUnmanagedAsyncMethod Interface</span></span>
<span data-ttu-id="0c1d8-103">Esta interfaz es el complemento de lectura a [ISymUnmanagedAsyncMethodPropertiesWriter (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span><span class="sxs-lookup"><span data-stu-id="0c1d8-103">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c1d8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0c1d8-104">Syntax</span></span>  
  
```idl  
[object,uuid(B20D55B3-532E-4906-87E7-25BD5734ABD2),pointer_default(unique)]interface ISymUnmanagedAsyncMethod : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="0c1d8-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="0c1d8-105">Methods</span></span>  
 <span data-ttu-id="0c1d8-106">Esta interfaz contiene los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="0c1d8-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="0c1d8-107">Método</span><span class="sxs-lookup"><span data-stu-id="0c1d8-107">Method</span></span>|<span data-ttu-id="0c1d8-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c1d8-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0c1d8-109">Método GetAsyncStepInfo</span><span class="sxs-lookup"><span data-stu-id="0c1d8-109">GetAsyncStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfo-method.md)|<span data-ttu-id="0c1d8-110">Consulte [DefineAsyncStepInfo (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="0c1d8-110">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="0c1d8-111">Método GetAsyncStepInfoCount</span><span class="sxs-lookup"><span data-stu-id="0c1d8-111">GetAsyncStepInfoCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfocount-method.md)|<span data-ttu-id="0c1d8-112">Consulte [DefineAsyncStepInfo (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="0c1d8-112">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="0c1d8-113">Método GetCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="0c1d8-113">GetCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getcatchhandleriloffset-method.md)|<span data-ttu-id="0c1d8-114">Consulte [DefineCatchHandlerILOffset (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="0c1d8-114">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="0c1d8-115">Método GetKickoffMethod</span><span class="sxs-lookup"><span data-stu-id="0c1d8-115">GetKickoffMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getkickoffmethod-method.md)|<span data-ttu-id="0c1d8-116">Consulte [DefineKickoffMethod (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="0c1d8-116">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>|  
|[<span data-ttu-id="0c1d8-117">Método HasCatchHandlerILOffset</span><span class="sxs-lookup"><span data-stu-id="0c1d8-117">HasCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-hascatchhandleriloffset-method.md)|<span data-ttu-id="0c1d8-118">Consulte [DefineCatchHandlerILOffset (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="0c1d8-118">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="0c1d8-119">Método IsAsyncMethod</span><span class="sxs-lookup"><span data-stu-id="0c1d8-119">IsAsyncMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-isasyncmethod-method.md)|<span data-ttu-id="0c1d8-120">Comprueba si el método tiene información de async o no.</span><span class="sxs-lookup"><span data-stu-id="0c1d8-120">Checks if the method has async information or not.</span></span><br /><br /> <span data-ttu-id="0c1d8-121">Si este método devuelve `FALSE` , a continuación, no es válido llamar a los otros métodos en esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="0c1d8-121">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="0c1d8-122">Lo harán todas devuelven `E_UNEXPECTED` en este caso.</span><span class="sxs-lookup"><span data-stu-id="0c1d8-122">They will all return `E_UNEXPECTED` in this case.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0c1d8-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0c1d8-123">Requirements</span></span>  
 <span data-ttu-id="0c1d8-124">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0c1d8-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c1d8-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c1d8-125">See also</span></span>

- [<span data-ttu-id="0c1d8-126">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="0c1d8-126">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
