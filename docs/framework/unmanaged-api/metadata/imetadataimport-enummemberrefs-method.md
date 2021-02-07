---
description: 'Más información sobre: IMetaDataImport:: EnumMemberRefs ((método)'
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
ms.openlocfilehash: 0c9b10342f73ae5b604ac25b6ff8ccec58deb5ab
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99670949"
---
# <a name="imetadataimportenummemberrefs-method"></a><span data-ttu-id="8b9dc-103">IMetaDataImport::EnumMemberRefs (Método)</span><span class="sxs-lookup"><span data-stu-id="8b9dc-103">IMetaDataImport::EnumMemberRefs Method</span></span>

<span data-ttu-id="8b9dc-104">Enumera los tokens de MemberRef que representan a miembros del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="8b9dc-104">Enumerates MemberRef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b9dc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8b9dc-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemberRefs (  
   [in, out] HCORENUM    *phEnum,
   [in]   mdToken        tkParent,
   [out]  mdMemberRef    rMemberRefs[],
   [in]   ULONG          cMax,
   [out]  ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b9dc-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8b9dc-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="8b9dc-107">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="8b9dc-107">[in, out] A pointer to the enumerator.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="8b9dc-108">de Un token TypeDef, TypeRef, MethodDef o ModuleRef para el tipo cuyos miembros se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="8b9dc-108">[in] A TypeDef, TypeRef, MethodDef, or ModuleRef token for the type whose members are to be enumerated.</span></span>  
  
 `rMemberRefs`  
 <span data-ttu-id="8b9dc-109">enuncia Matriz utilizada para almacenar los tokens de MemberRef.</span><span class="sxs-lookup"><span data-stu-id="8b9dc-109">[out] The array used to store MemberRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="8b9dc-110">[in] Tamaño máximo de la matriz `rMemberRefs`.</span><span class="sxs-lookup"><span data-stu-id="8b9dc-110">[in] The maximum size of the `rMemberRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="8b9dc-111">enuncia Número real de tokens de MemberRef devueltos en `rMemberRefs` .</span><span class="sxs-lookup"><span data-stu-id="8b9dc-111">[out] The actual number of MemberRef tokens returned in `rMemberRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8b9dc-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8b9dc-112">Return Value</span></span>  
  
|<span data-ttu-id="8b9dc-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8b9dc-113">HRESULT</span></span>|<span data-ttu-id="8b9dc-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="8b9dc-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="8b9dc-115">`EnumMemberRefs` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="8b9dc-115">`EnumMemberRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="8b9dc-116">No hay tokens de MemberRef que enumerar.</span><span class="sxs-lookup"><span data-stu-id="8b9dc-116">There are no MemberRef tokens to enumerate.</span></span> <span data-ttu-id="8b9dc-117">En ese caso, `pcTokens` es a cero.</span><span class="sxs-lookup"><span data-stu-id="8b9dc-117">In that case, `pcTokens` is to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8b9dc-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8b9dc-118">Requirements</span></span>  

 <span data-ttu-id="8b9dc-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b9dc-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b9dc-120">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8b9dc-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8b9dc-121">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8b9dc-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8b9dc-122">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b9dc-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b9dc-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="8b9dc-123">See also</span></span>

- [<span data-ttu-id="8b9dc-124">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8b9dc-124">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="8b9dc-125">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8b9dc-125">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
