---
title: IMetaDataImport::EnumMemberRefs (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: 743b6bed1a5d62f5214b8366b1a3c6e4ebecb98b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441721"
---
# <a name="imetadataimportenummemberrefs-method"></a><span data-ttu-id="f10f3-102">IMetaDataImport::EnumMemberRefs (Método)</span><span class="sxs-lookup"><span data-stu-id="f10f3-102">IMetaDataImport::EnumMemberRefs Method</span></span>
<span data-ttu-id="f10f3-103">Enumera los tokens de MemberRef que representan a miembros del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="f10f3-103">Enumerates MemberRef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f10f3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f10f3-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemberRefs (  
   [in, out] HCORENUM    *phEnum,   
   [in]   mdToken        tkParent,   
   [out]  mdMemberRef    rMemberRefs[],   
   [in]   ULONG          cMax,   
   [out]  ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f10f3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f10f3-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="f10f3-106">[in, out] A pointer to the enumerator.</span><span class="sxs-lookup"><span data-stu-id="f10f3-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="f10f3-107">[in] A TypeDef, TypeRef, MethodDef, or ModuleRef token for the type whose members are to be enumerated.</span><span class="sxs-lookup"><span data-stu-id="f10f3-107">[in] A TypeDef, TypeRef, MethodDef, or ModuleRef token for the type whose members are to be enumerated.</span></span>  
  
 `rMemberRefs`  
 <span data-ttu-id="f10f3-108">[out] The array used to store MemberRef tokens.</span><span class="sxs-lookup"><span data-stu-id="f10f3-108">[out] The array used to store MemberRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f10f3-109">[in] Tamaño máximo de la matriz `rMemberRefs`.</span><span class="sxs-lookup"><span data-stu-id="f10f3-109">[in] The maximum size of the `rMemberRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="f10f3-110">[out] The actual number of MemberRef tokens returned in `rMemberRefs`.</span><span class="sxs-lookup"><span data-stu-id="f10f3-110">[out] The actual number of MemberRef tokens returned in `rMemberRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f10f3-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f10f3-111">Return Value</span></span>  
  
|<span data-ttu-id="f10f3-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f10f3-112">HRESULT</span></span>|<span data-ttu-id="f10f3-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="f10f3-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="f10f3-114">`EnumMemberRefs` returned successfully.</span><span class="sxs-lookup"><span data-stu-id="f10f3-114">`EnumMemberRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="f10f3-115">There are no MemberRef tokens to enumerate.</span><span class="sxs-lookup"><span data-stu-id="f10f3-115">There are no MemberRef tokens to enumerate.</span></span> <span data-ttu-id="f10f3-116">In that case, `pcTokens` is to zero.</span><span class="sxs-lookup"><span data-stu-id="f10f3-116">In that case, `pcTokens` is to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f10f3-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f10f3-117">Requirements</span></span>  
 <span data-ttu-id="f10f3-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f10f3-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f10f3-119">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f10f3-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f10f3-120">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f10f3-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f10f3-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f10f3-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f10f3-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="f10f3-122">See also</span></span>

- [<span data-ttu-id="f10f3-123">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f10f3-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="f10f3-124">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f10f3-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
