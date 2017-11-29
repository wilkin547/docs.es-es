---
title: "ISymUnmanagedAsyncMethod::GetCatchHandlerILOffset (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: d5f88656-433d-447c-b21c-2a12bed2e72a
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4d04c34bdc1b61f81fa542dfb22de9a6998f9cc9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedasyncmethodgetcatchhandleriloffset-method"></a><span data-ttu-id="7874d-102">ISymUnmanagedAsyncMethod::GetCatchHandlerILOffset (Método)</span><span class="sxs-lookup"><span data-stu-id="7874d-102">ISymUnmanagedAsyncMethod::GetCatchHandlerILOffset Method</span></span>
<span data-ttu-id="7874d-103">Vea [DefineCatchHandlerILOffset (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span><span class="sxs-lookup"><span data-stu-id="7874d-103">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7874d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7874d-104">Syntax</span></span>  
  
```idl  
HRESULT GetCatchHandlerILOffset(    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7874d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7874d-105">Parameters</span></span>  
  
|<span data-ttu-id="7874d-106">Parámetro</span><span class="sxs-lookup"><span data-stu-id="7874d-106">Parameter</span></span>|<span data-ttu-id="7874d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="7874d-107">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="7874d-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7874d-108">Return Value</span></span>  
 <span data-ttu-id="7874d-109">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="7874d-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7874d-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7874d-110">Requirements</span></span>  
 <span data-ttu-id="7874d-111">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7874d-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7874d-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="7874d-112">See Also</span></span>  
 [<span data-ttu-id="7874d-113">ISymUnmanagedAsyncMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7874d-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
