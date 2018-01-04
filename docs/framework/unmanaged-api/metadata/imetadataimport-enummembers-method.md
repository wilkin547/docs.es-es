---
title: "IMetaDataImport::EnumMembers (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumMembers
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumMembers
helpviewer_keywords:
- IMetaDataImport::EnumMembers method [.NET Framework metadata]
- EnumMembers method [.NET Framework metadata]
ms.assetid: 3fb8e178-342b-4c89-9bcf-f7f834e6cb77
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: aa7dabad0e555fe965cba4e5cbc69c10c9826b8e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenummembers-method"></a><span data-ttu-id="e9b32-102">IMetaDataImport::EnumMembers (Método)</span><span class="sxs-lookup"><span data-stu-id="e9b32-102">IMetaDataImport::EnumMembers Method</span></span>
<span data-ttu-id="e9b32-103">Enumera los tokens de MemberDef que representan a miembros del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="e9b32-103">Enumerates MemberDef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9b32-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e9b32-104">Syntax</span></span>  
  
```  
HRESULT EnumMembers (   
   [in, out]  HCORENUM    *phEnum,   
   [in]  mdTypeDef   cl,   
   [out] mdToken     rMembers[],   
   [in]  ULONG       cMax,   
   [out] ULONG       *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e9b32-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e9b32-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="e9b32-106">[entrada, salida] Un puntero para el enumerador.</span><span class="sxs-lookup"><span data-stu-id="e9b32-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="e9b32-107">[in] Un token de TypeDef que representa el tipo cuyos miembros se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="e9b32-107">[in] A TypeDef token representing the type whose members are to be enumerated.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="e9b32-108">[out] La matriz que se usa para contener los tokens de MemberDef.</span><span class="sxs-lookup"><span data-stu-id="e9b32-108">[out] The array used to hold the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="e9b32-109">[in] Tamaño máximo de la matriz `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="e9b32-109">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="e9b32-110">[out] El número real de los tokens de MemberDef devueltos en `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="e9b32-110">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e9b32-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e9b32-111">Return Value</span></span>  
  
|<span data-ttu-id="e9b32-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e9b32-112">HRESULT</span></span>|<span data-ttu-id="e9b32-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="e9b32-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="e9b32-114">`EnumMembers`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="e9b32-114">`EnumMembers` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="e9b32-115">No hay ningún tokens de MemberDef que enumerar.</span><span class="sxs-lookup"><span data-stu-id="e9b32-115">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="e9b32-116">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="e9b32-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9b32-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e9b32-117">Remarks</span></span>  
 <span data-ttu-id="e9b32-118">Al enumerar colecciones de miembros para una clase, `EnumMembers` devuelve solo los miembros definidos directamente en la clase.</span><span class="sxs-lookup"><span data-stu-id="e9b32-118">When enumerating collections of members for a class, `EnumMembers` returns only members defined directly on the class.</span></span> <span data-ttu-id="e9b32-119">No devuelve a los miembros que hereda de la clase, incluso si la clase proporciona una implementación para esos miembros heredados.</span><span class="sxs-lookup"><span data-stu-id="e9b32-119">It does not return any members that the class inherits, even if the class provides an implementation for those inherited members.</span></span> <span data-ttu-id="e9b32-120">Para enumerar los miembros heredados, el llamador debe recorrer explícitamente la cadena de herencia.</span><span class="sxs-lookup"><span data-stu-id="e9b32-120">To enumerate inherited members, the caller must explicitly walk the inheritance chain.</span></span> <span data-ttu-id="e9b32-121">Tenga en cuenta que las reglas de la cadena de herencia pueden variar en función del idioma o el compilador que genera los metadatos originales.</span><span class="sxs-lookup"><span data-stu-id="e9b32-121">Note that the rules for the inheritance chain may vary depending on the language or compiler that emitted the original metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9b32-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e9b32-122">Requirements</span></span>  
 <span data-ttu-id="e9b32-123">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9b32-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9b32-124">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e9b32-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e9b32-125">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e9b32-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e9b32-126">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9b32-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9b32-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9b32-127">See Also</span></span>  
 [<span data-ttu-id="e9b32-128">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e9b32-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="e9b32-129">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e9b32-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
