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
ms.openlocfilehash: 7410f91a853f3a677a105dc2e12a86d723c9fad6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177318"
---
# <a name="imetadataimportenummemberswithname-method"></a><span data-ttu-id="3c893-102">IMetaDataImport::EnumMembersWithName (Método)</span><span class="sxs-lookup"><span data-stu-id="3c893-102">IMetaDataImport::EnumMembersWithName Method</span></span>
<span data-ttu-id="3c893-103">Enumera los tokens de MemberDef que representan a miembros del tipo especificado con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="3c893-103">Enumerates MemberDef tokens representing members of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c893-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3c893-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="3c893-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3c893-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="3c893-106">[adentro, fuera] Un puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="3c893-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="3c893-107">[en] Un token TypeDef que representa el tipo con miembros que se va a enumerar.</span><span class="sxs-lookup"><span data-stu-id="3c893-107">[in] A TypeDef token representing the type with members to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="3c893-108">[en] El nombre de miembro que limita el ámbito del enumerador.</span><span class="sxs-lookup"><span data-stu-id="3c893-108">[in] The member name that limits the scope of the enumerator.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="3c893-109">[fuera] Matriz utilizada para almacenar los tokens MemberDef.</span><span class="sxs-lookup"><span data-stu-id="3c893-109">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="3c893-110">[in] Tamaño máximo de la matriz `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="3c893-110">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="3c893-111">[fuera] El número real de tokens `rMembers`MemberDef devueltos en .</span><span class="sxs-lookup"><span data-stu-id="3c893-111">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c893-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3c893-112">Remarks</span></span>  
 <span data-ttu-id="3c893-113">Este método enumera campos y métodos, pero no propiedades o eventos.</span><span class="sxs-lookup"><span data-stu-id="3c893-113">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="3c893-114">A diferencia de [IMetaDataImport::EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` descarta todos los tokens de campo y miembro que no tienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="3c893-114">Unlike [IMetaDataImport::EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` discards all field and member tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c893-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3c893-115">Return Value</span></span>  
  
|<span data-ttu-id="3c893-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3c893-116">HRESULT</span></span>|<span data-ttu-id="3c893-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="3c893-117">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="3c893-118">`EnumTypeDefs`regresó con éxito.</span><span class="sxs-lookup"><span data-stu-id="3c893-118">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="3c893-119">No hay tokens MemberDef que enumerar.</span><span class="sxs-lookup"><span data-stu-id="3c893-119">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="3c893-120">En ese `pcTokens` caso, es cero.</span><span class="sxs-lookup"><span data-stu-id="3c893-120">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3c893-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3c893-121">Requirements</span></span>  
 <span data-ttu-id="3c893-122">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c893-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c893-123">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3c893-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3c893-124">**Biblioteca:** Incluido como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3c893-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3c893-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c893-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c893-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3c893-126">See also</span></span>

- [<span data-ttu-id="3c893-127">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3c893-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="3c893-128">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3c893-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
