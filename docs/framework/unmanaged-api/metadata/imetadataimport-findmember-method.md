---
title: IMetaDataImport::FindMember (Método)
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 63afd82ca88e1a7c61913ec7fcc4d77d03ae9927
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183175"
---
# <a name="imetadataimportfindmember-method"></a><span data-ttu-id="58b4a-102">IMetaDataImport::FindMember (Método)</span><span class="sxs-lookup"><span data-stu-id="58b4a-102">IMetaDataImport::FindMember Method</span></span>
<span data-ttu-id="58b4a-103">Obtiene un puntero a MemberDef token para el campo o método que se incluye por especificado <xref:System.Type> y que tiene la firma de nombre y los metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="58b4a-103">Gets a pointer to the MemberDef token for field or method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58b4a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="58b4a-104">Syntax</span></span>  
  
```  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,   
   [in]  PCCOR_SIGNATURE   pvSigBlob,   
   [in]  ULONG             cbSigBlob,   
   [out] mdToken           *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58b4a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="58b4a-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="58b4a-106">[in] El token de TypeDef para la clase o interfaz que incluye el miembro que se busca.</span><span class="sxs-lookup"><span data-stu-id="58b4a-106">[in] The TypeDef token for the class or interface that encloses the member to search for.</span></span> <span data-ttu-id="58b4a-107">Si este valor es `mdTokenNil`, la búsqueda se realiza para una variable global o una función global.</span><span class="sxs-lookup"><span data-stu-id="58b4a-107">If this value is `mdTokenNil`, the lookup is done for a global-variable or global-function.</span></span>  
  
 `szName`  
 <span data-ttu-id="58b4a-108">[in] El nombre del miembro que se busca.</span><span class="sxs-lookup"><span data-stu-id="58b4a-108">[in] The name of the member to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="58b4a-109">[in] Un puntero a la firma de metadatos binaria del miembro.</span><span class="sxs-lookup"><span data-stu-id="58b4a-109">[in] A pointer to the binary metadata signature of the member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="58b4a-110">[in] El tamaño en bytes de `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="58b4a-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="58b4a-111">[out] Un puntero al token MemberDef coincidente.</span><span class="sxs-lookup"><span data-stu-id="58b4a-111">[out] A pointer to the matching MemberDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58b4a-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="58b4a-112">Remarks</span></span>  
 <span data-ttu-id="58b4a-113">Especifique el miembro con su clase o interfaz envolvente (`td`), su nombre (`szName`) y, opcionalmente, su firma (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="58b4a-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="58b4a-114">Puede haber varios miembros con el mismo nombre en una clase o interfaz.</span><span class="sxs-lookup"><span data-stu-id="58b4a-114">There might be multiple members with the same name in a class or interface.</span></span> <span data-ttu-id="58b4a-115">En ese caso, pase la firma del miembro para encontrar a una coincidencia única.</span><span class="sxs-lookup"><span data-stu-id="58b4a-115">In that case, pass the member's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="58b4a-116">La firma pasa a `FindMember` deben haberse generado en el ámbito actual, porque las firmas están enlazadas a un ámbito determinado.</span><span class="sxs-lookup"><span data-stu-id="58b4a-116">The signature passed to `FindMember` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="58b4a-117">Una firma puede incrustar un token que identifica el tipo de valor o la clase envolvente.</span><span class="sxs-lookup"><span data-stu-id="58b4a-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="58b4a-118">El token es un índice en la tabla TypeDef local.</span><span class="sxs-lookup"><span data-stu-id="58b4a-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="58b4a-119">No se puede generar una firma de tiempo de ejecución fuera del contexto del ámbito actual y use esa firma como entrada a `FindMember`.</span><span class="sxs-lookup"><span data-stu-id="58b4a-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMember`.</span></span>  
  
 <span data-ttu-id="58b4a-120">`FindMember` busca a solo los miembros que se definieron directamente en la clase o interfaz; no encuentra los miembros heredados.</span><span class="sxs-lookup"><span data-stu-id="58b4a-120">`FindMember` finds only members that were defined directly in the class or interface; it does not find inherited members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="58b4a-121">`FindMember` es un método auxiliar.</span><span class="sxs-lookup"><span data-stu-id="58b4a-121">`FindMember` is a helper method.</span></span> <span data-ttu-id="58b4a-122">Llama a [FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); si esa llamada no encuentra una coincidencia, `FindMember` , a continuación, llama a [FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).</span><span class="sxs-lookup"><span data-stu-id="58b4a-122">It calls [IMetaDataImport::FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); if that call does not find a match, `FindMember` then calls [IMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58b4a-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="58b4a-123">Requirements</span></span>  
 <span data-ttu-id="58b4a-124">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58b4a-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58b4a-125">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="58b4a-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="58b4a-126">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="58b4a-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="58b4a-127">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58b4a-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58b4a-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="58b4a-128">See also</span></span>

- [<span data-ttu-id="58b4a-129">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="58b4a-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="58b4a-130">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="58b4a-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
