---
title: "IMetaDataImport::FindMember (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataImport.FindMember
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMember
helpviewer_keywords:
- IMetaDataImport::FindMember method [.NET Framework metadata]
- FindMember method [.NET Framework metadata]
ms.assetid: ad32fb84-c2b6-41cd-888d-787ff3a90449
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a20930688aed210309a719de2c7187f1f5fd1f24
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportfindmember-method"></a><span data-ttu-id="a13f9-102">IMetaDataImport::FindMember (Método)</span><span class="sxs-lookup"><span data-stu-id="a13f9-102">IMetaDataImport::FindMember Method</span></span>
<span data-ttu-id="a13f9-103">Obtiene un puntero al MemberDef símbolo (token) de campo o un método que se encierra entre según los valores especificados <xref:System.Type> y que tiene la firma de nombre y los metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="a13f9-103">Gets a pointer to the MemberDef token for field or method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a13f9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a13f9-104">Syntax</span></span>  
  
```  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,   
   [in]  PCCOR_SIGNATURE   pvSigBlob,   
   [in]  ULONG             cbSigBlob,   
   [out] mdToken           *pmb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a13f9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a13f9-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="a13f9-106">[in] El token de TypeDef para la clase o interfaz que incluye el miembro que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="a13f9-106">[in] The TypeDef token for the class or interface that encloses the member to search for.</span></span> <span data-ttu-id="a13f9-107">Si este valor es `mdTokenNil`, la búsqueda se realiza para una variable global o una función global.</span><span class="sxs-lookup"><span data-stu-id="a13f9-107">If this value is `mdTokenNil`, the lookup is done for a global-variable or global-function.</span></span>  
  
 `szName`  
 <span data-ttu-id="a13f9-108">[in] El nombre del miembro que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="a13f9-108">[in] The name of the member to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="a13f9-109">[in] Un puntero a la firma de metadatos binaria del miembro.</span><span class="sxs-lookup"><span data-stu-id="a13f9-109">[in] A pointer to the binary metadata signature of the member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="a13f9-110">[in] El tamaño en bytes de `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="a13f9-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="a13f9-111">[out] Un puntero al token MemberDef coincidente.</span><span class="sxs-lookup"><span data-stu-id="a13f9-111">[out] A pointer to the matching MemberDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a13f9-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a13f9-112">Remarks</span></span>  
 <span data-ttu-id="a13f9-113">Especificar el miembro con su clase o interfaz envolvente (`td`), su nombre (`szName`) y, opcionalmente, su firma (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="a13f9-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="a13f9-114">Puede haber varios miembros con el mismo nombre en una clase o interfaz.</span><span class="sxs-lookup"><span data-stu-id="a13f9-114">There might be multiple members with the same name in a class or interface.</span></span> <span data-ttu-id="a13f9-115">En ese caso, pase la firma del miembro para encontrar a una coincidencia única.</span><span class="sxs-lookup"><span data-stu-id="a13f9-115">In that case, pass the member's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="a13f9-116">La firma se pasa a `FindMember` deben haberse generado en el ámbito actual, porque las firmas están enlazadas a un ámbito determinado.</span><span class="sxs-lookup"><span data-stu-id="a13f9-116">The signature passed to `FindMember` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="a13f9-117">Una firma puede incrustar un símbolo (token) que identifica el tipo de valor o clase envolvente.</span><span class="sxs-lookup"><span data-stu-id="a13f9-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="a13f9-118">El token es un índice en la tabla TypeDef local.</span><span class="sxs-lookup"><span data-stu-id="a13f9-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="a13f9-119">No se puede compilar una firma en tiempo de ejecución fuera del contexto del ámbito actual y use esa firma como entrada a `FindMember`.</span><span class="sxs-lookup"><span data-stu-id="a13f9-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMember`.</span></span>  
  
 <span data-ttu-id="a13f9-120">`FindMember`busca a solo los miembros que se definieron directamente en la clase o interfaz; Si no encuentra los miembros heredados.</span><span class="sxs-lookup"><span data-stu-id="a13f9-120">`FindMember` finds only members that were defined directly in the class or interface; it does not find inherited members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a13f9-121">`FindMember`es un método auxiliar.</span><span class="sxs-lookup"><span data-stu-id="a13f9-121">`FindMember` is a helper method.</span></span> <span data-ttu-id="a13f9-122">Llama [IMetaDataImport:: FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); si esa llamada no encuentra una coincidencia, `FindMember` , a continuación, se llama [FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).</span><span class="sxs-lookup"><span data-stu-id="a13f9-122">It calls [IMetaDataImport::FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); if that call does not find a match, `FindMember` then calls [IMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a13f9-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a13f9-123">Requirements</span></span>  
 <span data-ttu-id="a13f9-124">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a13f9-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a13f9-125">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a13f9-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a13f9-126">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a13f9-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a13f9-127">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a13f9-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a13f9-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="a13f9-128">See Also</span></span>  
 [<span data-ttu-id="a13f9-129">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a13f9-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="a13f9-130">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a13f9-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
