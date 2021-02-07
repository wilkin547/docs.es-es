---
description: 'Más información sobre: ICorDebugAppDomain3:: Getcachedwinrttypesforiids ((método)'
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
ms.openlocfilehash: 76b93cdb8c465935a4aaf36090ee44f2b6253a3b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754178"
---
# <a name="icordebugappdomain3getcachedwinrttypesforiids-method"></a><span data-ttu-id="d4c82-103">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs (Método)</span><span class="sxs-lookup"><span data-stu-id="d4c82-103">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs Method</span></span>

<span data-ttu-id="d4c82-104">Obtiene un enumerador para los tipos de Windows Runtime almacenados en memoria caché en un dominio de aplicación en función de sus identificadores de interfaz.</span><span class="sxs-lookup"><span data-stu-id="d4c82-104">Gets an enumerator for cached Windows Runtime types in an application domain based on their interface identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4c82-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d4c82-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedWinRTTypesForIIDs (
    [in]  ULONG32            cReqTypes,  
    [in]  GUID                *iidsToResolve,  
    [out] ICorDebugTypeEnum   **ppTypesEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4c82-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d4c82-106">Parameters</span></span>  

 `cReqTypes`  
 <span data-ttu-id="d4c82-107">de Número de tipos necesarios.</span><span class="sxs-lookup"><span data-stu-id="d4c82-107">[in] The number of required types.</span></span>  
  
 `iidsToResolve`  
 <span data-ttu-id="d4c82-108">de Puntero a una matriz que contiene los identificadores de interfaz correspondientes a las representaciones administradas de los tipos de Windows Runtime que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="d4c82-108">[in] A pointer to an array that contains the interface identifiers corresponding to the managed representations of the Windows Runtime types to be retrieved.</span></span>  
  
 `ppTypesEnum`  
 <span data-ttu-id="d4c82-109">enuncia Puntero a la dirección de un objeto de interfaz "ICorDebugTypeEnum" que permite la enumeración de las representaciones administradas en caché de los tipos de Windows Runtime recuperados, en función de los identificadores de interfaz de `iidsToResolve` .</span><span class="sxs-lookup"><span data-stu-id="d4c82-109">[out] A pointer to the address of an "ICorDebugTypeEnum" interface object that allows enumeration of the cached managed representations of the Windows Runtime types retrieved, based on the interface identifiers in `iidsToResolve`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4c82-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d4c82-110">Remarks</span></span>  

 <span data-ttu-id="d4c82-111">Si el método no puede recuperar información de un identificador de interfaz concreto, la entrada correspondiente en la colección "ICorDebugTypeEnum" tendrá un tipo de `ELEMENT_TYPE_END` errores debido a problemas de recuperación de datos o `ELEMENT_TYPE_VOID` para los identificadores de interfaz desconocidos.</span><span class="sxs-lookup"><span data-stu-id="d4c82-111">If the method fails to retrieve information for a specific interface identifier, the corresponding entry in the "ICorDebugTypeEnum" collection will have a type of `ELEMENT_TYPE_END` for errors due to data retrieval issues, or `ELEMENT_TYPE_VOID` for unknown interface identifiers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4c82-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d4c82-112">Requirements</span></span>  

 <span data-ttu-id="d4c82-113">**Plataformas:** Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="d4c82-113">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="d4c82-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d4c82-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4c82-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4c82-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4c82-116">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4c82-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4c82-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4c82-117">See also</span></span>

- [<span data-ttu-id="d4c82-118">ICorDebugAppDomain3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d4c82-118">ICorDebugAppDomain3 Interface</span></span>](icordebugappdomain3-interface.md)
