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
ms.openlocfilehash: 6ef8d1c47275d3cbd69c1516b788b950f8535513
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737720"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a><span data-ttu-id="50ac6-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs (Método)</span><span class="sxs-lookup"><span data-stu-id="50ac6-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs Method</span></span>
<span data-ttu-id="50ac6-103">Obtiene un enumerador para los tipos en tiempo de ejecución de Windows almacenado en caché en un dominio de aplicación en función de sus identificadores de interfaz.</span><span class="sxs-lookup"><span data-stu-id="50ac6-103">Gets an enumerator for cached Windows Runtime types in an application domain based on their interface identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50ac6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="50ac6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedWinRTTypesForIIDs (   
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50ac6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="50ac6-105">Parameters</span></span>  
 `cReqTypes`  
 <span data-ttu-id="50ac6-106">[in] El número de tipos necesarios.</span><span class="sxs-lookup"><span data-stu-id="50ac6-106">[in] The number of required types.</span></span>  
  
 `iidsToResolve`  
 <span data-ttu-id="50ac6-107">[in] Un puntero a una matriz que contiene los identificadores de interfaz correspondientes a las representaciones administradas de los tipos de Windows en tiempo de ejecución, van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="50ac6-107">[in] A pointer to an array that contains the interface identifiers corresponding to the managed representations of the Windows Runtime types to be retrieved.</span></span>  
  
 `ppTypesEnum`  
 <span data-ttu-id="50ac6-108">[out] Recupera un puntero a la dirección de un objeto de interfaz "ICorDebugTypeEnum" que permite la enumeración de las representaciones administradas en caché de los tipos en tiempo de ejecución de Windows, en función de los identificadores de interfaz en `iidsToResolve`.</span><span class="sxs-lookup"><span data-stu-id="50ac6-108">[out] A pointer to the address of an "ICorDebugTypeEnum" interface object that allows enumeration of the cached managed representations of the Windows Runtime types retrieved, based on the interface identifiers in `iidsToResolve`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50ac6-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="50ac6-109">Remarks</span></span>  
 <span data-ttu-id="50ac6-110">Si se produce un error en el método recuperar información para un identificador de interfaz específica, la entrada correspondiente en la colección "ICorDebugTypeEnum" tendrá un tipo de `ELEMENT_TYPE_END` errores debido a problemas de recuperación de datos, o `ELEMENT_TYPE_VOID` para la interfaz desconocida identificadores.</span><span class="sxs-lookup"><span data-stu-id="50ac6-110">If the method fails to retrieve information for a specific interface identifier, the corresponding entry in the "ICorDebugTypeEnum" collection will have a type of `ELEMENT_TYPE_END` for errors due to data retrieval issues, or `ELEMENT_TYPE_VOID` for unknown interface identifiers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50ac6-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="50ac6-111">Requirements</span></span>  
 <span data-ttu-id="50ac6-112">**Plataformas:** Windows en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="50ac6-112">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="50ac6-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="50ac6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50ac6-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50ac6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50ac6-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50ac6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50ac6-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="50ac6-116">See also</span></span>

- [<span data-ttu-id="50ac6-117">ICorDebugAppDomain3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="50ac6-117">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
