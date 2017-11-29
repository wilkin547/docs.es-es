---
title: "IMetaDataImport::FindMemberRef (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.FindMemberRef
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::FindMemberRef
helpviewer_keywords:
- IMetaDataImport::FindMemberRef method [.NET Framework metadata]
- FindMemberRef method [.NET Framework metadata]
ms.assetid: 1ccda329-d752-4d89-abe8-511af3c3f4c9
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: efb8a3a74997c6894eff6fafb87e933a6d2cf7bc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportfindmemberref-method"></a><span data-ttu-id="43b0c-102">IMetaDataImport::FindMemberRef (Método)</span><span class="sxs-lookup"><span data-stu-id="43b0c-102">IMetaDataImport::FindMemberRef Method</span></span>
<span data-ttu-id="43b0c-103">Obtiene un puntero al token MemberRef para el miembro de referencia que es delimitadas por especificado <xref:System.Type> y que tiene la firma de nombre y los metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="43b0c-103">Gets a pointer to the MemberRef token for the member reference that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43b0c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="43b0c-104">Syntax</span></span>  
  
```  
HRESULT FindMemberRef (  
   [in]  mdTypeRef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMemberRef        *pmr  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="43b0c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="43b0c-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="43b0c-106">[in] Símbolo (token) de TypeRef para la clase o interfaz que incluye la referencia de miembro que se busca.</span><span class="sxs-lookup"><span data-stu-id="43b0c-106">[in] The TypeRef token for the class or interface that encloses the member reference to search for.</span></span> <span data-ttu-id="43b0c-107">Si este valor es `mdTokenNil`, la búsqueda se realiza para una variable global o una referencia de función global.</span><span class="sxs-lookup"><span data-stu-id="43b0c-107">If this value is `mdTokenNil`, the lookup is done for a global variable or a global-function reference.</span></span>  
  
 `szName`  
 <span data-ttu-id="43b0c-108">[in] El nombre de la referencia de miembro que se busca.</span><span class="sxs-lookup"><span data-stu-id="43b0c-108">[in] The name of the member reference to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="43b0c-109">[in] Un puntero a la firma de metadatos binaria de la referencia de miembro.</span><span class="sxs-lookup"><span data-stu-id="43b0c-109">[in] A pointer to the binary metadata signature of the member reference.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="43b0c-110">[in] El tamaño en bytes de `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="43b0c-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="43b0c-111">[out] Un puntero al token MemberRef coincidente.</span><span class="sxs-lookup"><span data-stu-id="43b0c-111">[out] A pointer to the matching MemberRef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43b0c-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="43b0c-112">Remarks</span></span>  
 <span data-ttu-id="43b0c-113">Especificar el miembro con su clase o interfaz envolvente (`td`), su nombre (`szName`) y, opcionalmente, su firma (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="43b0c-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="43b0c-114">La firma se pasa a `FindMemberRef` deben haberse generado en el ámbito actual, porque las firmas están enlazadas a un ámbito determinado.</span><span class="sxs-lookup"><span data-stu-id="43b0c-114">The signature passed to `FindMemberRef` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="43b0c-115">Una firma puede incrustar un símbolo (token) que identifica el tipo de valor o clase envolvente.</span><span class="sxs-lookup"><span data-stu-id="43b0c-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="43b0c-116">El token es un índice en la tabla TypeDef local.</span><span class="sxs-lookup"><span data-stu-id="43b0c-116">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="43b0c-117">No se puede compilar una firma en tiempo de ejecución fuera del contexto del ámbito actual y utilizar esa firma como entrada para `FindMemberRef`.</span><span class="sxs-lookup"><span data-stu-id="43b0c-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindMemberRef`.</span></span>  
  
 <span data-ttu-id="43b0c-118">`FindMemberRef`Busca solo las referencias de miembro que se definieron directamente en la clase o interfaz; Si no encuentra referencias de miembro heredadas.</span><span class="sxs-lookup"><span data-stu-id="43b0c-118">`FindMemberRef` finds only member references that were defined directly in the class or interface; it does not find inherited member references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43b0c-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="43b0c-119">Requirements</span></span>  
 <span data-ttu-id="43b0c-120">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43b0c-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43b0c-121">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="43b0c-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="43b0c-122">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="43b0c-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="43b0c-123">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43b0c-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43b0c-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="43b0c-124">See Also</span></span>  
 [<span data-ttu-id="43b0c-125">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="43b0c-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="43b0c-126">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="43b0c-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
