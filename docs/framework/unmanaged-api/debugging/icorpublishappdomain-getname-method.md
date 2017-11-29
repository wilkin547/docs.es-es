---
title: "ICorPublishAppDomain::GetName (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishAppDomain.GetName
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishAppDomain::GetName
helpviewer_keywords:
- GetName method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetName method [.NET Framework debugging]
ms.assetid: 6ef8ac9b-9803-4b65-8b13-25f3e0b1bc6b
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9807f914c767cc212bf97d83042e76d42a3d9440
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorpublishappdomaingetname-method"></a><span data-ttu-id="d6baf-102">ICorPublishAppDomain::GetName (Método)</span><span class="sxs-lookup"><span data-stu-id="d6baf-102">ICorPublishAppDomain::GetName Method</span></span>
<span data-ttu-id="d6baf-103">Obtiene el nombre del dominio de aplicación que está representado por este [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span><span class="sxs-lookup"><span data-stu-id="d6baf-103">Gets the name of the application domain that is represented by this [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6baf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d6baf-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in]  ULONG32   cchName,   
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR       *szName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d6baf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d6baf-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="d6baf-106">[in] Tamaño de la matriz `szName`.</span><span class="sxs-lookup"><span data-stu-id="d6baf-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="d6baf-107">[out] Un puntero al número de caracteres anchos, incluido el carácter null, devuelto en la `szName` matriz.</span><span class="sxs-lookup"><span data-stu-id="d6baf-107">[out] A pointer to the number of wide characters, including the null character, returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="d6baf-108">[out] Matriz en la que se va a almacenar el nombre.</span><span class="sxs-lookup"><span data-stu-id="d6baf-108">[out] An array in which to store the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6baf-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d6baf-109">Remarks</span></span>  
 <span data-ttu-id="d6baf-110">Si `szName` es distinto de null, el `GetName` método copia hasta `cchName` caracteres (incluido el terminador null) en `szName`.</span><span class="sxs-lookup"><span data-stu-id="d6baf-110">If `szName` is non-null, the `GetName` method copies up to `cchName` characters (including the null terminator) into `szName`.</span></span> <span data-ttu-id="d6baf-111">Si se devuelve un valor no nulo en `pcchName`, el número real de caracteres del nombre (incluido el terminador null) se almacena en la `szName` matriz.</span><span class="sxs-lookup"><span data-stu-id="d6baf-111">If a non-null is returned in `pcchName`, the actual number of characters in the name (including the null terminator) is stored in the `szName` array.</span></span>  
  
 <span data-ttu-id="d6baf-112">El `GetName` método devuelve un HRESULT de S_OK, independientemente de cuántos caracteres se han copiado.</span><span class="sxs-lookup"><span data-stu-id="d6baf-112">The `GetName` method returns an S_OK HRESULT regardless of how many characters were copied.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6baf-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d6baf-113">Requirements</span></span>  
 <span data-ttu-id="d6baf-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6baf-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6baf-115">**Encabezado:** Cordebug.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="d6baf-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="d6baf-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6baf-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6baf-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6baf-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6baf-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6baf-118">See Also</span></span>  
 [<span data-ttu-id="d6baf-119">ICorPublishAppDomain (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d6baf-119">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)
