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
ms.openlocfilehash: b8a65b0748fec0e474d8b3b5dc03473fbd716108
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177330"
---
# <a name="imetadataimportenummemberrefs-method"></a><span data-ttu-id="eaf5d-102">IMetaDataImport::EnumMemberRefs (Método)</span><span class="sxs-lookup"><span data-stu-id="eaf5d-102">IMetaDataImport::EnumMemberRefs Method</span></span>
<span data-ttu-id="eaf5d-103">Enumera los tokens de MemberRef que representan a miembros del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="eaf5d-103">Enumerates MemberRef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eaf5d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eaf5d-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemberRefs (  
   [in, out] HCORENUM    *phEnum,
   [in]   mdToken        tkParent,
   [out]  mdMemberRef    rMemberRefs[],
   [in]   ULONG          cMax,
   [out]  ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eaf5d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="eaf5d-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="eaf5d-106">[adentro, fuera] Un puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="eaf5d-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="eaf5d-107">[en] Un typeDef, TypeRef, MethodDef, o ModuleRef token para el tipo cuyos miembros se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="eaf5d-107">[in] A TypeDef, TypeRef, MethodDef, or ModuleRef token for the type whose members are to be enumerated.</span></span>  
  
 `rMemberRefs`  
 <span data-ttu-id="eaf5d-108">[fuera] Matriz utilizada para almacenar tokens MemberRef.</span><span class="sxs-lookup"><span data-stu-id="eaf5d-108">[out] The array used to store MemberRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="eaf5d-109">[in] Tamaño máximo de la matriz `rMemberRefs`.</span><span class="sxs-lookup"><span data-stu-id="eaf5d-109">[in] The maximum size of the `rMemberRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="eaf5d-110">[fuera] El número real de tokens `rMemberRefs`MemberRef devueltos en .</span><span class="sxs-lookup"><span data-stu-id="eaf5d-110">[out] The actual number of MemberRef tokens returned in `rMemberRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eaf5d-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="eaf5d-111">Return Value</span></span>  
  
|<span data-ttu-id="eaf5d-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="eaf5d-112">HRESULT</span></span>|<span data-ttu-id="eaf5d-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="eaf5d-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="eaf5d-114">`EnumMemberRefs`regresó con éxito.</span><span class="sxs-lookup"><span data-stu-id="eaf5d-114">`EnumMemberRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="eaf5d-115">No hay tokens MemberRef para enumerar.</span><span class="sxs-lookup"><span data-stu-id="eaf5d-115">There are no MemberRef tokens to enumerate.</span></span> <span data-ttu-id="eaf5d-116">En ese `pcTokens` caso, es a cero.</span><span class="sxs-lookup"><span data-stu-id="eaf5d-116">In that case, `pcTokens` is to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eaf5d-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eaf5d-117">Requirements</span></span>  
 <span data-ttu-id="eaf5d-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eaf5d-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eaf5d-119">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="eaf5d-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="eaf5d-120">**Biblioteca:** Incluido como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="eaf5d-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="eaf5d-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eaf5d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaf5d-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eaf5d-122">See also</span></span>

- [<span data-ttu-id="eaf5d-123">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="eaf5d-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="eaf5d-124">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="eaf5d-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
