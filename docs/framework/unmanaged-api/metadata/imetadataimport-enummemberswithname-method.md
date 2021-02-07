---
description: 'Más información sobre: IMetaDataImport:: EnumMembersWithName ((método)'
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
ms.openlocfilehash: bb6d8f0769029dccaf1f52dd211c67d47bf32a73
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99670767"
---
# <a name="imetadataimportenummemberswithname-method"></a><span data-ttu-id="ba3f0-103">IMetaDataImport::EnumMembersWithName (Método)</span><span class="sxs-lookup"><span data-stu-id="ba3f0-103">IMetaDataImport::EnumMembersWithName Method</span></span>

<span data-ttu-id="ba3f0-104">Enumera los tokens de MemberDef que representan a miembros del tipo especificado con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="ba3f0-104">Enumerates MemberDef tokens representing members of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba3f0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ba3f0-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="ba3f0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ba3f0-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="ba3f0-107">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="ba3f0-107">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="ba3f0-108">de Un token de TypeDef que representa el tipo con miembros que se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="ba3f0-108">[in] A TypeDef token representing the type with members to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="ba3f0-109">de Nombre del miembro que limita el ámbito del enumerador.</span><span class="sxs-lookup"><span data-stu-id="ba3f0-109">[in] The member name that limits the scope of the enumerator.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="ba3f0-110">enuncia Matriz utilizada para almacenar los tokens de MemberDef.</span><span class="sxs-lookup"><span data-stu-id="ba3f0-110">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ba3f0-111">[in] Tamaño máximo de la matriz `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="ba3f0-111">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="ba3f0-112">enuncia Número real de tokens de MemberDef devueltos en `rMembers` .</span><span class="sxs-lookup"><span data-stu-id="ba3f0-112">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ba3f0-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ba3f0-113">Remarks</span></span>  

 <span data-ttu-id="ba3f0-114">Este método enumera los campos y métodos, pero no las propiedades o los eventos.</span><span class="sxs-lookup"><span data-stu-id="ba3f0-114">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="ba3f0-115">A diferencia de [IMetaDataImport:: EnumMembers (](imetadataimport-enummembers-method.md), `EnumMembersWithName` descarta todos los tokens de campo y miembro que no tienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="ba3f0-115">Unlike [IMetaDataImport::EnumMembers](imetadataimport-enummembers-method.md), `EnumMembersWithName` discards all field and member tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba3f0-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ba3f0-116">Return Value</span></span>  
  
|<span data-ttu-id="ba3f0-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ba3f0-117">HRESULT</span></span>|<span data-ttu-id="ba3f0-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="ba3f0-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="ba3f0-119">`EnumTypeDefs` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="ba3f0-119">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="ba3f0-120">No hay tokens de MemberDef que enumerar.</span><span class="sxs-lookup"><span data-stu-id="ba3f0-120">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="ba3f0-121">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="ba3f0-121">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ba3f0-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ba3f0-122">Requirements</span></span>  

 <span data-ttu-id="ba3f0-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba3f0-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba3f0-124">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ba3f0-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ba3f0-125">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ba3f0-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ba3f0-126">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba3f0-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba3f0-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba3f0-127">See also</span></span>

- [<span data-ttu-id="ba3f0-128">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ba3f0-128">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="ba3f0-129">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ba3f0-129">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
