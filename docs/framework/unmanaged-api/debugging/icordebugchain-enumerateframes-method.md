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
ms.openlocfilehash: c8a62d8b4a4db0f36d991c32dbfc5bad68780f1b
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894693"
---
# <a name="icordebugchainenumerateframes-method"></a><span data-ttu-id="ca9cd-102">ICorDebugChain::EnumerateFrames (Método)</span><span class="sxs-lookup"><span data-stu-id="ca9cd-102">ICorDebugChain::EnumerateFrames Method</span></span>
<span data-ttu-id="ca9cd-103">Obtiene un enumerador que contiene todos los marcos de pila administrados de la cadena, empezando por el fotograma más reciente.</span><span class="sxs-lookup"><span data-stu-id="ca9cd-103">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca9cd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ca9cd-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca9cd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ca9cd-105">Parameters</span></span>  
 `ppFrames`  
 <span data-ttu-id="ca9cd-106">enuncia Puntero a la dirección de un objeto ICorDebugFrameEnum (que es el enumerador de los marcos de pila.</span><span class="sxs-lookup"><span data-stu-id="ca9cd-106">[out] A pointer to the address of an ICorDebugFrameEnum object that is the enumerator for the stack frames.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca9cd-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ca9cd-107">Remarks</span></span>  
 <span data-ttu-id="ca9cd-108">La cadena representa la pila de llamadas física del subproceso.</span><span class="sxs-lookup"><span data-stu-id="ca9cd-108">The chain represents the physical call stack for the thread.</span></span>  
  
 <span data-ttu-id="ca9cd-109">Solo `EnumerateFrames` se debe llamar al método para las cadenas administradas.</span><span class="sxs-lookup"><span data-stu-id="ca9cd-109">The `EnumerateFrames` method should be called only for managed chains.</span></span> <span data-ttu-id="ca9cd-110">La API de depuración no proporciona métodos para obtener fotogramas contenidos en cadenas no administradas.</span><span class="sxs-lookup"><span data-stu-id="ca9cd-110">The debugging API does not provide methods for obtaining frames contained in unmanaged chains.</span></span> <span data-ttu-id="ca9cd-111">El depurador debe utilizar otros medios para obtener esta información.</span><span class="sxs-lookup"><span data-stu-id="ca9cd-111">The debugger must use other means to obtain this information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca9cd-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ca9cd-112">Requirements</span></span>  
 <span data-ttu-id="ca9cd-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca9cd-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca9cd-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ca9cd-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ca9cd-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca9cd-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca9cd-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca9cd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
