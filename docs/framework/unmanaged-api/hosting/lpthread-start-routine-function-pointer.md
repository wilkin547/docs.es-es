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
ms.openlocfilehash: c86b65e136869603f93253678108b2ffa9d388e1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730076"
---
# <a name="lpthread_start_routine-function-pointer"></a><span data-ttu-id="e3cbd-102">puntero a la función LPTHREAD_START_ROUTINE</span><span class="sxs-lookup"><span data-stu-id="e3cbd-102">LPTHREAD_START_ROUTINE Function Pointer</span></span>

<span data-ttu-id="e3cbd-103">Apunta a una función que notifica al host que se ha iniciado la ejecución de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="e3cbd-103">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 <span data-ttu-id="e3cbd-104">Este puntero de función ha quedado en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="e3cbd-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3cbd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e3cbd-105">Syntax</span></span>  
  
```cpp  
typedef DWORD (__stdcall *LPTHREAD_START_ROUTINE) (  
    [in] LPVOID lpThreadParameter  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3cbd-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e3cbd-106">Parameters</span></span>  

 `lpThreadParameter`  
 <span data-ttu-id="e3cbd-107">de Puntero al código que ha empezado a ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="e3cbd-107">[in] A pointer to the code that has started executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e3cbd-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e3cbd-108">Remarks</span></span>  

 <span data-ttu-id="e3cbd-109">La función a la que `LPTHREAD_START_ROUTINE` apunta es una función de devolución de llamada y debe ser implementada por el escritor de la aplicación de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="e3cbd-109">The function to which `LPTHREAD_START_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3cbd-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e3cbd-110">Requirements</span></span>  

 <span data-ttu-id="e3cbd-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3cbd-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3cbd-112">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e3cbd-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e3cbd-113">**Biblioteca:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="e3cbd-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="e3cbd-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3cbd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3cbd-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e3cbd-115">See also</span></span>

- [<span data-ttu-id="e3cbd-116">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="e3cbd-116">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
