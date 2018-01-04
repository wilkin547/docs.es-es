---
title: "puntero a la función FExecuteInAppDomainCallback"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FExecuteInAppDomainCallback
api_location: mscoree.dll
api_type: COM
f1_keywords: FExecuteInAppDomainCallback
helpviewer_keywords: FExecuteInAppDomainCallback function pointer [.NET Framework hosting]
ms.assetid: 2709f18f-3eee-497f-bc33-3ab7a485599b
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9852abbf2f69dda5c4c3b06f48adbd1bc33f5a1e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="fexecuteinappdomaincallback-function-pointer"></a><span data-ttu-id="8f73a-102">puntero a la función FExecuteInAppDomainCallback</span><span class="sxs-lookup"><span data-stu-id="8f73a-102">FExecuteInAppDomainCallback Function Pointer</span></span>
<span data-ttu-id="8f73a-103">Señala a una función que llama a common language runtime (CLR) para ejecutar código administrado.</span><span class="sxs-lookup"><span data-stu-id="8f73a-103">Points to a function that is called by the common language runtime (CLR) to execute managed code.</span></span>  
  
 <span data-ttu-id="8f73a-104">Este puntero de función está desusada en la [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f73a-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f73a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8f73a-105">Syntax</span></span>  
  
```  
typedef HRESULT (__stdcall *FExecuteInAppDomainCallback) (  
    [in] void  *cookie  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8f73a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8f73a-106">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="8f73a-107">[in] Un puntero a la memoria asignada por el llamador opaco que contiene el código administrado que se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="8f73a-107">[in] A pointer to opaque caller-allocated memory that contains the managed code to be executed.</span></span>  
  
 <span data-ttu-id="8f73a-108">La asignación y duración de esta memoria se controlan por el llamador (es decir, el CLR).</span><span class="sxs-lookup"><span data-stu-id="8f73a-108">The allocation and lifetime of this memory are controlled by the caller (that is, the CLR).</span></span> <span data-ttu-id="8f73a-109">Esto no es memoria del montón administrado de CLR.</span><span class="sxs-lookup"><span data-stu-id="8f73a-109">This is not CLR managed-heap memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f73a-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8f73a-110">Requirements</span></span>  
 <span data-ttu-id="8f73a-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f73a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f73a-112">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8f73a-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8f73a-113">**Biblioteca:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="8f73a-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="8f73a-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f73a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f73a-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f73a-115">See Also</span></span>  
 [<span data-ttu-id="8f73a-116">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="8f73a-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
