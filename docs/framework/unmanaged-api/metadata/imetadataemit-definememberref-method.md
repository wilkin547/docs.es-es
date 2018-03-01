---
title: "IMetaDataEmit::DefineMemberRef (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataEmit.DefineMemberRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMemberRef
helpviewer_keywords:
- DefineMemberRef method [.NET Framework metadata]
- IMetaDataEmit::DefineMemberRef method [.NET Framework metadata]
ms.assetid: 21b5bcb8-ea75-4962-8acc-ad17584061e5
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 38c2c495bc88dadae2d71b1b3710f30998023516
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinememberref-method"></a><span data-ttu-id="073b4-102">IMetaDataEmit::DefineMemberRef (Método)</span><span class="sxs-lookup"><span data-stu-id="073b4-102">IMetaDataEmit::DefineMemberRef Method</span></span>
<span data-ttu-id="073b4-103">Define una referencia a un miembro de un módulo fuera del ámbito actual y obtiene un símbolo (token) para dicha definición de referencia.</span><span class="sxs-lookup"><span data-stu-id="073b4-103">Defines a reference to a member of a module outside the current scope, and gets a token to that reference definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="073b4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="073b4-104">Syntax</span></span>  
  
```  
HRESULT DefineMemberRef (   
    [in]  mdToken           tkImport,   
    [in]  LPCWSTR           szName,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [out] mdMemberRef       *pmr   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="073b4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="073b4-105">Parameters</span></span>  
 `tkImport`  
 <span data-ttu-id="073b4-106">[in] Símbolo (token) de clase o una interfaz, el miembro de destino si el miembro no es global; Si el miembro es global, la `mdModuleRef` símbolo (token) para ese otro archivo.</span><span class="sxs-lookup"><span data-stu-id="073b4-106">[in] Token for the target member's class or interface, if the member is not global; if the member is global, the `mdModuleRef` token for that other file.</span></span>  
  
 `szName`  
 <span data-ttu-id="073b4-107">[in] El nombre del miembro de destino.</span><span class="sxs-lookup"><span data-stu-id="073b4-107">[in] The name of the target member.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="073b4-108">[in] La firma del miembro de destino.</span><span class="sxs-lookup"><span data-stu-id="073b4-108">[in] The signature of the target member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="073b4-109">[in] El recuento de bytes en `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="073b4-109">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="073b4-110">[out] El `mdMemberRef` token asignado.</span><span class="sxs-lookup"><span data-stu-id="073b4-110">[out] The `mdMemberRef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="073b4-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="073b4-111">Requirements</span></span>  
 <span data-ttu-id="073b4-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="073b4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="073b4-113">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="073b4-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="073b4-114">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="073b4-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="073b4-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="073b4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="073b4-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="073b4-116">See Also</span></span>  
 [<span data-ttu-id="073b4-117">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="073b4-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="073b4-118">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="073b4-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
