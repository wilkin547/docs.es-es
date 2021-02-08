---
description: 'Más información acerca de: ICorDebugMDA:: GetXML (método)'
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
ms.openlocfilehash: fa506e6e8f306271f10a7a715af9b8bc6a80c1d6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801142"
---
# <a name="icordebugmdagetxml-method"></a><span data-ttu-id="cecdc-103">ICorDebugMDA::GetXML (Método)</span><span class="sxs-lookup"><span data-stu-id="cecdc-103">ICorDebugMDA::GetXML Method</span></span>

<span data-ttu-id="cecdc-104">Obtiene la secuencia XML completa asociada al Asistente para la depuración administrada (MDA) representado por [ICorDebugMDA](icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="cecdc-104">Gets the full XML stream associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cecdc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cecdc-105">Syntax</span></span>  
  
```cpp  
HRESULT GetXML (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cecdc-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cecdc-106">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="cecdc-107">[in] Tamaño de la matriz `szName`.</span><span class="sxs-lookup"><span data-stu-id="cecdc-107">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="cecdc-108">enuncia Puntero a la longitud de la secuencia XML.</span><span class="sxs-lookup"><span data-stu-id="cecdc-108">[out] A pointer to the length of the XML stream.</span></span>  
  
 `szName`  
 <span data-ttu-id="cecdc-109">enuncia Matriz en la que se va a almacenar la secuencia XML.</span><span class="sxs-lookup"><span data-stu-id="cecdc-109">[out] An array in which to store the XML stream.</span></span> <span data-ttu-id="cecdc-110">La matriz puede estar vacía.</span><span class="sxs-lookup"><span data-stu-id="cecdc-110">The array may be empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cecdc-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cecdc-111">Remarks</span></span>  

 <span data-ttu-id="cecdc-112">El `GetXML` método puede afectar al rendimiento, dependiendo del tamaño de la secuencia XML asociada.</span><span class="sxs-lookup"><span data-stu-id="cecdc-112">The `GetXML` method can potentially affect performance, depending on the size of the associated XML stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cecdc-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cecdc-113">Requirements</span></span>  

 <span data-ttu-id="cecdc-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cecdc-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cecdc-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cecdc-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cecdc-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cecdc-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cecdc-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cecdc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cecdc-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="cecdc-118">See also</span></span>

- [<span data-ttu-id="cecdc-119">ICorDebugMDA (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cecdc-119">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="cecdc-120">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="cecdc-120">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
