---
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
ms.openlocfilehash: 1b19ce5e9f795fd9ff4dd15e10256a150063a314
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128041"
---
# <a name="icordebugmdagetname-method"></a><span data-ttu-id="8a5fa-102">ICorDebugMDA::GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="8a5fa-102">ICorDebugMDA::GetName Method</span></span>
<span data-ttu-id="8a5fa-103">Obtiene una cadena que contiene el nombre del Asistente para la depuración administrada (MDA) representado por [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="8a5fa-103">Gets a string containing the name of the managed debugging assistant (MDA) represented by [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a5fa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8a5fa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a5fa-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8a5fa-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="8a5fa-106">[in] Tamaño de la matriz `szName`.</span><span class="sxs-lookup"><span data-stu-id="8a5fa-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="8a5fa-107">enuncia Puntero a la longitud del nombre.</span><span class="sxs-lookup"><span data-stu-id="8a5fa-107">[out] A pointer to the length of the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="8a5fa-108">enuncia Matriz en la que se va a almacenar el nombre.</span><span class="sxs-lookup"><span data-stu-id="8a5fa-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a5fa-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8a5fa-109">Remarks</span></span>  
 <span data-ttu-id="8a5fa-110">Los nombres de MDA son valores únicos.</span><span class="sxs-lookup"><span data-stu-id="8a5fa-110">MDA names are unique values.</span></span> <span data-ttu-id="8a5fa-111">El método `GetName` es una alternativa de rendimiento adecuada para obtener la secuencia XML y extraer el nombre de la secuencia basada en el esquema.</span><span class="sxs-lookup"><span data-stu-id="8a5fa-111">The `GetName` method is a convenient performance alternative to getting the XML stream and extracting the name from the stream based on the schema.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a5fa-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8a5fa-112">Requirements</span></span>  
 <span data-ttu-id="8a5fa-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a5fa-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a5fa-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a5fa-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a5fa-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a5fa-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a5fa-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a5fa-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a5fa-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a5fa-117">See also</span></span>

- [<span data-ttu-id="8a5fa-118">ICorDebugMDA (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8a5fa-118">ICorDebugMDA Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)
- [<span data-ttu-id="8a5fa-119">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="8a5fa-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
