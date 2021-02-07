---
description: 'Más información sobre: ICorDebugChain:: EnumerateFrames ((método)'
title: ICorDebugChain::EnumerateFrames (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugChain.EnumerateFrames
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::EnumerateFrames method
helpviewer_keywords:
- EnumerateFrames method [.NET Framework debugging]
- ICorDebugChain::EnumerateFrames method [.NET Framework debugging]
ms.assetid: 9fcefa98-750d-4168-8915-8173a43accf2
topic_type:
- apiref
ms.openlocfilehash: 45bf69760eeccebada743d81e859a19e209b611a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711601"
---
# <a name="icordebugchainenumerateframes-method"></a><span data-ttu-id="e8142-103">ICorDebugChain::EnumerateFrames (Método)</span><span class="sxs-lookup"><span data-stu-id="e8142-103">ICorDebugChain::EnumerateFrames Method</span></span>

<span data-ttu-id="e8142-104">Obtiene un enumerador que contiene todos los marcos de pila administrados de la cadena, empezando por el fotograma más reciente.</span><span class="sxs-lookup"><span data-stu-id="e8142-104">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8142-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e8142-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8142-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e8142-106">Parameters</span></span>  

 `ppFrames`  
 <span data-ttu-id="e8142-107">enuncia Puntero a la dirección de un objeto ICorDebugFrameEnum (que es el enumerador de los marcos de pila.</span><span class="sxs-lookup"><span data-stu-id="e8142-107">[out] A pointer to the address of an ICorDebugFrameEnum object that is the enumerator for the stack frames.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8142-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e8142-108">Remarks</span></span>  

 <span data-ttu-id="e8142-109">La cadena representa la pila de llamadas física del subproceso.</span><span class="sxs-lookup"><span data-stu-id="e8142-109">The chain represents the physical call stack for the thread.</span></span>  
  
 <span data-ttu-id="e8142-110">`EnumerateFrames`Solo se debe llamar al método para las cadenas administradas.</span><span class="sxs-lookup"><span data-stu-id="e8142-110">The `EnumerateFrames` method should be called only for managed chains.</span></span> <span data-ttu-id="e8142-111">La API de depuración no proporciona métodos para obtener fotogramas contenidos en cadenas no administradas.</span><span class="sxs-lookup"><span data-stu-id="e8142-111">The debugging API does not provide methods for obtaining frames contained in unmanaged chains.</span></span> <span data-ttu-id="e8142-112">El depurador debe utilizar otros medios para obtener esta información.</span><span class="sxs-lookup"><span data-stu-id="e8142-112">The debugger must use other means to obtain this information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8142-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e8142-113">Requirements</span></span>  

 <span data-ttu-id="e8142-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8142-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8142-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e8142-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e8142-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8142-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8142-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8142-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
