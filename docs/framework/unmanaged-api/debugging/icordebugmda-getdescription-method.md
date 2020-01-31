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
ms.openlocfilehash: e3744cbfa08de30c53f15c457034b50e2fc5d283
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793247"
---
# <a name="icordebugmdagetdescription-method"></a><span data-ttu-id="c0eba-102">ICorDebugMDA::GetDescription (Método)</span><span class="sxs-lookup"><span data-stu-id="c0eba-102">ICorDebugMDA::GetDescription Method</span></span>
<span data-ttu-id="c0eba-103">Obtiene una cadena que contiene la descripción del Asistente para la depuración administrada (MDA) representado por [ICorDebugMDA](icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="c0eba-103">Gets a string containing the description of the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0eba-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c0eba-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDescription (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0eba-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="c0eba-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="c0eba-106">de Tamaño del búfer de cadena que almacenará la descripción.</span><span class="sxs-lookup"><span data-stu-id="c0eba-106">[in] The size of the string buffer that will store the description.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="c0eba-107">enuncia Puntero al número de bytes devuelto en el búfer de cadena.</span><span class="sxs-lookup"><span data-stu-id="c0eba-107">[out] A pointer to the number of bytes returned in the string buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="c0eba-108">enuncia Búfer de cadena que contiene la descripción del MDA.</span><span class="sxs-lookup"><span data-stu-id="c0eba-108">[out] A string buffer containing the description of the MDA.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0eba-109">Notas</span><span class="sxs-lookup"><span data-stu-id="c0eba-109">Remarks</span></span>  
 <span data-ttu-id="c0eba-110">La longitud de la cadena puede ser cero.</span><span class="sxs-lookup"><span data-stu-id="c0eba-110">The string can be zero in length.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0eba-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="c0eba-111">Requirements</span></span>  
 <span data-ttu-id="c0eba-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0eba-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0eba-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c0eba-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c0eba-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0eba-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0eba-115">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0eba-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0eba-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0eba-116">See also</span></span>

- [<span data-ttu-id="c0eba-117">ICorDebugMDA (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c0eba-117">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="c0eba-118">Diagnóstico de errores con asistentes para la depuración administrada</span><span class="sxs-lookup"><span data-stu-id="c0eba-118">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
