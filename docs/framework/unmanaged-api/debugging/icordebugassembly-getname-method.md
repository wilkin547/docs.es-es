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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3077e0494816a083d97839d66d06b18130e5dac8
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487803"
---
# <a name="icordebugassemblygetname-method"></a><span data-ttu-id="6f824-102">ICorDebugAssembly::GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="6f824-102">ICorDebugAssembly::GetName Method</span></span>
<span data-ttu-id="6f824-103">Obtiene el nombre del ensamblado que esto `ICorDebugAssembly` representa la instancia.</span><span class="sxs-lookup"><span data-stu-id="6f824-103">Gets the name of the assembly that this `ICorDebugAssembly` instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f824-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6f824-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in] ULONG32  cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f824-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6f824-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="6f824-106">[in] Tamaño de la matriz `szName`.</span><span class="sxs-lookup"><span data-stu-id="6f824-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="6f824-107">[out] Un puntero a un entero que especifica la longitud del nombre real.</span><span class="sxs-lookup"><span data-stu-id="6f824-107">[out] A pointer to an integer that specifies the actual length of the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="6f824-108">[out] Una matriz que almacena el nombre.</span><span class="sxs-lookup"><span data-stu-id="6f824-108">[out] An array that stores the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f824-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6f824-109">Remarks</span></span>  
 <span data-ttu-id="6f824-110">El `GetName` método devuelve la ruta de acceso y el nombre completo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6f824-110">The `GetName` method returns the full path and file name of the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f824-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6f824-111">Requirements</span></span>  
 <span data-ttu-id="6f824-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f824-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f824-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6f824-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6f824-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f824-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f824-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f824-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
