---
title: puntero a la función FLockClrVersionCallback
ms.date: 03/30/2017
api_name:
- FLockClrVersionCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FLockClrVersionCallback
helpviewer_keywords:
- FLockClrVersionCallback function pointer [.NET Framework hosting]
ms.assetid: 98a4762d-9ad2-45bd-9d03-39064a028b44
topic_type:
- apiref
ms.openlocfilehash: f1ad414c30788801e14a33e98a0893e2a0f58d0c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136513"
---
# <a name="flockclrversioncallback-function-pointer"></a><span data-ttu-id="163e5-102">puntero a la función FLockClrVersionCallback</span><span class="sxs-lookup"><span data-stu-id="163e5-102">FLockClrVersionCallback Function Pointer</span></span>
<span data-ttu-id="163e5-103">Apunta a una función a la que llama el Common Language Runtime (CLR) para indicar que la inicialización se ha iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="163e5-103">Points to a function that the common language runtime (CLR) calls to indicate that initialization has either started or completed.</span></span>  
  
 <span data-ttu-id="163e5-104">Este puntero de función ha quedado en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="163e5-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="163e5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="163e5-105">Syntax</span></span>  
  
```cpp  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="163e5-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="163e5-106">Remarks</span></span>  
 <span data-ttu-id="163e5-107">Esta función se implementa mediante el host.</span><span class="sxs-lookup"><span data-stu-id="163e5-107">This function is implemented by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="163e5-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="163e5-108">Requirements</span></span>  
 <span data-ttu-id="163e5-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="163e5-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="163e5-110">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="163e5-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="163e5-111">**Biblioteca:** MSCorWks. dll</span><span class="sxs-lookup"><span data-stu-id="163e5-111">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="163e5-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="163e5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="163e5-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="163e5-113">See also</span></span>

- [<span data-ttu-id="163e5-114">LockClrVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="163e5-114">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)
- [<span data-ttu-id="163e5-115">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="163e5-115">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
