---
title: ISymUnmanagedAsyncMethod (Interfaz)
ms.date: 03/30/2017
ms.assetid: f2de5224-fd91-45de-9e58-bc600c6d22f1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cefad27d8b9314b45dec6100e35a54990fb591c2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428004"
---
# <a name="isymunmanagedasyncmethod-interface"></a><span data-ttu-id="2aaca-102">ISymUnmanagedAsyncMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2aaca-102">ISymUnmanagedAsyncMethod Interface</span></span>
<span data-ttu-id="2aaca-103">Esta interfaz es el complemento de lectura a [ISymUnmanagedAsyncMethodPropertiesWriter (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span><span class="sxs-lookup"><span data-stu-id="2aaca-103">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2aaca-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2aaca-104">Syntax</span></span>  
  
```idl  
[object,uuid(B20D55B3-532E-4906-87E7-25BD5734ABD2),pointer_default(unique)]interface ISymUnmanagedAsyncMethod : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="2aaca-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="2aaca-105">Methods</span></span>  
 <span data-ttu-id="2aaca-106">Esta interfaz contiene los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="2aaca-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="2aaca-107">Método</span><span class="sxs-lookup"><span data-stu-id="2aaca-107">Method</span></span>|<span data-ttu-id="2aaca-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="2aaca-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2aaca-109">GetAsyncStepInfo (método)</span><span class="sxs-lookup"><span data-stu-id="2aaca-109">GetAsyncStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfo-method.md)|<span data-ttu-id="2aaca-110">Vea [DefineAsyncStepInfo (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="2aaca-110">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="2aaca-111">GetAsyncStepInfoCount (método)</span><span class="sxs-lookup"><span data-stu-id="2aaca-111">GetAsyncStepInfoCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfocount-method.md)|<span data-ttu-id="2aaca-112">Vea [DefineAsyncStepInfo (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="2aaca-112">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="2aaca-113">GetCatchHandlerILOffset (método)</span><span class="sxs-lookup"><span data-stu-id="2aaca-113">GetCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getcatchhandleriloffset-method.md)|<span data-ttu-id="2aaca-114">Vea [DefineCatchHandlerILOffset (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="2aaca-114">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="2aaca-115">GetKickoffMethod (método)</span><span class="sxs-lookup"><span data-stu-id="2aaca-115">GetKickoffMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getkickoffmethod-method.md)|<span data-ttu-id="2aaca-116">Vea [DefineKickoffMethod (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="2aaca-116">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>|  
|[<span data-ttu-id="2aaca-117">HasCatchHandlerILOffset (método)</span><span class="sxs-lookup"><span data-stu-id="2aaca-117">HasCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-hascatchhandleriloffset-method.md)|<span data-ttu-id="2aaca-118">Vea [DefineCatchHandlerILOffset (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="2aaca-118">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="2aaca-119">IsAsyncMethod (método)</span><span class="sxs-lookup"><span data-stu-id="2aaca-119">IsAsyncMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-isasyncmethod-method.md)|<span data-ttu-id="2aaca-120">Comprueba si el método tiene información de async o no.</span><span class="sxs-lookup"><span data-stu-id="2aaca-120">Checks if the method has async information or not.</span></span><br /><br /> <span data-ttu-id="2aaca-121">Si este método devuelve `FALSE` , a continuación, no es válido para llamar a ningún otro método en esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="2aaca-121">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="2aaca-122">Lo harían devuelven todos los `E_UNEXPECTED` en este caso.</span><span class="sxs-lookup"><span data-stu-id="2aaca-122">They will all return `E_UNEXPECTED` in this case.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2aaca-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2aaca-123">Requirements</span></span>  
 <span data-ttu-id="2aaca-124">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2aaca-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2aaca-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="2aaca-125">See Also</span></span>  
 [<span data-ttu-id="2aaca-126">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="2aaca-126">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
