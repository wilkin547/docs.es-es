---
title: "IMetaDataImport::EnumMembersWithName (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumMembersWithName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumMembersWithName
helpviewer_keywords:
- IMetaDataImport::EnumMembersWithName method [.NET Framework metadata]
- EnumMembersWithName method [.NET Framework metadata]
ms.assetid: 7c9e9120-3104-42f0-86ce-19a025f20dcc
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 64568fb185cd8a18e43639568ecb67fcfa350dba
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenummemberswithname-method"></a><span data-ttu-id="d539e-102">IMetaDataImport::EnumMembersWithName (Método)</span><span class="sxs-lookup"><span data-stu-id="d539e-102">IMetaDataImport::EnumMembersWithName Method</span></span>
<span data-ttu-id="d539e-103">Enumera los tokens de MemberDef que representan a miembros del tipo especificado con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="d539e-103">Enumerates MemberDef tokens representing members of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d539e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d539e-104">Syntax</span></span>  
  
```  
HRESULT EnumMembersWithName (  
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   cl,   
   [in]      LPCWSTR     szName,   
   [out]     mdToken     rMembers[],   
   [in]      ULONG       cMax,   
   [out]     ULONG       *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d539e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d539e-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="d539e-106">[entrada, salida] Un puntero para el enumerador.</span><span class="sxs-lookup"><span data-stu-id="d539e-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="d539e-107">[in] Un token de TypeDef que representa el tipo con miembros para enumerar.</span><span class="sxs-lookup"><span data-stu-id="d539e-107">[in] A TypeDef token representing the type with members to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="d539e-108">[in] El nombre de miembro que limita el ámbito del enumerador.</span><span class="sxs-lookup"><span data-stu-id="d539e-108">[in] The member name that limits the scope of the enumerator.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="d539e-109">[out] Matriz utilizada para almacenar los tokens de MemberDef.</span><span class="sxs-lookup"><span data-stu-id="d539e-109">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="d539e-110">[in] Tamaño máximo de la matriz `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="d539e-110">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="d539e-111">[out] El número real de los tokens de MemberDef devueltos en `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="d539e-111">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d539e-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d539e-112">Remarks</span></span>  
 <span data-ttu-id="d539e-113">Este método enumera campos y métodos, pero no propiedades o eventos.</span><span class="sxs-lookup"><span data-stu-id="d539e-113">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="d539e-114">A diferencia de [IMetaDataImport:: EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` descarta todos los tokens de campo y miembro que no tiene el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="d539e-114">Unlike [IMetaDataImport::EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` discards all field and member tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d539e-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d539e-115">Return Value</span></span>  
  
|<span data-ttu-id="d539e-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d539e-116">HRESULT</span></span>|<span data-ttu-id="d539e-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="d539e-117">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="d539e-118">`EnumTypeDefs`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="d539e-118">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="d539e-119">No hay ningún tokens de MemberDef que enumerar.</span><span class="sxs-lookup"><span data-stu-id="d539e-119">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="d539e-120">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="d539e-120">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d539e-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d539e-121">Requirements</span></span>  
 <span data-ttu-id="d539e-122">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d539e-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d539e-123">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d539e-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d539e-124">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d539e-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d539e-125">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d539e-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d539e-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="d539e-126">See Also</span></span>  
 [<span data-ttu-id="d539e-127">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d539e-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="d539e-128">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d539e-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
