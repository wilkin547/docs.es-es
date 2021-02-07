---
description: 'Más información sobre: ISymUnmanagedAsyncMethod:: Getasyncstepinfo ((método)'
title: ISymUnmanagedAsyncMethod::GetAsyncStepInfo (Método)
ms.date: 03/30/2017
ms.assetid: 3ef5b4b8-4ac7-4906-849b-f932c5e3db07
ms.openlocfilehash: dc255323f103b3422b927b0489402b24767dcd92
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737849"
---
# <a name="isymunmanagedasyncmethodgetasyncstepinfo-method"></a><span data-ttu-id="6e176-103">ISymUnmanagedAsyncMethod::GetAsyncStepInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="6e176-103">ISymUnmanagedAsyncMethod::GetAsyncStepInfo Method</span></span>

<span data-ttu-id="6e176-104">Consulte [método defineasyncstepinfo (](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="6e176-104">See [DefineAsyncStepInfo Method](isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e176-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6e176-105">Syntax</span></span>  
  
```idl  
HRESULT GetAsyncStepInfo(    [in] ULONG32 cStepInfo,    [out] ULONG32 *pcStepInfo,    [in, size_is(cStepInfo)] ULONG32 yieldOffsets[],    [in, size_is(cStepInfo)] ULONG32 breakpointOffset[],    [in, size_is(cStepInfo)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e176-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6e176-106">Parameters</span></span>  
  
|<span data-ttu-id="6e176-107">Parámetro</span><span class="sxs-lookup"><span data-stu-id="6e176-107">Parameter</span></span>|<span data-ttu-id="6e176-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="6e176-108">Description</span></span>|  
|---------------|-----------------|  
|`cStepInfo`||  
|`pcStepInfo`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="6e176-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6e176-109">Return Value</span></span>  

 <span data-ttu-id="6e176-110">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="6e176-110">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e176-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6e176-111">Requirements</span></span>  

 <span data-ttu-id="6e176-112">**Encabezado:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="6e176-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e176-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="6e176-113">See also</span></span>

- [<span data-ttu-id="6e176-114">ISymUnmanagedAsyncMethod (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6e176-114">ISymUnmanagedAsyncMethod Interface</span></span>](isymunmanagedasyncmethod-interface.md)
