---
title: "ICorDebugMDA::GetName (Método)"
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
- ICorDebugMDA.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetName
helpviewer_keywords:
- ICorDebugMDA::GetName method [.NET Framework debugging]
- GetName method, ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 885bf5e8-00b7-4cd7-9d8d-e720d47918c4
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c31125b1faf9f14262e8e4a4c6269671a35519f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmdagetname-method"></a><span data-ttu-id="cdc79-102">ICorDebugMDA::GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="cdc79-102">ICorDebugMDA::GetName Method</span></span>
<span data-ttu-id="cdc79-103">Obtiene una cadena que contiene el nombre del Asistente para depuración administrada (MDA) representado por [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="cdc79-103">Gets a string containing the name of the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdc79-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cdc79-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cdc79-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cdc79-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="cdc79-106">[in] Tamaño de la matriz `szName`.</span><span class="sxs-lookup"><span data-stu-id="cdc79-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="cdc79-107">[out] Un puntero a la longitud del nombre.</span><span class="sxs-lookup"><span data-stu-id="cdc79-107">[out] A pointer to the length of the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="cdc79-108">[out] Matriz en la que se va a almacenar el nombre.</span><span class="sxs-lookup"><span data-stu-id="cdc79-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cdc79-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cdc79-109">Remarks</span></span>  
 <span data-ttu-id="cdc79-110">Los nombres de MDA son valores únicos.</span><span class="sxs-lookup"><span data-stu-id="cdc79-110">MDA names are unique values.</span></span> <span data-ttu-id="cdc79-111">El `GetName` método es una buena alternativa de rendimiento para obtener la secuencia XML y extraer el nombre de la secuencia basándose en el esquema.</span><span class="sxs-lookup"><span data-stu-id="cdc79-111">The `GetName` method is a convenient performance alternative to getting the XML stream and extracting the name from the stream based on the schema.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdc79-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cdc79-112">Requirements</span></span>  
 <span data-ttu-id="cdc79-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cdc79-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cdc79-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cdc79-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cdc79-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cdc79-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cdc79-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cdc79-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdc79-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="cdc79-117">See Also</span></span>  
 [<span data-ttu-id="cdc79-118">ICorDebugMDA (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cdc79-118">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)  
 [<span data-ttu-id="cdc79-119">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="cdc79-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
