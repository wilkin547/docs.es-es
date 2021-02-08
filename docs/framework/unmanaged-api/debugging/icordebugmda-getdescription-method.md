---
description: 'Más información acerca de: ICorDebugMDA:: GetDescription (método)'
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
ms.openlocfilehash: 75ee7d0b912c9f0039acc872173f2cbad25fff38
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801207"
---
# <a name="icordebugmdagetdescription-method"></a><span data-ttu-id="86212-103">ICorDebugMDA::GetDescription (Método)</span><span class="sxs-lookup"><span data-stu-id="86212-103">ICorDebugMDA::GetDescription Method</span></span>

<span data-ttu-id="86212-104">Obtiene una cadena que contiene la descripción del Asistente para la depuración administrada (MDA) representado por [ICorDebugMDA](icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="86212-104">Gets a string containing the description of the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86212-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="86212-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDescription (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86212-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="86212-106">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="86212-107">de Tamaño del búfer de cadena que almacenará la descripción.</span><span class="sxs-lookup"><span data-stu-id="86212-107">[in] The size of the string buffer that will store the description.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="86212-108">enuncia Puntero al número de bytes devuelto en el búfer de cadena.</span><span class="sxs-lookup"><span data-stu-id="86212-108">[out] A pointer to the number of bytes returned in the string buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="86212-109">enuncia Búfer de cadena que contiene la descripción del MDA.</span><span class="sxs-lookup"><span data-stu-id="86212-109">[out] A string buffer containing the description of the MDA.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86212-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="86212-110">Remarks</span></span>  

 <span data-ttu-id="86212-111">La longitud de la cadena puede ser cero.</span><span class="sxs-lookup"><span data-stu-id="86212-111">The string can be zero in length.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86212-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="86212-112">Requirements</span></span>  

 <span data-ttu-id="86212-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86212-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86212-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="86212-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="86212-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86212-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86212-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86212-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86212-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="86212-117">See also</span></span>

- [<span data-ttu-id="86212-118">ICorDebugMDA (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="86212-118">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="86212-119">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="86212-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
