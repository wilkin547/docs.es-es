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
ms.openlocfilehash: f8e92ec4f813e8810273a1514298d0739a3d2406
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179057"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a><span data-ttu-id="df76e-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs (Método)</span><span class="sxs-lookup"><span data-stu-id="df76e-102">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs Method</span></span>
<span data-ttu-id="df76e-103">Obtiene un enumerador para los tipos de Windows Runtime almacenados en caché en un dominio de aplicación en función de sus identificadores de interfaz.</span><span class="sxs-lookup"><span data-stu-id="df76e-103">Gets an enumerator for cached Windows Runtime types in an application domain based on their interface identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df76e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="df76e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedWinRTTypesForIIDs (
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df76e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="df76e-105">Parameters</span></span>  
 `cReqTypes`  
 <span data-ttu-id="df76e-106">[en] El número de tipos necesarios.</span><span class="sxs-lookup"><span data-stu-id="df76e-106">[in] The number of required types.</span></span>  
  
 `iidsToResolve`  
 <span data-ttu-id="df76e-107">[en] Puntero a una matriz que contiene los identificadores de interfaz correspondientes a las representaciones administradas de los tipos de Windows Runtime que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="df76e-107">[in] A pointer to an array that contains the interface identifiers corresponding to the managed representations of the Windows Runtime types to be retrieved.</span></span>  
  
 `ppTypesEnum`  
 <span data-ttu-id="df76e-108">[fuera] Puntero a la dirección de un objeto de interfaz "ICorDebugTypeEnum" que permite la enumeración de las `iidsToResolve`representaciones administradas almacenadas en caché de los tipos de Windows Runtime recuperados, en función de los identificadores de interfaz en .</span><span class="sxs-lookup"><span data-stu-id="df76e-108">[out] A pointer to the address of an "ICorDebugTypeEnum" interface object that allows enumeration of the cached managed representations of the Windows Runtime types retrieved, based on the interface identifiers in `iidsToResolve`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df76e-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="df76e-109">Remarks</span></span>  
 <span data-ttu-id="df76e-110">Si el método no puede recuperar información para un identificador de interfaz específico, la entrada `ELEMENT_TYPE_END` correspondiente en el "ICorDebugTypeEnum" colección tendrá un tipo de para errores debido a problemas de recuperación de datos, o `ELEMENT_TYPE_VOID` para identificadores de interfaz desconocidos.</span><span class="sxs-lookup"><span data-stu-id="df76e-110">If the method fails to retrieve information for a specific interface identifier, the corresponding entry in the "ICorDebugTypeEnum" collection will have a type of `ELEMENT_TYPE_END` for errors due to data retrieval issues, or `ELEMENT_TYPE_VOID` for unknown interface identifiers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df76e-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="df76e-111">Requirements</span></span>  
 <span data-ttu-id="df76e-112">**Plataformas:** Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="df76e-112">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="df76e-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df76e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="df76e-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df76e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df76e-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df76e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df76e-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="df76e-116">See also</span></span>

- [<span data-ttu-id="df76e-117">ICorDebugAppDomain3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="df76e-117">ICorDebugAppDomain3 Interface</span></span>](icordebugappdomain3-interface.md)
