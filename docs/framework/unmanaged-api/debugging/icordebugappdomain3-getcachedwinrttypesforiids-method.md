---
title: ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs (Método)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed1d7ad95b7c8474121994d0f54557c1c36cb531
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59095131"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a><span data-ttu-id="50b90-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs (Método)</span><span class="sxs-lookup"><span data-stu-id="50b90-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs Method</span></span>
<span data-ttu-id="50b90-103">Obtiene un enumerador para almacenar en caché [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipos en un dominio de aplicación en función de sus identificadores de interfaz.</span><span class="sxs-lookup"><span data-stu-id="50b90-103">Gets an enumerator for cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types in an application domain based on their interface identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50b90-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="50b90-104">Syntax</span></span>  
  
```  
HRESULT GetCachedWinRTTypesForIIDs (   
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50b90-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="50b90-105">Parameters</span></span>  
 `cReqTypes`  
 <span data-ttu-id="50b90-106">[in] El número de tipos necesarios.</span><span class="sxs-lookup"><span data-stu-id="50b90-106">[in] The number of required types.</span></span>  
  
 `iidsToResolve`  
 <span data-ttu-id="50b90-107">[in] Un puntero a una matriz que contiene los identificadores de interfaz correspondientes a las representaciones administradas de la [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipos van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="50b90-107">[in] A pointer to an array that contains the interface identifiers corresponding to the managed representations of the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types to be retrieved.</span></span>  
  
 `ppTypesEnum`  
 <span data-ttu-id="50b90-108">[out] Un puntero a la dirección de un objeto de interfaz "ICorDebugTypeEnum" que permite la enumeración de la caché administrada representaciones de la [!INCLUDE[wrt](../../../../includes/wrt-md.md)] recuperar tipos, en función de los identificadores de interfaz en `iidsToResolve`.</span><span class="sxs-lookup"><span data-stu-id="50b90-108">[out] A pointer to the address of an "ICorDebugTypeEnum" interface object that allows enumeration of the cached managed representations of the [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types retrieved, based on the interface identifiers in `iidsToResolve`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50b90-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="50b90-109">Remarks</span></span>  
 <span data-ttu-id="50b90-110">Si se produce un error en el método recuperar información para un identificador de interfaz específica, la entrada correspondiente en la colección "ICorDebugTypeEnum" tendrá un tipo de `ELEMENT_TYPE_END` errores debido a problemas de recuperación de datos, o `ELEMENT_TYPE_VOID` para la interfaz desconocida identificadores.</span><span class="sxs-lookup"><span data-stu-id="50b90-110">If the method fails to retrieve information for a specific interface identifier, the corresponding entry in the "ICorDebugTypeEnum" collection will have a type of `ELEMENT_TYPE_END` for errors due to data retrieval issues, or `ELEMENT_TYPE_VOID` for unknown interface identifiers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50b90-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="50b90-111">Requirements</span></span>  
 **<span data-ttu-id="50b90-112">Plataformas:</span><span class="sxs-lookup"><span data-stu-id="50b90-112">Platforms:</span></span>** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]  
  
 <span data-ttu-id="50b90-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="50b90-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50b90-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50b90-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="50b90-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="50b90-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="50b90-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="50b90-116">See also</span></span>

- [<span data-ttu-id="50b90-117">ICorDebugAppDomain3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="50b90-117">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
