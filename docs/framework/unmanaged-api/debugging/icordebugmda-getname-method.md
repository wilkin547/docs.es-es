---
description: 'Más información acerca de: ICorDebugMDA:: GetName (método)'
title: ICorDebugMDA::GetName (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: 4ea39f062071073684a20d8f60875fbaaab43a2f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801174"
---
# <a name="icordebugmdagetname-method"></a><span data-ttu-id="7bf61-103">ICorDebugMDA::GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="7bf61-103">ICorDebugMDA::GetName Method</span></span>

<span data-ttu-id="7bf61-104">Obtiene una cadena que contiene el nombre del Asistente para la depuración administrada (MDA) representado por [ICorDebugMDA](icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="7bf61-104">Gets a string containing the name of the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bf61-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7bf61-105">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7bf61-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7bf61-106">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="7bf61-107">[in] Tamaño de la matriz `szName`.</span><span class="sxs-lookup"><span data-stu-id="7bf61-107">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="7bf61-108">enuncia Puntero a la longitud del nombre.</span><span class="sxs-lookup"><span data-stu-id="7bf61-108">[out] A pointer to the length of the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="7bf61-109">enuncia Matriz en la que se va a almacenar el nombre.</span><span class="sxs-lookup"><span data-stu-id="7bf61-109">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7bf61-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7bf61-110">Remarks</span></span>  

 <span data-ttu-id="7bf61-111">Los nombres de MDA son valores únicos.</span><span class="sxs-lookup"><span data-stu-id="7bf61-111">MDA names are unique values.</span></span> <span data-ttu-id="7bf61-112">El `GetName` método es una alternativa de rendimiento adecuada para obtener la secuencia XML y extraer el nombre de la secuencia basada en el esquema.</span><span class="sxs-lookup"><span data-stu-id="7bf61-112">The `GetName` method is a convenient performance alternative to getting the XML stream and extracting the name from the stream based on the schema.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bf61-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7bf61-113">Requirements</span></span>  

 <span data-ttu-id="7bf61-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7bf61-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bf61-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7bf61-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7bf61-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7bf61-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7bf61-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bf61-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bf61-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="7bf61-118">See also</span></span>

- [<span data-ttu-id="7bf61-119">ICorDebugMDA (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7bf61-119">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="7bf61-120">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="7bf61-120">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
