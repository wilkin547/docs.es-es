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
ms.openlocfilehash: 5e0df443e691292817ff37900fbc87204a8325ab
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684504"
---
# <a name="icordebugappdomain3getcachedwinrttypes-method"></a><span data-ttu-id="cd998-102">ICorDebugAppDomain3::GetCachedWinRTTypes (Método)</span><span class="sxs-lookup"><span data-stu-id="cd998-102">ICorDebugAppDomain3::GetCachedWinRTTypes Method</span></span>

<span data-ttu-id="cd998-103">Obtiene un enumerador para todos los tipos de Windows Runtime almacenados en caché.</span><span class="sxs-lookup"><span data-stu-id="cd998-103">Gets an enumerator for all cached Windows Runtime types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd998-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cd998-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedWinRTTypes (
    [out] ICorDebugGuidToTypeEnum **ppGuidToTypeEnum)  
;  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd998-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cd998-105">Parameters</span></span>  

 `ppGuidToTypeEnum`  
 <span data-ttu-id="cd998-106">enuncia Un puntero a un objeto de interfaz [icordebugguidtotypeenum (](icordebugguidtotypeenum-interface.md) que puede enumerar las representaciones administradas de Windows Runtime tipos cargados actualmente en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="cd998-106">[out] A pointer to an [ICorDebugGuidToTypeEnum](icordebugguidtotypeenum-interface.md) interface object that can enumerate the managed representations of Windows Runtime types currently loaded in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd998-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cd998-107">Requirements</span></span>  

 <span data-ttu-id="cd998-108">**Plataformas:** Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="cd998-108">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="cd998-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd998-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd998-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd998-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd998-111">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd998-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd998-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cd998-112">See also</span></span>

- [<span data-ttu-id="cd998-113">ICorDebugAppDomain3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cd998-113">ICorDebugAppDomain3 Interface</span></span>](icordebugappdomain3-interface.md)
