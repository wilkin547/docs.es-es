---
title: "ISymUnmanagedAsyncMethod::GetAsyncStepInfoCount (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 32a4e084-09b2-4946-a4a7-19a1fed9f7cc
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6b2431662caa41c67746da7e21591c743896c161
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedasyncmethodgetasyncstepinfocount-method"></a><span data-ttu-id="d42ac-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfoCount (Método)</span><span class="sxs-lookup"><span data-stu-id="d42ac-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfoCount Method</span></span>
<span data-ttu-id="d42ac-103">Vea [DefineAsyncStepInfo (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="d42ac-103">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d42ac-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d42ac-104">Syntax</span></span>  
  
```idl  
HRESULT GetAsyncStepInfoCount(    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d42ac-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d42ac-105">Parameters</span></span>  
  
|<span data-ttu-id="d42ac-106">Parámetro</span><span class="sxs-lookup"><span data-stu-id="d42ac-106">Parameter</span></span>|<span data-ttu-id="d42ac-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d42ac-107">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="d42ac-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d42ac-108">Return Value</span></span>  
 <span data-ttu-id="d42ac-109">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="d42ac-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d42ac-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d42ac-110">Requirements</span></span>  
 <span data-ttu-id="d42ac-111">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d42ac-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d42ac-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="d42ac-112">See Also</span></span>  
 [<span data-ttu-id="d42ac-113">ISymUnmanagedAsyncMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d42ac-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
