---
title: ISymUnmanagedAsyncMethod::GetAsyncStepInfo (Método)
ms.date: 03/30/2017
ms.assetid: 3ef5b4b8-4ac7-4906-849b-f932c5e3db07
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f7c72d0766580f9aa3aa678aacd872b804172a8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940223"
---
# <a name="isymunmanagedasyncmethodgetasyncstepinfo-method"></a><span data-ttu-id="a7ae8-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="a7ae8-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfo Method</span></span>
<span data-ttu-id="a7ae8-103">Consulte [DefineAsyncStepInfo (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="a7ae8-103">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7ae8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a7ae8-104">Syntax</span></span>  
  
```idl  
HRESULT GetAsyncStepInfo(    [in] ULONG32 cStepInfo,    [out] ULONG32 *pcStepInfo,    [in, size_is(cStepInfo)] ULONG32 yieldOffsets[],    [in, size_is(cStepInfo)] ULONG32 breakpointOffset[],    [in, size_is(cStepInfo)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7ae8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a7ae8-105">Parameters</span></span>  
  
|<span data-ttu-id="a7ae8-106">Parámetro</span><span class="sxs-lookup"><span data-stu-id="a7ae8-106">Parameter</span></span>|<span data-ttu-id="a7ae8-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a7ae8-107">Description</span></span>|  
|---------------|-----------------|  
|`cStepInfo`||  
|`pcStepInfo`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="a7ae8-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a7ae8-108">Return Value</span></span>  
 <span data-ttu-id="a7ae8-109">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="a7ae8-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7ae8-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a7ae8-110">Requirements</span></span>  
 <span data-ttu-id="a7ae8-111">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a7ae8-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7ae8-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7ae8-112">See also</span></span>

- [<span data-ttu-id="a7ae8-113">ISymUnmanagedAsyncMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a7ae8-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
