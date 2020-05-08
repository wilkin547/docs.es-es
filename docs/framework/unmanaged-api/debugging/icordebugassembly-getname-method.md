---
title: ICorDebugAssembly::GetName (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetName
helpviewer_keywords:
- ICorDebugAssembly::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: cdeda721-b214-4503-a291-c70b68b5f36b
topic_type:
- apiref
ms.openlocfilehash: daf5319f5d57f44cb20ce9f28d3c7b84c7015ff6
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894919"
---
# <a name="icordebugassemblygetname-method"></a><span data-ttu-id="9b819-102">ICorDebugAssembly::GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="9b819-102">ICorDebugAssembly::GetName Method</span></span>
<span data-ttu-id="9b819-103">Obtiene el nombre del ensamblado que esta `ICorDebugAssembly` instancia representa.</span><span class="sxs-lookup"><span data-stu-id="9b819-103">Gets the name of the assembly that this `ICorDebugAssembly` instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b819-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9b819-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName (  
    [in] ULONG32  cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b819-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9b819-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="9b819-106">[in] Tamaño de la matriz `szName`.</span><span class="sxs-lookup"><span data-stu-id="9b819-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="9b819-107">enuncia Puntero a un entero que especifica la longitud real del nombre.</span><span class="sxs-lookup"><span data-stu-id="9b819-107">[out] A pointer to an integer that specifies the actual length of the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="9b819-108">enuncia Matriz que almacena el nombre.</span><span class="sxs-lookup"><span data-stu-id="9b819-108">[out] An array that stores the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b819-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9b819-109">Remarks</span></span>  
 <span data-ttu-id="9b819-110">El `GetName` método devuelve la ruta de acceso completa y el nombre de archivo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9b819-110">The `GetName` method returns the full path and file name of the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b819-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9b819-111">Requirements</span></span>  
 <span data-ttu-id="9b819-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b819-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b819-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9b819-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9b819-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b819-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b819-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b819-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
