---
title: ICorDebugAppDomain3::GetCachedWinRTTypes (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3.GetCachedWinRTTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypes
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypes method [.NET Framework debugging]
- GetCachedWinRTTypes method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 9afd0e04-a403-41e2-9528-a6dcbcdcbd4d
topic_type:
- apiref
ms.openlocfilehash: 89f45208550d49f214e763728ddc9eb1bfcd9800
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088973"
---
# <a name="icordebugappdomain3getcachedwinrttypes-method"></a><span data-ttu-id="1218f-102">ICorDebugAppDomain3::GetCachedWinRTTypes (Método)</span><span class="sxs-lookup"><span data-stu-id="1218f-102">ICorDebugAppDomain3::GetCachedWinRTTypes Method</span></span>
<span data-ttu-id="1218f-103">Obtiene un enumerador para todos los tipos de Windows Runtime almacenados en caché.</span><span class="sxs-lookup"><span data-stu-id="1218f-103">Gets an enumerator for all cached Windows Runtime types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1218f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1218f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedWinRTTypes (   
    [out] ICorDebugGuidToTypeEnum **ppGuidToTypeEnum)  
;  
```  
  
## <a name="parameters"></a><span data-ttu-id="1218f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1218f-105">Parameters</span></span>  
 `ppGuidToTypeEnum`  
 <span data-ttu-id="1218f-106">enuncia Un puntero a un objeto de interfaz [icordebugguidtotypeenum (](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md) que puede enumerar las representaciones administradas de Windows Runtime tipos cargados actualmente en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="1218f-106">[out] A pointer to an [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md) interface object that can enumerate the managed representations of Windows Runtime types currently loaded in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1218f-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1218f-107">Requirements</span></span>  
 <span data-ttu-id="1218f-108">**Plataformas:** Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="1218f-108">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="1218f-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1218f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1218f-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1218f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1218f-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1218f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1218f-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="1218f-112">See also</span></span>

- [<span data-ttu-id="1218f-113">ICorDebugAppDomain3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1218f-113">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
