---
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
ms.openlocfilehash: ae6d81e6fdab0f8e3346d8a08a3b5ebc329a542a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730154"
---
# <a name="icordebugchainenumerateframes-method"></a><span data-ttu-id="60f32-102">ICorDebugChain::EnumerateFrames (Método)</span><span class="sxs-lookup"><span data-stu-id="60f32-102">ICorDebugChain::EnumerateFrames Method</span></span>

<span data-ttu-id="60f32-103">Obtiene un enumerador que contiene todos los marcos de pila administrados de la cadena, empezando por el fotograma más reciente.</span><span class="sxs-lookup"><span data-stu-id="60f32-103">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60f32-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="60f32-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60f32-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="60f32-105">Parameters</span></span>  

 `ppFrames`  
 <span data-ttu-id="60f32-106">enuncia Puntero a la dirección de un objeto ICorDebugFrameEnum (que es el enumerador de los marcos de pila.</span><span class="sxs-lookup"><span data-stu-id="60f32-106">[out] A pointer to the address of an ICorDebugFrameEnum object that is the enumerator for the stack frames.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60f32-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="60f32-107">Remarks</span></span>  

 <span data-ttu-id="60f32-108">La cadena representa la pila de llamadas física del subproceso.</span><span class="sxs-lookup"><span data-stu-id="60f32-108">The chain represents the physical call stack for the thread.</span></span>  
  
 <span data-ttu-id="60f32-109">`EnumerateFrames`Solo se debe llamar al método para las cadenas administradas.</span><span class="sxs-lookup"><span data-stu-id="60f32-109">The `EnumerateFrames` method should be called only for managed chains.</span></span> <span data-ttu-id="60f32-110">La API de depuración no proporciona métodos para obtener fotogramas contenidos en cadenas no administradas.</span><span class="sxs-lookup"><span data-stu-id="60f32-110">The debugging API does not provide methods for obtaining frames contained in unmanaged chains.</span></span> <span data-ttu-id="60f32-111">El depurador debe utilizar otros medios para obtener esta información.</span><span class="sxs-lookup"><span data-stu-id="60f32-111">The debugger must use other means to obtain this information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60f32-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="60f32-112">Requirements</span></span>  

 <span data-ttu-id="60f32-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60f32-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60f32-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="60f32-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="60f32-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60f32-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60f32-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60f32-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
