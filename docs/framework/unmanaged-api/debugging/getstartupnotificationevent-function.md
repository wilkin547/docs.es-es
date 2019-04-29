---
title: GetStartupNotificationEvent (Función)
ms.date: 03/30/2017
api_name:
- GetStartupNotificationEvent
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- GetStartupNotificationEvent
helpviewer_keywords:
- GetStartupNotificationEvent function
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: c94b1b61-045a-4695-bacd-0f18c5acc246
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8ed1db49be78d7d16648a9ef9735e79ef1b3ab98
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698205"
---
# <a name="getstartupnotificationevent-function"></a><span data-ttu-id="93538-102">GetStartupNotificationEvent (Función)</span><span class="sxs-lookup"><span data-stu-id="93538-102">GetStartupNotificationEvent Function</span></span>
<span data-ttu-id="93538-103">Crea o abre un identificador de evento al que apuntará cualquier Common Language Runtime (CLR) que se cargue en el proceso de destino especificado.</span><span class="sxs-lookup"><span data-stu-id="93538-103">Creates or opens an event handle that will be signaled upon by any common language runtime (CLR) that is loading in the specified target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93538-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="93538-104">Syntax</span></span>  
  
```  
HRESULT GetStartupNotificationEvent  
    (  
    [in]  DWORD     debuggeePID,  
    [out]  HANDLE*  phStartupEvent  
    );  
```  
  
## <a name="parameters"></a><span data-ttu-id="93538-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="93538-105">Parameters</span></span>  
 `debuggeePID`  
 <span data-ttu-id="93538-106">[in] Identificador de proceso del proceso de destino desde el que se reciben las notificaciones de inicio del CLR.</span><span class="sxs-lookup"><span data-stu-id="93538-106">[in] Process identifier of the target process from which to receive CLR startup notifications.</span></span>  
  
 `phStartupEvent`  
 <span data-ttu-id="93538-107">[out] Puntero a un identificador que señalará un CLR en el inicio.</span><span class="sxs-lookup"><span data-stu-id="93538-107">[out] A pointer to a handle that will be signaled by a CLR on startup.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="93538-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="93538-108">Return Value</span></span>  
 <span data-ttu-id="93538-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="93538-109">S_OK</span></span>  
 <span data-ttu-id="93538-110">El identificador del evento de notificación de inicio se obtuvo correctamente.</span><span class="sxs-lookup"><span data-stu-id="93538-110">Successfully obtained the handle to the startup notification event.</span></span>  
  
 <span data-ttu-id="93538-111">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="93538-111">E_INVALIDARG</span></span>  
 <span data-ttu-id="93538-112">`phStartupEvent` es nulo o `debuggeePID` no hace referencia a un proceso actualmente en ejecución.</span><span class="sxs-lookup"><span data-stu-id="93538-112">`phStartupEvent` is null or `debuggeePID` does not refer to a process that is currently running.</span></span>  
  
 <span data-ttu-id="93538-113">E_FAIL (u otros códigos devueltos de E_)</span><span class="sxs-lookup"><span data-stu-id="93538-113">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="93538-114">No se puede obtener el identificador del evento de notificación de inicio.</span><span class="sxs-lookup"><span data-stu-id="93538-114">Unable to obtain the handle to the startup notification event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93538-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="93538-115">Remarks</span></span>  
 <span data-ttu-id="93538-116">En el sistema operativo Windows, `debuggeePID` se asigna a un identificador de procesos del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="93538-116">On the Windows operating system, `debuggeePID` maps to an OS process identifier.</span></span>  
  
 <span data-ttu-id="93538-117">El evento se señala antes de que el CLR que lo señaló ejecute ningún código administrado.</span><span class="sxs-lookup"><span data-stu-id="93538-117">The event is signaled before any managed code is executed by the CLR that signaled the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93538-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="93538-118">Requirements</span></span>  
 <span data-ttu-id="93538-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93538-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93538-120">**Encabezado:** dbgshim.h</span><span class="sxs-lookup"><span data-stu-id="93538-120">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="93538-121">**Biblioteca:** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="93538-121">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="93538-122">**Versiones de .NET framework:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="93538-122">**.NET Framework Versions:** 3.5 SP1</span></span>
