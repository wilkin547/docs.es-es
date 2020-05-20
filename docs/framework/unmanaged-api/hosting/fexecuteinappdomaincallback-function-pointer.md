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
ms.openlocfilehash: 6fd7a19d9fc77b43bbceb1b5e5399a455429e700
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616158"
---
# <a name="fexecuteinappdomaincallback-function-pointer"></a><span data-ttu-id="d1f28-102">puntero a la función FExecuteInAppDomainCallback</span><span class="sxs-lookup"><span data-stu-id="d1f28-102">FExecuteInAppDomainCallback Function Pointer</span></span>
<span data-ttu-id="d1f28-103">Apunta a una función a la que llama el Common Language Runtime (CLR) para ejecutar código administrado.</span><span class="sxs-lookup"><span data-stu-id="d1f28-103">Points to a function that is called by the common language runtime (CLR) to execute managed code.</span></span>  
  
 <span data-ttu-id="d1f28-104">Este puntero de función ha quedado en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="d1f28-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1f28-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d1f28-105">Syntax</span></span>  
  
```cpp  
typedef HRESULT (__stdcall *FExecuteInAppDomainCallback) (  
    [in] void  *cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1f28-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d1f28-106">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="d1f28-107">de Puntero a la memoria opaca asignada por el llamador que contiene el código administrado que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="d1f28-107">[in] A pointer to opaque caller-allocated memory that contains the managed code to be executed.</span></span>  
  
 <span data-ttu-id="d1f28-108">El autor de la llamada (es decir, el CLR) controla la asignación y la duración de esta memoria.</span><span class="sxs-lookup"><span data-stu-id="d1f28-108">The allocation and lifetime of this memory are controlled by the caller (that is, the CLR).</span></span> <span data-ttu-id="d1f28-109">Esto no es la memoria del montón administrado de CLR.</span><span class="sxs-lookup"><span data-stu-id="d1f28-109">This is not CLR managed-heap memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1f28-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d1f28-110">Requirements</span></span>  
 <span data-ttu-id="d1f28-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1f28-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1f28-112">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d1f28-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d1f28-113">**Biblioteca:** MSCorWks. dll</span><span class="sxs-lookup"><span data-stu-id="d1f28-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="d1f28-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1f28-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1f28-115">Consulta también</span><span class="sxs-lookup"><span data-stu-id="d1f28-115">See also</span></span>

- [<span data-ttu-id="d1f28-116">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="d1f28-116">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
