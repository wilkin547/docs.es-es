---
description: 'Más información sobre: puntero de función FExecuteInAppDomainCallback'
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
ms.openlocfilehash: 97c7fe14a3eafd6f4626d8729be3b45ad5502f1a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785402"
---
# <a name="fexecuteinappdomaincallback-function-pointer"></a><span data-ttu-id="42111-103">puntero a la función FExecuteInAppDomainCallback</span><span class="sxs-lookup"><span data-stu-id="42111-103">FExecuteInAppDomainCallback Function Pointer</span></span>

<span data-ttu-id="42111-104">Apunta a una función a la que llama el Common Language Runtime (CLR) para ejecutar código administrado.</span><span class="sxs-lookup"><span data-stu-id="42111-104">Points to a function that is called by the common language runtime (CLR) to execute managed code.</span></span>  
  
 <span data-ttu-id="42111-105">Este puntero de función ha quedado en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="42111-105">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42111-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42111-106">Syntax</span></span>  
  
```cpp  
typedef HRESULT (__stdcall *FExecuteInAppDomainCallback) (  
    [in] void  *cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42111-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="42111-107">Parameters</span></span>  

 `cookie`  
 <span data-ttu-id="42111-108">de Puntero a la memoria opaca asignada por el llamador que contiene el código administrado que se va a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="42111-108">[in] A pointer to opaque caller-allocated memory that contains the managed code to be executed.</span></span>  
  
 <span data-ttu-id="42111-109">El autor de la llamada (es decir, el CLR) controla la asignación y la duración de esta memoria.</span><span class="sxs-lookup"><span data-stu-id="42111-109">The allocation and lifetime of this memory are controlled by the caller (that is, the CLR).</span></span> <span data-ttu-id="42111-110">Esto no es la memoria del montón administrado de CLR.</span><span class="sxs-lookup"><span data-stu-id="42111-110">This is not CLR managed-heap memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42111-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42111-111">Requirements</span></span>  

 <span data-ttu-id="42111-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42111-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42111-113">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="42111-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="42111-114">**Biblioteca:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="42111-114">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="42111-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42111-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42111-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="42111-116">See also</span></span>

- [<span data-ttu-id="42111-117">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="42111-117">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
