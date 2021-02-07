---
description: 'Más información sobre: ICorDebugFrameEnum (:: Next (método)'
title: ICorDebugFrameEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFrameEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrameEnum::Next
helpviewer_keywords:
- ICorDebugFrameEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugFrameEnum interface [.NET Framework debugging]
ms.assetid: 0bc96acb-6179-4328-a447-cda562ce9e98
topic_type:
- apiref
ms.openlocfilehash: 67b7dd0282c07358f942990f8915150d6449fd32
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692672"
---
# <a name="icordebugframeenumnext-method"></a><span data-ttu-id="74406-103">ICorDebugFrameEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="74406-103">ICorDebugFrameEnum::Next Method</span></span>

<span data-ttu-id="74406-104">Obtiene el número especificado de instancias de ICorDebugFrame, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="74406-104">Gets the specified number of ICorDebugFrame instances, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74406-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74406-105">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugFrame *frames[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74406-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="74406-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="74406-107">de El número de `ICorDebugFrame` instancias que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="74406-107">[in] The number of `ICorDebugFrame` instances to be retrieved.</span></span>  
  
 `frames`  
 <span data-ttu-id="74406-108">enuncia Matriz de punteros, cada uno de los cuales señala a un `ICorDebugFrame` objeto.</span><span class="sxs-lookup"><span data-stu-id="74406-108">[out] An array of pointers, each of which points to an `ICorDebugFrame` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="74406-109">enuncia Puntero al número de `ICorDebugFrame` instancias devueltas realmente.</span><span class="sxs-lookup"><span data-stu-id="74406-109">[out] A pointer to the number of `ICorDebugFrame` instances actually returned.</span></span> <span data-ttu-id="74406-110">Este valor puede ser null si `celt` es uno.</span><span class="sxs-lookup"><span data-stu-id="74406-110">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74406-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="74406-111">Requirements</span></span>  

 <span data-ttu-id="74406-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74406-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74406-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="74406-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="74406-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74406-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74406-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74406-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
