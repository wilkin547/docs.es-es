---
title: "IMetaDataImport::EnumMemberRefs (Método)"
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
- IMetaDataImport.EnumMemberRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMemberRefs
helpviewer_keywords:
- EnumMemberRefs method [.NET Framework metadata]
- IMetaDataImport::EnumMemberRefs method [.NET Framework metadata]
ms.assetid: e97c97a6-6e4f-41f5-9af1-9b3cf3bdbd6b
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ea308db566e37d10cccdc2777b5a2374408a8ea6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenummemberrefs-method"></a><span data-ttu-id="8fc64-102">IMetaDataImport::EnumMemberRefs (Método)</span><span class="sxs-lookup"><span data-stu-id="8fc64-102">IMetaDataImport::EnumMemberRefs Method</span></span>
<span data-ttu-id="8fc64-103">Enumera los tokens de MemberRef que representan a miembros del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="8fc64-103">Enumerates MemberRef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fc64-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8fc64-104">Syntax</span></span>  
  
```  
HRESULT EnumMemberRefs (  
   [in, out] HCORENUM    *phEnum,   
   [in]   mdToken        tkParent,   
   [out]  mdMemberRef    rMemberRefs[],   
   [in]   ULONG          cMax,   
   [out]  ULONG          *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8fc64-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8fc64-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="8fc64-106">[entrada, salida] Un puntero para el enumerador.</span><span class="sxs-lookup"><span data-stu-id="8fc64-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="8fc64-107">[in] Símbolo (token) de TypeDef, TypeRef, MethodDef o ModuleRef para el tipo cuyos miembros se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="8fc64-107">[in] A TypeDef, TypeRef, MethodDef, or ModuleRef token for the type whose members are to be enumerated.</span></span>  
  
 `rMemberRefs`  
 <span data-ttu-id="8fc64-108">[out] La matriz que se utiliza para almacenar los tokens de MemberRef.</span><span class="sxs-lookup"><span data-stu-id="8fc64-108">[out] The array used to store MemberRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="8fc64-109">[in] Tamaño máximo de la matriz `rMemberRefs`.</span><span class="sxs-lookup"><span data-stu-id="8fc64-109">[in] The maximum size of the `rMemberRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="8fc64-110">[out] El número real de símbolos (tokens) de MemberRef devueltos en `rMemberRefs`.</span><span class="sxs-lookup"><span data-stu-id="8fc64-110">[out] The actual number of MemberRef tokens returned in `rMemberRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8fc64-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8fc64-111">Return Value</span></span>  
  
|<span data-ttu-id="8fc64-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8fc64-112">HRESULT</span></span>|<span data-ttu-id="8fc64-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="8fc64-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="8fc64-114">`EnumMemberRefs`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="8fc64-114">`EnumMemberRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="8fc64-115">No hay ningún tokens de MemberRef que enumerar.</span><span class="sxs-lookup"><span data-stu-id="8fc64-115">There are no MemberRef tokens to enumerate.</span></span> <span data-ttu-id="8fc64-116">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="8fc64-116">In that case, `pcTokens` is to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8fc64-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8fc64-117">Requirements</span></span>  
 <span data-ttu-id="8fc64-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8fc64-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fc64-119">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8fc64-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8fc64-120">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8fc64-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8fc64-121">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8fc64-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fc64-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="8fc64-122">See Also</span></span>  
 [<span data-ttu-id="8fc64-123">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8fc64-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="8fc64-124">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8fc64-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
