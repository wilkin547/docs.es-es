---
title: "ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugAppDomain3.GetCachedWinRTTypesForIIDs
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs method, [.NET Framework debugging]
- GetCachedWinRTTypesForIIDs method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 23682ca0-1bcf-48e6-996e-69f7ba337682
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5a7ce44dcfc709b4fea1952471cf31f5f07d4d0e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a><span data-ttu-id="0eaa4-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs (Método)</span><span class="sxs-lookup"><span data-stu-id="0eaa4-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs Method</span></span>
<span data-ttu-id="0eaa4-103">Obtiene un enumerador para almacenado en memoria caché [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipos en un dominio de aplicación en función de sus identificadores de interfaz.</span><span class="sxs-lookup"><span data-stu-id="0eaa4-103">Gets an enumerator for cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types in an application domain based on their interface identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0eaa4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0eaa4-104">Syntax</span></span>  
  
```  
HRESULT GetCachedWinRTTypesForIIDs (   
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0eaa4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0eaa4-105">Parameters</span></span>  
 `cReqTypes`  
 <span data-ttu-id="0eaa4-106">[in] El número de tipos necesarios.</span><span class="sxs-lookup"><span data-stu-id="0eaa4-106">[in] The number of required types.</span></span>  
  
 `iidsToResolve`  
 <span data-ttu-id="0eaa4-107">[in] Un puntero a una matriz que contiene los identificadores de interfaz correspondientes a las representaciones administradas de la [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipos va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="0eaa4-107">[in] A pointer to an array that contains the interface identifiers corresponding to the managed representations of the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types to be retrieved.</span></span>  
  
 `ppTypesEnum`  
 <span data-ttu-id="0eaa4-108">[out] Un puntero a la dirección de un objeto de interfaz de "ICorDebugTypeEnum" que permite la enumeración de las almacenadas en caché administrada representaciones de la [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipos recuperar, en función de los identificadores de interfaz de `iidsToResolve`.</span><span class="sxs-lookup"><span data-stu-id="0eaa4-108">[out] A pointer to the address of an "ICorDebugTypeEnum" interface object that allows enumeration of the cached managed representations of the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types retrieved, based on the interface identifiers in `iidsToResolve`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0eaa4-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0eaa4-109">Remarks</span></span>  
 <span data-ttu-id="0eaa4-110">Si el método no se puede recuperar la información de un identificador de interfaz específica, la entrada correspondiente en la colección "ICorDebugTypeEnum" tendrá un tipo de `ELEMENT_TYPE_END` para errores causados por problemas de recuperación de datos, o `ELEMENT_TYPE_VOID` para la interfaz desconocida identificadores.</span><span class="sxs-lookup"><span data-stu-id="0eaa4-110">If the method fails to retrieve information for a specific interface identifier, the corresponding entry in the "ICorDebugTypeEnum" collection will have a type of `ELEMENT_TYPE_END` for errors due to data retrieval issues, or `ELEMENT_TYPE_VOID` for unknown interface identifiers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0eaa4-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0eaa4-111">Requirements</span></span>  
 <span data-ttu-id="0eaa4-112">**Plataformas:**[!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0eaa4-112">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="0eaa4-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0eaa4-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0eaa4-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0eaa4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0eaa4-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0eaa4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eaa4-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="0eaa4-116">See Also</span></span>  
 [<span data-ttu-id="0eaa4-117">ICorDebugAppDomain3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0eaa4-117">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
