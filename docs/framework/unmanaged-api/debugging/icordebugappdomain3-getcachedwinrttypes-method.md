---
description: 'Más información sobre: ICorDebugAppDomain3:: Getcachedwinrttypes ((método)'
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
ms.openlocfilehash: 813fb6c05d5e1e5f119424c6e983b86b3ff5889d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772242"
---
# <a name="icordebugappdomain3getcachedwinrttypes-method"></a><span data-ttu-id="ef8e0-103">ICorDebugAppDomain3::GetCachedWinRTTypes (Método)</span><span class="sxs-lookup"><span data-stu-id="ef8e0-103">ICorDebugAppDomain3::GetCachedWinRTTypes Method</span></span>

<span data-ttu-id="ef8e0-104">Obtiene un enumerador para todos los tipos de Windows Runtime almacenados en caché.</span><span class="sxs-lookup"><span data-stu-id="ef8e0-104">Gets an enumerator for all cached Windows Runtime types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef8e0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ef8e0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedWinRTTypes (
    [out] ICorDebugGuidToTypeEnum **ppGuidToTypeEnum)  
;  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef8e0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ef8e0-106">Parameters</span></span>  

 `ppGuidToTypeEnum`  
 <span data-ttu-id="ef8e0-107">enuncia Un puntero a un objeto de interfaz [icordebugguidtotypeenum (](icordebugguidtotypeenum-interface.md) que puede enumerar las representaciones administradas de Windows Runtime tipos cargados actualmente en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="ef8e0-107">[out] A pointer to an [ICorDebugGuidToTypeEnum](icordebugguidtotypeenum-interface.md) interface object that can enumerate the managed representations of Windows Runtime types currently loaded in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef8e0-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ef8e0-108">Requirements</span></span>  

 <span data-ttu-id="ef8e0-109">**Plataformas:** Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="ef8e0-109">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="ef8e0-110">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ef8e0-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ef8e0-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef8e0-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef8e0-112">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef8e0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef8e0-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef8e0-113">See also</span></span>

- [<span data-ttu-id="ef8e0-114">ICorDebugAppDomain3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ef8e0-114">ICorDebugAppDomain3 Interface</span></span>](icordebugappdomain3-interface.md)
