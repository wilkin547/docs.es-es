---
title: IMetaDataImport::EnumMembersWithName (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMembersWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMembersWithName
helpviewer_keywords:
- IMetaDataImport::EnumMembersWithName method [.NET Framework metadata]
- EnumMembersWithName method [.NET Framework metadata]
ms.assetid: 7c9e9120-3104-42f0-86ce-19a025f20dcc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 737ccc8af41c9eca765a7ea06f29d1aec1ccfad6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758853"
---
# <a name="imetadataimportenummemberswithname-method"></a><span data-ttu-id="5ee58-102">IMetaDataImport::EnumMembersWithName (Método)</span><span class="sxs-lookup"><span data-stu-id="5ee58-102">IMetaDataImport::EnumMembersWithName Method</span></span>
<span data-ttu-id="5ee58-103">Enumera los tokens de MemberDef que representan a miembros del tipo especificado con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="5ee58-103">Enumerates MemberDef tokens representing members of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ee58-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5ee58-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMembersWithName (  
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   cl,   
   [in]      LPCWSTR     szName,   
   [out]     mdToken     rMembers[],   
   [in]      ULONG       cMax,   
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ee58-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5ee58-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="5ee58-106">[in, out] Un puntero en el enumerador.</span><span class="sxs-lookup"><span data-stu-id="5ee58-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="5ee58-107">[in] Un token de TypeDef que representa el tipo con miembros para enumerar.</span><span class="sxs-lookup"><span data-stu-id="5ee58-107">[in] A TypeDef token representing the type with members to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="5ee58-108">[in] El nombre de miembro que limita el ámbito del enumerador.</span><span class="sxs-lookup"><span data-stu-id="5ee58-108">[in] The member name that limits the scope of the enumerator.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="5ee58-109">[out] Matriz utilizada para almacenar los tokens de MemberDef.</span><span class="sxs-lookup"><span data-stu-id="5ee58-109">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="5ee58-110">[in] Tamaño máximo de la matriz `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="5ee58-110">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="5ee58-111">[out] El número real de los tokens de MemberDef devueltos en `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="5ee58-111">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ee58-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5ee58-112">Remarks</span></span>  
 <span data-ttu-id="5ee58-113">Este método enumera los campos y métodos, pero no las propiedades o eventos.</span><span class="sxs-lookup"><span data-stu-id="5ee58-113">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="5ee58-114">A diferencia de [EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` descarta todos los tokens de campo y los miembros que no tienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="5ee58-114">Unlike [IMetaDataImport::EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` discards all field and member tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5ee58-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5ee58-115">Return Value</span></span>  
  
|<span data-ttu-id="5ee58-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5ee58-116">HRESULT</span></span>|<span data-ttu-id="5ee58-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5ee58-117">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="5ee58-118">`EnumTypeDefs` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="5ee58-118">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="5ee58-119">No hay ningún token MemberDef para enumerar.</span><span class="sxs-lookup"><span data-stu-id="5ee58-119">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="5ee58-120">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="5ee58-120">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5ee58-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5ee58-121">Requirements</span></span>  
 <span data-ttu-id="5ee58-122">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ee58-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ee58-123">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="5ee58-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5ee58-124">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5ee58-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5ee58-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ee58-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ee58-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ee58-126">See also</span></span>

- [<span data-ttu-id="5ee58-127">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5ee58-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="5ee58-128">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5ee58-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
