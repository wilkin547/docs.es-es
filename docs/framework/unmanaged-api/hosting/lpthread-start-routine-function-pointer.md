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
ms.openlocfilehash: c6e0c02af93b9df726202f397bbb2afc306f3b3a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73090877"
---
# <a name="lpthread_start_routine-function-pointer"></a><span data-ttu-id="9ff97-102">puntero a la función LPTHREAD_START_ROUTINE</span><span class="sxs-lookup"><span data-stu-id="9ff97-102">LPTHREAD_START_ROUTINE Function Pointer</span></span>
<span data-ttu-id="9ff97-103">Apunta a una función que notifica al host que se ha iniciado la ejecución de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="9ff97-103">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 <span data-ttu-id="9ff97-104">Este puntero de función ha quedado en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="9ff97-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ff97-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9ff97-105">Syntax</span></span>  
  
```cpp  
typedef DWORD (__stdcall *LPTHREAD_START_ROUTINE) (  
    [in] LPVOID lpThreadParameter  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ff97-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9ff97-106">Parameters</span></span>  
 `lpThreadParameter`  
 <span data-ttu-id="9ff97-107">de Puntero al código que ha empezado a ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="9ff97-107">[in] A pointer to the code that has started executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ff97-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9ff97-108">Remarks</span></span>  
 <span data-ttu-id="9ff97-109">Función a la que `LPTHREAD_START_ROUTINE` puntos es una función de devolución de llamada y debe ser implementada por el escritor de la aplicación de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="9ff97-109">The function to which `LPTHREAD_START_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ff97-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9ff97-110">Requirements</span></span>  
 <span data-ttu-id="9ff97-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ff97-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ff97-112">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9ff97-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9ff97-113">**Biblioteca:** MSCorWks. dll</span><span class="sxs-lookup"><span data-stu-id="9ff97-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="9ff97-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ff97-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ff97-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ff97-115">See also</span></span>

- [<span data-ttu-id="9ff97-116">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="9ff97-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
