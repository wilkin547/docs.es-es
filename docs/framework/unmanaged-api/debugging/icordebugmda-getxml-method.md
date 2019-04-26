---
title: ICorDebugMDA::GetXML (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetXML
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetXML
helpviewer_keywords:
- ICorDebugMDA::GetXML method [.NET Framework debugging]
- GetXML method [.NET Framework debugging]
ms.assetid: 29746b24-3766-4255-8813-0426c45e73e5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4e78b8a2069671d0fe790956ca914225325a78bc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916622"
---
# <a name="icordebugmdagetxml-method"></a><span data-ttu-id="9d3e1-102">ICorDebugMDA::GetXML (Método)</span><span class="sxs-lookup"><span data-stu-id="9d3e1-102">ICorDebugMDA::GetXML Method</span></span>
<span data-ttu-id="9d3e1-103">Obtiene la secuencia XML completa asociada con el Asistente para depuración administrada (MDA) representado por [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="9d3e1-103">Gets the full XML stream associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d3e1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9d3e1-104">Syntax</span></span>  
  
```  
HRESULT GetXML (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d3e1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9d3e1-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="9d3e1-106">[in] Tamaño de la matriz `szName`.</span><span class="sxs-lookup"><span data-stu-id="9d3e1-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="9d3e1-107">[out] Un puntero a la longitud de la secuencia XML.</span><span class="sxs-lookup"><span data-stu-id="9d3e1-107">[out] A pointer to the length of the XML stream.</span></span>  
  
 `szName`  
 <span data-ttu-id="9d3e1-108">[out] Matriz en la que se va a almacenar la secuencia XML.</span><span class="sxs-lookup"><span data-stu-id="9d3e1-108">[out] An array in which to store the XML stream.</span></span> <span data-ttu-id="9d3e1-109">La matriz puede estar vacía.</span><span class="sxs-lookup"><span data-stu-id="9d3e1-109">The array may be empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d3e1-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9d3e1-110">Remarks</span></span>  
 <span data-ttu-id="9d3e1-111">El `GetXML` método potencialmente puede afectar al rendimiento, dependiendo del tamaño de la secuencia XML asociada.</span><span class="sxs-lookup"><span data-stu-id="9d3e1-111">The `GetXML` method can potentially affect performance, depending on the size of the associated XML stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d3e1-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9d3e1-112">Requirements</span></span>  
 <span data-ttu-id="9d3e1-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d3e1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d3e1-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9d3e1-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9d3e1-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d3e1-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d3e1-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d3e1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d3e1-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d3e1-117">See also</span></span>

- [<span data-ttu-id="9d3e1-118">ICorDebugMDA (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9d3e1-118">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="9d3e1-119">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="9d3e1-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
