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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 73a08e83d67c973294938a030b95b906aec6be6d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59126612"
---
# <a name="icordebugappdomain3getcachedwinrttypes-method"></a><span data-ttu-id="40a67-102">ICorDebugAppDomain3::GetCachedWinRTTypes (Método)</span><span class="sxs-lookup"><span data-stu-id="40a67-102">ICorDebugAppDomain3::GetCachedWinRTTypes Method</span></span>
<span data-ttu-id="40a67-103">Obtiene un enumerador para todos los almacena en caché [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipos.</span><span class="sxs-lookup"><span data-stu-id="40a67-103">Gets an enumerator for all cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40a67-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="40a67-104">Syntax</span></span>  
  
```  
HRESULT GetCachedWinRTTypes (   
    [out] ICorDebugGuidToTypeEnum **ppGuidToTypeEnum)  
;  
```  
  
## <a name="parameters"></a><span data-ttu-id="40a67-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="40a67-105">Parameters</span></span>  
 `ppGuidToTypeEnum`  
 <span data-ttu-id="40a67-106">[out] Un puntero a un [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md) objeto de interfaz que puede enumerar las representaciones administradas de [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipos cargados actualmente en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="40a67-106">[out] A pointer to an [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md) interface object that can enumerate the managed representations of [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types currently loaded in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40a67-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="40a67-107">Requirements</span></span>  
 <span data-ttu-id="40a67-108">**Plataformas:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40a67-108">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="40a67-109">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="40a67-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="40a67-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40a67-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40a67-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40a67-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40a67-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="40a67-112">See also</span></span>

- [<span data-ttu-id="40a67-113">ICorDebugAppDomain3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="40a67-113">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
