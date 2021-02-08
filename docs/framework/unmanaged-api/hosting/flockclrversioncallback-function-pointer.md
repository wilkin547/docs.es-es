---
description: 'Más información sobre: puntero de función FLockClrVersionCallback'
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
ms.openlocfilehash: 3506cd30ab2a9e5a06b03f5010c9870280a38378
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785385"
---
# <a name="flockclrversioncallback-function-pointer"></a><span data-ttu-id="4124b-103">puntero a la función FLockClrVersionCallback</span><span class="sxs-lookup"><span data-stu-id="4124b-103">FLockClrVersionCallback Function Pointer</span></span>

<span data-ttu-id="4124b-104">Apunta a una función a la que llama el Common Language Runtime (CLR) para indicar que la inicialización se ha iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="4124b-104">Points to a function that the common language runtime (CLR) calls to indicate that initialization has either started or completed.</span></span>  
  
 <span data-ttu-id="4124b-105">Este puntero de función ha quedado en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="4124b-105">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4124b-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4124b-106">Syntax</span></span>  
  
```cpp  
typedef HRESULT (__stdcall *FLockClrVersionCallback) ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="4124b-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4124b-107">Remarks</span></span>  

 <span data-ttu-id="4124b-108">Esta función se implementa mediante el host.</span><span class="sxs-lookup"><span data-stu-id="4124b-108">This function is implemented by the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4124b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4124b-109">Requirements</span></span>  

 <span data-ttu-id="4124b-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4124b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4124b-111">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4124b-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4124b-112">**Biblioteca:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="4124b-112">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="4124b-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4124b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4124b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="4124b-114">See also</span></span>

- [<span data-ttu-id="4124b-115">LockClrVersion (Función)</span><span class="sxs-lookup"><span data-stu-id="4124b-115">LockClrVersion Function</span></span>](lockclrversion-function.md)
- [<span data-ttu-id="4124b-116">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="4124b-116">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
