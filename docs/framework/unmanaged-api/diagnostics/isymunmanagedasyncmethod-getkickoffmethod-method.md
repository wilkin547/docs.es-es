---
title: ISymUnmanagedAsyncMethod::GetKickoffMethod (Método)
ms.date: 03/30/2017
ms.assetid: ba084444-9e68-4cde-9388-54b950670987
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e2f055dc19bf7f40036283102d8cc4549555b992
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424773"
---
# <a name="isymunmanagedasyncmethodgetkickoffmethod-method"></a><span data-ttu-id="ee200-102">ISymUnmanagedAsyncMethod::GetKickoffMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="ee200-102">ISymUnmanagedAsyncMethod::GetKickoffMethod Method</span></span>
<span data-ttu-id="ee200-103">Vea [DefineKickoffMethod (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="ee200-103">See [DefineKickoffMethod Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee200-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ee200-104">Syntax</span></span>  
  
```idl  
HRESULT GetKickoffMethod(    [out, retval] mdToken* kickoffMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ee200-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ee200-105">Parameters</span></span>  
  
|<span data-ttu-id="ee200-106">Parámetro</span><span class="sxs-lookup"><span data-stu-id="ee200-106">Parameter</span></span>|<span data-ttu-id="ee200-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ee200-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="ee200-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ee200-108">Return Value</span></span>  
 <span data-ttu-id="ee200-109">Devuelve `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="ee200-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee200-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ee200-110">Requirements</span></span>  
 <span data-ttu-id="ee200-111">**Encabezado:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ee200-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee200-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee200-112">See Also</span></span>  
 [<span data-ttu-id="ee200-113">ISymUnmanagedAsyncMethod (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ee200-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
