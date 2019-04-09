---
title: ICorDebugGuidToTypeEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum::Next
helpviewer_keywords:
- ICorDebugGuidToTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: c9937666-8e18-484d-9fe0-b9ac95199530
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f48c142b2b3742d01a8f796f11d5c9174529a041
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59105831"
---
# <a name="icordebugguidtotypeenumnext-method"></a><span data-ttu-id="0782a-102">ICorDebugGuidToTypeEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="0782a-102">ICorDebugGuidToTypeEnum::Next Method</span></span>
<span data-ttu-id="0782a-103">Obtiene el número especificado de [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instancias que se asignan los GUID para escribir información.</span><span class="sxs-lookup"><span data-stu-id="0782a-103">Gets the specified number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0782a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0782a-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched] CorDebugGuidToTypeMapping values[  ],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0782a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0782a-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="0782a-106">[in] El número de objetos de asignación del tipo de GUID va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="0782a-106">[in] The number of GUID-to-type mapping objects to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="0782a-107">[out] Una matriz de punteros, cada uno de los cuales señala a un [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) objeto que asigna un [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID a su objeto ICorDebugType correspondiente.</span><span class="sxs-lookup"><span data-stu-id="0782a-107">[out] An array of pointers, each of which points to a [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) object that maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding ICorDebugType object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="0782a-108">[out] Un puntero al número de [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) los objetos devueltos realmente en `values`.</span><span class="sxs-lookup"><span data-stu-id="0782a-108">[out] A pointer to the number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) objects actually returned in `values`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0782a-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0782a-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0782a-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0782a-110">Requirements</span></span>  
 **<span data-ttu-id="0782a-111">Plataformas:</span><span class="sxs-lookup"><span data-stu-id="0782a-111">Platforms:</span></span>** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]  
  
 <span data-ttu-id="0782a-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0782a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0782a-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0782a-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="0782a-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0782a-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0782a-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="0782a-115">See also</span></span>

- [<span data-ttu-id="0782a-116">ICorDebugGuidToTypeEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0782a-116">ICorDebugGuidToTypeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)
- [<span data-ttu-id="0782a-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="0782a-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
