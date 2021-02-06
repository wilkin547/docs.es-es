---
description: 'Más información acerca de: ICorDebugThread:: Getactivechain ((método)'
title: ICorDebugThread::GetActiveChain (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveChain
helpviewer_keywords:
- ICorDebugThread::GetActiveChain method [.NET Framework debugging]
- GetActiveChain method [.NET Framework debugging]
ms.assetid: f50de1f7-40ef-4949-b542-1d9a61f7bfef
topic_type:
- apiref
ms.openlocfilehash: d9aff80801fa72a227a84b3b5216e3ffa72b0e24
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99659288"
---
# <a name="icordebugthreadgetactivechain-method"></a><span data-ttu-id="1fdf0-103">ICorDebugThread::GetActiveChain (Método)</span><span class="sxs-lookup"><span data-stu-id="1fdf0-103">ICorDebugThread::GetActiveChain Method</span></span>

<span data-ttu-id="1fdf0-104">Obtiene un puntero de interfaz a la cadena de pila activa (más reciente) en este objeto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="1fdf0-104">Gets an interface pointer to the active (most recent) stack chain on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fdf0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1fdf0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveChain (  
    [out] ICorDebugChain **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1fdf0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1fdf0-106">Parameters</span></span>  

 `ppChain`  
 <span data-ttu-id="1fdf0-107">enuncia Puntero a la dirección de un objeto ICorDebugChain que representa la cadena de pila.</span><span class="sxs-lookup"><span data-stu-id="1fdf0-107">[out] A pointer to the address of an ICorDebugChain object that represents the stack chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1fdf0-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1fdf0-108">Remarks</span></span>  

 <span data-ttu-id="1fdf0-109">El `ppChain` parámetro es NULL si no hay ninguna cadena de pila activa actualmente.</span><span class="sxs-lookup"><span data-stu-id="1fdf0-109">The `ppChain` parameter is null if no stack chain is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fdf0-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1fdf0-110">Requirements</span></span>  

 <span data-ttu-id="1fdf0-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1fdf0-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fdf0-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1fdf0-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1fdf0-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1fdf0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1fdf0-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fdf0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
