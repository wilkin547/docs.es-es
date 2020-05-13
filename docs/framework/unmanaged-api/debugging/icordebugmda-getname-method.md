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
ms.openlocfilehash: 6a6769265a2e140f1fa001bb8240bc5d4bd76018
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213678"
---
# <a name="icordebugmdagetname-method"></a><span data-ttu-id="de495-102">ICorDebugMDA::GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="de495-102">ICorDebugMDA::GetName Method</span></span>
<span data-ttu-id="de495-103">Obtiene una cadena que contiene el nombre del Asistente para la depuración administrada (MDA) representado por [ICorDebugMDA](icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="de495-103">Gets a string containing the name of the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de495-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="de495-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in] ULONG32   cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
        WCHAR      szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de495-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="de495-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="de495-106">[in] Tamaño de la matriz `szName`.</span><span class="sxs-lookup"><span data-stu-id="de495-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="de495-107">enuncia Puntero a la longitud del nombre.</span><span class="sxs-lookup"><span data-stu-id="de495-107">[out] A pointer to the length of the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="de495-108">enuncia Matriz en la que se va a almacenar el nombre.</span><span class="sxs-lookup"><span data-stu-id="de495-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de495-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="de495-109">Remarks</span></span>  
 <span data-ttu-id="de495-110">Los nombres de MDA son valores únicos.</span><span class="sxs-lookup"><span data-stu-id="de495-110">MDA names are unique values.</span></span> <span data-ttu-id="de495-111">El `GetName` método es una alternativa de rendimiento adecuada para obtener la secuencia XML y extraer el nombre de la secuencia basada en el esquema.</span><span class="sxs-lookup"><span data-stu-id="de495-111">The `GetName` method is a convenient performance alternative to getting the XML stream and extracting the name from the stream based on the schema.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de495-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="de495-112">Requirements</span></span>  
 <span data-ttu-id="de495-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de495-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de495-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de495-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de495-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de495-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de495-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de495-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de495-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="de495-117">See also</span></span>

- [<span data-ttu-id="de495-118">ICorDebugMDA (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="de495-118">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="de495-119">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="de495-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
