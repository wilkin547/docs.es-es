---
title: ICorDebugMDA::GetDescription (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetDescription
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetDescription
helpviewer_keywords:
- GetDescription method [.NET Framework debugging]
- ICorDebugMDA::GetDescription method [.NET Framework debugging]
ms.assetid: 01d1b481-ca67-4712-8744-d342ec0df639
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2fdace527194228dd6004a991950a80d23275650
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413301"
---
# <a name="icordebugmdagetdescription-method"></a><span data-ttu-id="e931d-102">ICorDebugMDA::GetDescription (Método)</span><span class="sxs-lookup"><span data-stu-id="e931d-102">ICorDebugMDA::GetDescription Method</span></span>
<span data-ttu-id="e931d-103">Obtiene una cadena que contiene la descripción del Asistente para depuración administrada (MDA) representado por [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="e931d-103">Gets a string containing the description of the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e931d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e931d-104">Syntax</span></span>  
  
```  
HRESULT GetDescription (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e931d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e931d-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="e931d-106">[in] El tamaño del búfer de cadena que almacenará la descripción.</span><span class="sxs-lookup"><span data-stu-id="e931d-106">[in] The size of the string buffer that will store the description.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="e931d-107">[out] Un puntero al número de bytes devueltos en el búfer de cadena.</span><span class="sxs-lookup"><span data-stu-id="e931d-107">[out] A pointer to the number of bytes returned in the string buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="e931d-108">[out] Un búfer de cadena que contiene la descripción del MDA.</span><span class="sxs-lookup"><span data-stu-id="e931d-108">[out] A string buffer containing the description of the MDA.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e931d-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e931d-109">Remarks</span></span>  
 <span data-ttu-id="e931d-110">La cadena puede ser de longitud cero.</span><span class="sxs-lookup"><span data-stu-id="e931d-110">The string can be zero in length.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e931d-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e931d-111">Requirements</span></span>  
 <span data-ttu-id="e931d-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e931d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e931d-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e931d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e931d-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e931d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e931d-115">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e931d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e931d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e931d-116">See Also</span></span>  
 [<span data-ttu-id="e931d-117">ICorDebugMDA (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e931d-117">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)  
 [<span data-ttu-id="e931d-118">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="e931d-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
