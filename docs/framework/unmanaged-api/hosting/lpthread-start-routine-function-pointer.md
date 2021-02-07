---
description: 'Más información acerca de: LPTHREAD_START_ROUTINE puntero a función'
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
ms.openlocfilehash: 9f79cffb0b5290031915b453353dd47cb3959970
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679815"
---
# <a name="lpthread_start_routine-function-pointer"></a><span data-ttu-id="4fe81-103">puntero a la función LPTHREAD_START_ROUTINE</span><span class="sxs-lookup"><span data-stu-id="4fe81-103">LPTHREAD_START_ROUTINE Function Pointer</span></span>

<span data-ttu-id="4fe81-104">Apunta a una función que notifica al host que se ha iniciado la ejecución de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="4fe81-104">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 <span data-ttu-id="4fe81-105">Este puntero de función ha quedado en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="4fe81-105">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4fe81-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4fe81-106">Syntax</span></span>  
  
```cpp  
typedef DWORD (__stdcall *LPTHREAD_START_ROUTINE) (  
    [in] LPVOID lpThreadParameter  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4fe81-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4fe81-107">Parameters</span></span>  

 `lpThreadParameter`  
 <span data-ttu-id="4fe81-108">de Puntero al código que ha empezado a ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="4fe81-108">[in] A pointer to the code that has started executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4fe81-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4fe81-109">Remarks</span></span>  

 <span data-ttu-id="4fe81-110">La función a la que `LPTHREAD_START_ROUTINE` apunta es una función de devolución de llamada y debe ser implementada por el escritor de la aplicación de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="4fe81-110">The function to which `LPTHREAD_START_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4fe81-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4fe81-111">Requirements</span></span>  

 <span data-ttu-id="4fe81-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4fe81-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4fe81-113">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4fe81-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4fe81-114">**Biblioteca:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="4fe81-114">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="4fe81-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4fe81-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fe81-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="4fe81-116">See also</span></span>

- [<span data-ttu-id="4fe81-117">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="4fe81-117">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
