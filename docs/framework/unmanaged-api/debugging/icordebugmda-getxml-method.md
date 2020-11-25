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
ms.openlocfilehash: 9a088c7e4e9c72c8247ccdd384bc724587210c37
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710875"
---
# <a name="icordebugmdagetxml-method"></a><span data-ttu-id="d04ef-102">ICorDebugMDA::GetXML (Método)</span><span class="sxs-lookup"><span data-stu-id="d04ef-102">ICorDebugMDA::GetXML Method</span></span>

<span data-ttu-id="d04ef-103">Obtiene la secuencia XML completa asociada al Asistente para la depuración administrada (MDA) representado por [ICorDebugMDA](icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="d04ef-103">Gets the full XML stream associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d04ef-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d04ef-104">Syntax</span></span>  
  
```cpp  
HRESULT GetXML (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d04ef-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d04ef-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="d04ef-106">[in] Tamaño de la matriz `szName`.</span><span class="sxs-lookup"><span data-stu-id="d04ef-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="d04ef-107">enuncia Puntero a la longitud de la secuencia XML.</span><span class="sxs-lookup"><span data-stu-id="d04ef-107">[out] A pointer to the length of the XML stream.</span></span>  
  
 `szName`  
 <span data-ttu-id="d04ef-108">enuncia Matriz en la que se va a almacenar la secuencia XML.</span><span class="sxs-lookup"><span data-stu-id="d04ef-108">[out] An array in which to store the XML stream.</span></span> <span data-ttu-id="d04ef-109">La matriz puede estar vacía.</span><span class="sxs-lookup"><span data-stu-id="d04ef-109">The array may be empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d04ef-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d04ef-110">Remarks</span></span>  

 <span data-ttu-id="d04ef-111">El `GetXML` método puede afectar al rendimiento, dependiendo del tamaño de la secuencia XML asociada.</span><span class="sxs-lookup"><span data-stu-id="d04ef-111">The `GetXML` method can potentially affect performance, depending on the size of the associated XML stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d04ef-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d04ef-112">Requirements</span></span>  

 <span data-ttu-id="d04ef-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d04ef-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d04ef-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d04ef-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d04ef-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d04ef-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d04ef-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d04ef-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d04ef-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d04ef-117">See also</span></span>

- [<span data-ttu-id="d04ef-118">ICorDebugMDA (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d04ef-118">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="d04ef-119">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="d04ef-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
