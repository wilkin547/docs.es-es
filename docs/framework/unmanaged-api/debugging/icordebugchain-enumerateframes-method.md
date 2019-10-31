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
ms.openlocfilehash: 0b024d3396dfe1796fcb18afa122d4aee39c4ccc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132720"
---
# <a name="icordebugchainenumerateframes-method"></a><span data-ttu-id="ab40d-102">ICorDebugChain::EnumerateFrames (Método)</span><span class="sxs-lookup"><span data-stu-id="ab40d-102">ICorDebugChain::EnumerateFrames Method</span></span>
<span data-ttu-id="ab40d-103">Obtiene un enumerador que contiene todos los marcos de pila administrados de la cadena, empezando por el fotograma más reciente.</span><span class="sxs-lookup"><span data-stu-id="ab40d-103">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab40d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ab40d-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateFrames (  
    [out] ICorDebugFrameEnum **ppFrames  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab40d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ab40d-105">Parameters</span></span>  
 `ppFrames`  
 <span data-ttu-id="ab40d-106">enuncia Puntero a la dirección de un objeto ICorDebugFrameEnum (que es el enumerador de los marcos de pila.</span><span class="sxs-lookup"><span data-stu-id="ab40d-106">[out] A pointer to the address of an ICorDebugFrameEnum object that is the enumerator for the stack frames.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab40d-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ab40d-107">Remarks</span></span>  
 <span data-ttu-id="ab40d-108">La cadena representa la pila de llamadas física del subproceso.</span><span class="sxs-lookup"><span data-stu-id="ab40d-108">The chain represents the physical call stack for the thread.</span></span>  
  
 <span data-ttu-id="ab40d-109">Solo se debe llamar al método `EnumerateFrames` para las cadenas administradas.</span><span class="sxs-lookup"><span data-stu-id="ab40d-109">The `EnumerateFrames` method should be called only for managed chains.</span></span> <span data-ttu-id="ab40d-110">La API de depuración no proporciona métodos para obtener fotogramas contenidos en cadenas no administradas.</span><span class="sxs-lookup"><span data-stu-id="ab40d-110">The debugging API does not provide methods for obtaining frames contained in unmanaged chains.</span></span> <span data-ttu-id="ab40d-111">El depurador debe utilizar otros medios para obtener esta información.</span><span class="sxs-lookup"><span data-stu-id="ab40d-111">The debugger must use other means to obtain this information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab40d-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ab40d-112">Requirements</span></span>  
 <span data-ttu-id="ab40d-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab40d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab40d-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ab40d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ab40d-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab40d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab40d-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab40d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
