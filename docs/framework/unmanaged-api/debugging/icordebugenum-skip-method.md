---
title: ICorDebugEnum::Skip (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.Skip
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::Skip
helpviewer_keywords:
- ICorDebugEnum::Skip method [.NET Framework debugging]
- Skip method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: e925d88a-67a5-4f76-88b8-09cedeed0232
topic_type:
- apiref
ms.openlocfilehash: 64d9db09b3e604247ab6a26cdca9eca22adbaace
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976309"
---
# <a name="icordebugenumskip-method"></a><span data-ttu-id="08c86-102">ICorDebugEnum::Skip (Método)</span><span class="sxs-lookup"><span data-stu-id="08c86-102">ICorDebugEnum::Skip Method</span></span>
<span data-ttu-id="08c86-103">Mueve el cursor hacia delante en la enumeración el número de elementos especificado.</span><span class="sxs-lookup"><span data-stu-id="08c86-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08c86-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="08c86-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08c86-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="08c86-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="08c86-106">de Número de elementos por los que se va a desplazar el cursor hacia delante.</span><span class="sxs-lookup"><span data-stu-id="08c86-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08c86-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="08c86-107">Requirements</span></span>  
 <span data-ttu-id="08c86-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08c86-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08c86-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="08c86-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08c86-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08c86-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08c86-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08c86-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08c86-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="08c86-112">See also</span></span>

- [<span data-ttu-id="08c86-113">Interfaz ICorDebugEnum</span><span class="sxs-lookup"><span data-stu-id="08c86-113">ICorDebugEnum Interface</span></span>](icordebugenum-interface1.md)
