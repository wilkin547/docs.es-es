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
ms.openlocfilehash: ea451bdd645d2d4dea4c5dd00408e0bc51804803
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492075"
---
# <a name="imetadataimportenummemberswithname-method"></a><span data-ttu-id="fe7dc-102">IMetaDataImport::EnumMembersWithName (Método)</span><span class="sxs-lookup"><span data-stu-id="fe7dc-102">IMetaDataImport::EnumMembersWithName Method</span></span>
<span data-ttu-id="fe7dc-103">Enumera los tokens de MemberDef que representan a miembros del tipo especificado con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="fe7dc-103">Enumerates MemberDef tokens representing members of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe7dc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fe7dc-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="fe7dc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fe7dc-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="fe7dc-106">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="fe7dc-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="fe7dc-107">de Un token de TypeDef que representa el tipo con miembros que se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="fe7dc-107">[in] A TypeDef token representing the type with members to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="fe7dc-108">de Nombre del miembro que limita el ámbito del enumerador.</span><span class="sxs-lookup"><span data-stu-id="fe7dc-108">[in] The member name that limits the scope of the enumerator.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="fe7dc-109">enuncia Matriz utilizada para almacenar los tokens de MemberDef.</span><span class="sxs-lookup"><span data-stu-id="fe7dc-109">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="fe7dc-110">[in] Tamaño máximo de la matriz `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="fe7dc-110">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="fe7dc-111">enuncia Número real de tokens de MemberDef devueltos en `rMembers` .</span><span class="sxs-lookup"><span data-stu-id="fe7dc-111">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe7dc-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fe7dc-112">Remarks</span></span>  
 <span data-ttu-id="fe7dc-113">Este método enumera los campos y métodos, pero no las propiedades o los eventos.</span><span class="sxs-lookup"><span data-stu-id="fe7dc-113">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="fe7dc-114">A diferencia de [IMetaDataImport:: EnumMembers (](imetadataimport-enummembers-method.md), `EnumMembersWithName` descarta todos los tokens de campo y miembro que no tienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="fe7dc-114">Unlike [IMetaDataImport::EnumMembers](imetadataimport-enummembers-method.md), `EnumMembersWithName` discards all field and member tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe7dc-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fe7dc-115">Return Value</span></span>  
  
|<span data-ttu-id="fe7dc-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fe7dc-116">HRESULT</span></span>|<span data-ttu-id="fe7dc-117">Description</span><span class="sxs-lookup"><span data-stu-id="fe7dc-117">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="fe7dc-118">`EnumTypeDefs`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="fe7dc-118">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="fe7dc-119">No hay tokens de MemberDef que enumerar.</span><span class="sxs-lookup"><span data-stu-id="fe7dc-119">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="fe7dc-120">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="fe7dc-120">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fe7dc-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fe7dc-121">Requirements</span></span>  
 <span data-ttu-id="fe7dc-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe7dc-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe7dc-123">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fe7dc-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fe7dc-124">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fe7dc-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fe7dc-125">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe7dc-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe7dc-126">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="fe7dc-126">See also</span></span>

- [<span data-ttu-id="fe7dc-127">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fe7dc-127">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="fe7dc-128">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fe7dc-128">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
