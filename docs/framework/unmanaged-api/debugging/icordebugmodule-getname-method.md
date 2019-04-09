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
ms.openlocfilehash: b39467c067e50f2d553b35a41b0f783e0fc82156
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59176649"
---
# <a name="icordebugmodulegetname-method"></a><span data-ttu-id="3da1a-102">ICorDebugModule::GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="3da1a-102">ICorDebugModule::GetName Method</span></span>
<span data-ttu-id="3da1a-103">Obtiene el nombre de archivo del módulo.</span><span class="sxs-lookup"><span data-stu-id="3da1a-103">Gets the file name of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3da1a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3da1a-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3da1a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3da1a-105">Parameters</span></span>  
 `cchname`  
 <span data-ttu-id="3da1a-106">[in] Tamaño de la matriz `szName`.</span><span class="sxs-lookup"><span data-stu-id="3da1a-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="3da1a-107">[in] Un puntero a la longitud del nombre devuelto.</span><span class="sxs-lookup"><span data-stu-id="3da1a-107">[in] A pointer to the length of the returned name.</span></span>  
  
 `szName`  
 <span data-ttu-id="3da1a-108">[out] Una matriz que almacena el nombre devuelto.</span><span class="sxs-lookup"><span data-stu-id="3da1a-108">[out] An array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3da1a-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3da1a-109">Remarks</span></span>  
 <span data-ttu-id="3da1a-110">El `GetName` método devuelve S_OK HRESULT si el nombre de archivo del módulo coincide con el nombre en el disco.</span><span class="sxs-lookup"><span data-stu-id="3da1a-110">The `GetName` method returns an S_OK HRESULT if the module's file name matches the name on disk.</span></span> `GetName` <span data-ttu-id="3da1a-111">Devuelve un HRESULT S_FALSE si el nombre es fabricadas, por ejemplo, para un módulo dinámico o en memoria.</span><span class="sxs-lookup"><span data-stu-id="3da1a-111">returns an S_FALSE HRESULT if the name is fabricated, such as for a dynamic or in-memory module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3da1a-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3da1a-112">Requirements</span></span>  
 <span data-ttu-id="3da1a-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3da1a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3da1a-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3da1a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3da1a-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3da1a-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3da1a-116">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3da1a-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3da1a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="3da1a-117">See also</span></span>
