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
ms.openlocfilehash: 219aa27296dffa525bf3e2b836825437a8ce77b0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207654"
---
# <a name="icordebugmdagetxml-method"></a><span data-ttu-id="3b793-102">ICorDebugMDA::GetXML (Método)</span><span class="sxs-lookup"><span data-stu-id="3b793-102">ICorDebugMDA::GetXML Method</span></span>
<span data-ttu-id="3b793-103">Obtiene la secuencia XML completa asociada al Asistente para la depuración administrada (MDA) representado por [ICorDebugMDA](icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="3b793-103">Gets the full XML stream associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b793-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3b793-104">Syntax</span></span>  
  
```cpp  
HRESULT GetXML (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b793-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3b793-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="3b793-106">[in] Tamaño de la matriz `szName`.</span><span class="sxs-lookup"><span data-stu-id="3b793-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="3b793-107">enuncia Puntero a la longitud de la secuencia XML.</span><span class="sxs-lookup"><span data-stu-id="3b793-107">[out] A pointer to the length of the XML stream.</span></span>  
  
 `szName`  
 <span data-ttu-id="3b793-108">enuncia Matriz en la que se va a almacenar la secuencia XML.</span><span class="sxs-lookup"><span data-stu-id="3b793-108">[out] An array in which to store the XML stream.</span></span> <span data-ttu-id="3b793-109">La matriz puede estar vacía.</span><span class="sxs-lookup"><span data-stu-id="3b793-109">The array may be empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b793-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3b793-110">Remarks</span></span>  
 <span data-ttu-id="3b793-111">El `GetXML` método puede afectar al rendimiento, dependiendo del tamaño de la secuencia XML asociada.</span><span class="sxs-lookup"><span data-stu-id="3b793-111">The `GetXML` method can potentially affect performance, depending on the size of the associated XML stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b793-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3b793-112">Requirements</span></span>  
 <span data-ttu-id="3b793-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b793-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b793-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3b793-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3b793-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b793-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b793-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b793-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b793-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3b793-117">See also</span></span>

- [<span data-ttu-id="3b793-118">ICorDebugMDA (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3b793-118">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="3b793-119">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="3b793-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
