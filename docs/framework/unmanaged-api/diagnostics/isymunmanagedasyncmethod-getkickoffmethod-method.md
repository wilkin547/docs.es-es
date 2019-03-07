---
title: ISymUnmanagedAsyncMethod::GetKickoffMethod (Método)
ms.date: 03/30/2017
ms.assetid: ba084444-9e68-4cde-9388-54b950670987
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 84aef2b26e008d1a3c6d95d7ec1e130ab0594a11
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484555"
---
# <a name="isymunmanagedasyncmethodgetkickoffmethod-method"></a><span data-ttu-id="964af-102">ISymUnmanagedAsyncMethod::GetKickoffMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="964af-102">ISymUnmanagedAsyncMethod::GetKickoffMethod Method</span></span>
<span data-ttu-id="964af-103">Consulte [DefineKickoffMethod (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="964af-103">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="964af-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="964af-104">Syntax</span></span>  
  
```idl  
HRESULT GetKickoffMethod(    [out, retval] mdToken* kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="964af-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="964af-105">Parameters</span></span>  
  
|<span data-ttu-id="964af-106">Parámetro</span><span class="sxs-lookup"><span data-stu-id="964af-106">Parameter</span></span>|<span data-ttu-id="964af-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="964af-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="964af-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="964af-108">Return Value</span></span>  
 <span data-ttu-id="964af-109">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="964af-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="964af-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="964af-110">Requirements</span></span>  
 <span data-ttu-id="964af-111">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="964af-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="964af-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="964af-112">See also</span></span>
- [<span data-ttu-id="964af-113">ISymUnmanagedAsyncMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="964af-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
