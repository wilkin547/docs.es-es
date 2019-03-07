---
title: puntero a la función FExecuteInAppDomainCallback
ms.date: 03/30/2017
api_name:
- FExecuteInAppDomainCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FExecuteInAppDomainCallback
helpviewer_keywords:
- FExecuteInAppDomainCallback function pointer [.NET Framework hosting]
ms.assetid: 2709f18f-3eee-497f-bc33-3ab7a485599b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 16608980505ffc03ef8ecc19cacddabaefaba6ca
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471750"
---
# <a name="fexecuteinappdomaincallback-function-pointer"></a><span data-ttu-id="2bc13-102">puntero a la función FExecuteInAppDomainCallback</span><span class="sxs-lookup"><span data-stu-id="2bc13-102">FExecuteInAppDomainCallback Function Pointer</span></span>
<span data-ttu-id="2bc13-103">Señala una función que se llama mediante common language runtime (CLR) para ejecutar código administrado.</span><span class="sxs-lookup"><span data-stu-id="2bc13-103">Points to a function that is called by the common language runtime (CLR) to execute managed code.</span></span>  
  
 <span data-ttu-id="2bc13-104">Este puntero de función ha quedado obsoleto en la [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2bc13-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bc13-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2bc13-105">Syntax</span></span>  
  
```  
typedef HRESULT (__stdcall *FExecuteInAppDomainCallback) (  
    [in] void  *cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bc13-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2bc13-106">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="2bc13-107">[in] Puntero a la memoria asignada por el llamador opaco que contiene el código administrado que se ejecutará.</span><span class="sxs-lookup"><span data-stu-id="2bc13-107">[in] A pointer to opaque caller-allocated memory that contains the managed code to be executed.</span></span>  
  
 <span data-ttu-id="2bc13-108">La asignación y duración de esta memoria se controlan por el llamador (es decir, el CLR).</span><span class="sxs-lookup"><span data-stu-id="2bc13-108">The allocation and lifetime of this memory are controlled by the caller (that is, the CLR).</span></span> <span data-ttu-id="2bc13-109">Esto no es memoria del montón administrado de CLR.</span><span class="sxs-lookup"><span data-stu-id="2bc13-109">This is not CLR managed-heap memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bc13-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2bc13-110">Requirements</span></span>  
 <span data-ttu-id="2bc13-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2bc13-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bc13-112">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2bc13-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2bc13-113">**Biblioteca:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="2bc13-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="2bc13-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bc13-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bc13-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="2bc13-115">See also</span></span>
- [<span data-ttu-id="2bc13-116">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="2bc13-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
