---
title: ISymUnmanagedAsyncMethod::GetAsyncStepInfo (Método)
ms.date: 03/30/2017
ms.assetid: 3ef5b4b8-4ac7-4906-849b-f932c5e3db07
ms.openlocfilehash: f9392dae4119e59b4eb0fdb87e2b334b32b77109
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707261"
---
# <a name="isymunmanagedasyncmethodgetasyncstepinfo-method"></a><span data-ttu-id="8cf1e-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="8cf1e-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfo Method</span></span>

<span data-ttu-id="8cf1e-103">Consulte [método defineasyncstepinfo (](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="8cf1e-103">See [DefineAsyncStepInfo Method](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cf1e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8cf1e-104">Syntax</span></span>  
  
```idl  
HRESULT GetAsyncStepInfo(    [in] ULONG32 cStepInfo,    [out] ULONG32 *pcStepInfo,    [in, size_is(cStepInfo)] ULONG32 yieldOffsets[],    [in, size_is(cStepInfo)] ULONG32 breakpointOffset[],    [in, size_is(cStepInfo)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8cf1e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8cf1e-105">Parameters</span></span>  
  
|<span data-ttu-id="8cf1e-106">Parámetro</span><span class="sxs-lookup"><span data-stu-id="8cf1e-106">Parameter</span></span>|<span data-ttu-id="8cf1e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8cf1e-107">Description</span></span>|  
|---------------|-----------------|  
|`cStepInfo`||  
|`pcStepInfo`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="8cf1e-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8cf1e-108">Return Value</span></span>  

 <span data-ttu-id="8cf1e-109">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="8cf1e-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cf1e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8cf1e-110">Requirements</span></span>  

 <span data-ttu-id="8cf1e-111">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="8cf1e-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cf1e-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8cf1e-112">See also</span></span>

- [<span data-ttu-id="8cf1e-113">ISymUnmanagedAsyncMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8cf1e-113">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)
