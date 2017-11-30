---
title: ISymUnmanagedAsyncMethod (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: f2de5224-fd91-45de-9e58-bc600c6d22f1
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3ee944940cef0d3162a020c81353fd6b8cfb82f8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedasyncmethod-interface"></a><span data-ttu-id="b7896-102">ISymUnmanagedAsyncMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b7896-102">ISymUnmanagedAsyncMethod Interface</span></span>
<span data-ttu-id="b7896-103">Esta interfaz es el complemento de lectura a [ISymUnmanagedAsyncMethodPropertiesWriter (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span><span class="sxs-lookup"><span data-stu-id="b7896-103">This interface is the reading complement to [ISymUnmanagedAsyncMethodPropertiesWriter Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7896-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7896-104">Syntax</span></span>  
  
```idl  
[object,uuid(B20D55B3-532E-4906-87E7-25BD5734ABD2),pointer_default(unique)]interface ISymUnmanagedAsyncMethod : IUnknown  
```  
  
## <a name="methods"></a><span data-ttu-id="b7896-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="b7896-105">Methods</span></span>  
 <span data-ttu-id="b7896-106">Esta interfaz contiene los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="b7896-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="b7896-107">Método</span><span class="sxs-lookup"><span data-stu-id="b7896-107">Method</span></span>|<span data-ttu-id="b7896-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7896-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b7896-109">GetAsyncStepInfo (método)</span><span class="sxs-lookup"><span data-stu-id="b7896-109">GetAsyncStepInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfo-method.md)|<span data-ttu-id="b7896-110">Vea [DefineAsyncStepInfo (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="b7896-110">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="b7896-111">GetAsyncStepInfoCount (método)</span><span class="sxs-lookup"><span data-stu-id="b7896-111">GetAsyncStepInfoCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getasyncstepinfocount-method.md)|<span data-ttu-id="b7896-112">Vea [DefineAsyncStepInfo (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="b7896-112">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>|  
|[<span data-ttu-id="b7896-113">GetCatchHandlerILOffset (método)</span><span class="sxs-lookup"><span data-stu-id="b7896-113">GetCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getcatchhandleriloffset-method.md)|<span data-ttu-id="b7896-114">Vea [DefineCatchHandlerILOffset (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="b7896-114">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="b7896-115">GetKickoffMethod (método)</span><span class="sxs-lookup"><span data-stu-id="b7896-115">GetKickoffMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-getkickoffmethod-method.md)|<span data-ttu-id="b7896-116">Vea [DefineKickoffMethod (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="b7896-116">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>|  
|[<span data-ttu-id="b7896-117">HasCatchHandlerILOffset (método)</span><span class="sxs-lookup"><span data-stu-id="b7896-117">HasCatchHandlerILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-hascatchhandleriloffset-method.md)|<span data-ttu-id="b7896-118">Vea [DefineCatchHandlerILOffset (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="b7896-118">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>|  
|[<span data-ttu-id="b7896-119">IsAsyncMethod (método)</span><span class="sxs-lookup"><span data-stu-id="b7896-119">IsAsyncMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-isasyncmethod-method.md)|<span data-ttu-id="b7896-120">Comprueba si el método tiene información de async o no.</span><span class="sxs-lookup"><span data-stu-id="b7896-120">Checks if the method has async information or not.</span></span><br /><br /> <span data-ttu-id="b7896-121">Si este método devuelve `FALSE` , a continuación, no es válido para llamar a ningún otro método en esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="b7896-121">If this method returns `FALSE` then it is invalid to call any other methods in this interface.</span></span> <span data-ttu-id="b7896-122">Lo harían devuelven todos los `E_UNEXPECTED` en este caso.</span><span class="sxs-lookup"><span data-stu-id="b7896-122">They will all return `E_UNEXPECTED` in this case.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b7896-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b7896-123">Requirements</span></span>  
 <span data-ttu-id="b7896-124">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b7896-124">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7896-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7896-125">See Also</span></span>  
 [<span data-ttu-id="b7896-126">Interfaces de almacén de símbolos de diagnósticos</span><span class="sxs-lookup"><span data-stu-id="b7896-126">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
