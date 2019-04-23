---
title: ISymUnmanagedAsyncMethod::GetKickoffMethod (Método)
ms.date: 03/30/2017
ms.assetid: ba084444-9e68-4cde-9388-54b950670987
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4599d41336778db8ce8dcf3ac567e4e2cc8833e6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59174946"
---
# <a name="isymunmanagedasyncmethodgetkickoffmethod-method"></a><span data-ttu-id="e99bb-102">ISymUnmanagedAsyncMethod::GetKickoffMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="e99bb-102">ISymUnmanagedAsyncMethod::GetKickoffMethod Method</span></span>
<span data-ttu-id="e99bb-103">Consulte [DefineKickoffMethod (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="e99bb-103">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e99bb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e99bb-104">Syntax</span></span>  
  
```idl  
HRESULT GetKickoffMethod(    [out, retval] mdToken* kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e99bb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e99bb-105">Parameters</span></span>  
  
|<span data-ttu-id="e99bb-106">Parámetro</span><span class="sxs-lookup"><span data-stu-id="e99bb-106">Parameter</span></span>|<span data-ttu-id="e99bb-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e99bb-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="e99bb-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e99bb-108">Return Value</span></span>  
 <span data-ttu-id="e99bb-109">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="e99bb-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e99bb-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e99bb-110">Requirements</span></span>  
 <span data-ttu-id="e99bb-111">**Encabezado**: CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e99bb-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e99bb-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e99bb-112">See also</span></span>

- [<span data-ttu-id="e99bb-113">ISymUnmanagedAsyncMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e99bb-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
