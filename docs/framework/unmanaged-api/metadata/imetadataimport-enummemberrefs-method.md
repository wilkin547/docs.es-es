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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a08577f15a6fab0e630d40032a23c273ee935faa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992334"
---
# <a name="imetadataimportenummemberrefs-method"></a><span data-ttu-id="6b802-102">IMetaDataImport::EnumMemberRefs (Método)</span><span class="sxs-lookup"><span data-stu-id="6b802-102">IMetaDataImport::EnumMemberRefs Method</span></span>
<span data-ttu-id="6b802-103">Enumera los tokens de MemberRef que representan a miembros del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="6b802-103">Enumerates MemberRef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b802-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6b802-104">Syntax</span></span>  
  
```  
HRESULT EnumMemberRefs (  
   [in, out] HCORENUM    *phEnum,   
   [in]   mdToken        tkParent,   
   [out]  mdMemberRef    rMemberRefs[],   
   [in]   ULONG          cMax,   
   [out]  ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b802-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6b802-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="6b802-106">[in, out] Un puntero en el enumerador.</span><span class="sxs-lookup"><span data-stu-id="6b802-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="6b802-107">[in] Un token de TypeDef, TypeRef, MethodDef o ModuleRef para el tipo cuyos miembros se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="6b802-107">[in] A TypeDef, TypeRef, MethodDef, or ModuleRef token for the type whose members are to be enumerated.</span></span>  
  
 `rMemberRefs`  
 <span data-ttu-id="6b802-108">[out] Matriz utilizada para almacenar los tokens de MemberRef.</span><span class="sxs-lookup"><span data-stu-id="6b802-108">[out] The array used to store MemberRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="6b802-109">[in] Tamaño máximo de la matriz `rMemberRefs`.</span><span class="sxs-lookup"><span data-stu-id="6b802-109">[in] The maximum size of the `rMemberRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="6b802-110">[out] El número real de los tokens de MemberRef devueltos en `rMemberRefs`.</span><span class="sxs-lookup"><span data-stu-id="6b802-110">[out] The actual number of MemberRef tokens returned in `rMemberRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6b802-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6b802-111">Return Value</span></span>  
  
|<span data-ttu-id="6b802-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6b802-112">HRESULT</span></span>|<span data-ttu-id="6b802-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="6b802-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="6b802-114">`EnumMemberRefs` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="6b802-114">`EnumMemberRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="6b802-115">No hay ningún token MemberRef para enumerar.</span><span class="sxs-lookup"><span data-stu-id="6b802-115">There are no MemberRef tokens to enumerate.</span></span> <span data-ttu-id="6b802-116">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="6b802-116">In that case, `pcTokens` is to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6b802-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6b802-117">Requirements</span></span>  
 <span data-ttu-id="6b802-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b802-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b802-119">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="6b802-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6b802-120">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6b802-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6b802-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b802-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b802-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b802-122">See also</span></span>

- [<span data-ttu-id="6b802-123">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6b802-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="6b802-124">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6b802-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
