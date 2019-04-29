---
title: puntero a la función LPTHREAD_START_ROUTINE
ms.date: 03/30/2017
api_name:
- LPTHREAD_START_ROUTINE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- LPTHREAD_START_ROUTINE
helpviewer_keywords:
- LPTHREAD_START_ROUTINE function pointer [.NET Framework hosting]
ms.assetid: 7b9b93b0-fe92-42ba-8693-701168a29dde
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 27d1837f9f9f11ad34140f50ec41aa6fe8a62160
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765250"
---
# <a name="lpthreadstartroutine-function-pointer"></a><span data-ttu-id="c3dbb-102">puntero a la función LPTHREAD_START_ROUTINE</span><span class="sxs-lookup"><span data-stu-id="c3dbb-102">LPTHREAD_START_ROUTINE Function Pointer</span></span>
<span data-ttu-id="c3dbb-103">Señala una función que notifica al host que un subproceso ha empezado a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="c3dbb-103">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 <span data-ttu-id="c3dbb-104">Este puntero de función ha quedado obsoleto en la [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3dbb-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3dbb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c3dbb-105">Syntax</span></span>  
  
```  
typedef DWORD (__stdcall *LPTHREAD_START_ROUTINE) (  
    [in] LPVOID lpThreadParameter  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3dbb-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c3dbb-106">Parameters</span></span>  
 `lpThreadParameter`  
 <span data-ttu-id="c3dbb-107">[in] Un puntero al código que ha iniciado la ejecución.</span><span class="sxs-lookup"><span data-stu-id="c3dbb-107">[in] A pointer to the code that has started executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3dbb-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c3dbb-108">Remarks</span></span>  
 <span data-ttu-id="c3dbb-109">La función a la que `LPTHREAD_START_ROUTINE` puntos es una función de devolución de llamada y debe ser implementada por el sistema de escritura de la aplicación de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="c3dbb-109">The function to which `LPTHREAD_START_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3dbb-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c3dbb-110">Requirements</span></span>  
 <span data-ttu-id="c3dbb-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3dbb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3dbb-112">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c3dbb-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c3dbb-113">**Biblioteca:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="c3dbb-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="c3dbb-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3dbb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3dbb-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3dbb-115">See also</span></span>

- [<span data-ttu-id="c3dbb-116">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="c3dbb-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
