---
title: ICorDebugModule::GetName (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetName
helpviewer_keywords:
- ICorDebugModule::GetName method [.NET Framework debugging]
- GetName method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: db499637-7ba9-421e-b8b1-35856995e80b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ae9bc5925634f8bba71731a0c51eb19cf9eec04
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54663958"
---
# <a name="icordebugmodulegetname-method"></a><span data-ttu-id="fe00c-102">ICorDebugModule::GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="fe00c-102">ICorDebugModule::GetName Method</span></span>
<span data-ttu-id="fe00c-103">Obtiene el nombre de archivo del módulo.</span><span class="sxs-lookup"><span data-stu-id="fe00c-103">Gets the file name of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe00c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fe00c-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fe00c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fe00c-105">Parameters</span></span>  
 `cchname`  
 <span data-ttu-id="fe00c-106">[in] Tamaño de la matriz `szName`.</span><span class="sxs-lookup"><span data-stu-id="fe00c-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="fe00c-107">[in] Un puntero a la longitud del nombre devuelto.</span><span class="sxs-lookup"><span data-stu-id="fe00c-107">[in] A pointer to the length of the returned name.</span></span>  
  
 `szName`  
 <span data-ttu-id="fe00c-108">[out] Una matriz que almacena el nombre devuelto.</span><span class="sxs-lookup"><span data-stu-id="fe00c-108">[out] An array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe00c-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fe00c-109">Remarks</span></span>  
 <span data-ttu-id="fe00c-110">El `GetName` método devuelve S_OK HRESULT si el nombre de archivo del módulo coincide con el nombre en el disco.</span><span class="sxs-lookup"><span data-stu-id="fe00c-110">The `GetName` method returns an S_OK HRESULT if the module's file name matches the name on disk.</span></span> <span data-ttu-id="fe00c-111">`GetName` Devuelve un HRESULT S_FALSE si el nombre es fabricadas, por ejemplo, para un módulo dinámico o en memoria.</span><span class="sxs-lookup"><span data-stu-id="fe00c-111">`GetName` returns an S_FALSE HRESULT if the name is fabricated, such as for a dynamic or in-memory module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe00c-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fe00c-112">Requirements</span></span>  
 <span data-ttu-id="fe00c-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe00c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe00c-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fe00c-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fe00c-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe00c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe00c-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe00c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe00c-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe00c-117">See also</span></span>


