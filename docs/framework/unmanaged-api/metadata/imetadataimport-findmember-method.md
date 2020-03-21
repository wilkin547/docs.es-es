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
ms.openlocfilehash: dab155b82d87609b3d3f390133e6490502a43518
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177281"
---
# <a name="imetadataimportfindmember-method"></a><span data-ttu-id="f5e6a-102">IMetaDataImport::FindMember (Método)</span><span class="sxs-lookup"><span data-stu-id="f5e6a-102">IMetaDataImport::FindMember Method</span></span>
<span data-ttu-id="f5e6a-103">Obtiene un puntero al token MemberDef para el campo o <xref:System.Type> método que está incluido en el especificado y que tiene el nombre especificado y la firma de metadatos.</span><span class="sxs-lookup"><span data-stu-id="f5e6a-103">Gets a pointer to the MemberDef token for field or method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5e6a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f5e6a-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,
   [in]  PCCOR_SIGNATURE   pvSigBlob,
   [in]  ULONG             cbSigBlob,
   [out] mdToken           *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5e6a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f5e6a-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="f5e6a-106">[en] El token TypeDef para la clase o interfaz que encierra el miembro que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="f5e6a-106">[in] The TypeDef token for the class or interface that encloses the member to search for.</span></span> <span data-ttu-id="f5e6a-107">Si este `mdTokenNil`valor es , la búsqueda se realiza para una variable global o una función global.</span><span class="sxs-lookup"><span data-stu-id="f5e6a-107">If this value is `mdTokenNil`, the lookup is done for a global-variable or global-function.</span></span>  
  
 `szName`  
 <span data-ttu-id="f5e6a-108">[en] El nombre del miembro que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="f5e6a-108">[in] The name of the member to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="f5e6a-109">[en] Un puntero a la firma de metadatos binarios del miembro.</span><span class="sxs-lookup"><span data-stu-id="f5e6a-109">[in] A pointer to the binary metadata signature of the member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="f5e6a-110">[en] El tamaño en `pvSigBlob`bytes de .</span><span class="sxs-lookup"><span data-stu-id="f5e6a-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="f5e6a-111">[fuera] Un puntero al token MemberDef coincidente.</span><span class="sxs-lookup"><span data-stu-id="f5e6a-111">[out] A pointer to the matching MemberDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5e6a-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f5e6a-112">Remarks</span></span>  
 <span data-ttu-id="f5e6a-113">El miembro se especifica utilizando su`td`clase o`szName`interfaz envolvente (`pvSigBlob`), su nombre ( ) y, opcionalmente, su firma ( ).</span><span class="sxs-lookup"><span data-stu-id="f5e6a-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="f5e6a-114">Puede haber varios miembros con el mismo nombre en una clase o interfaz.</span><span class="sxs-lookup"><span data-stu-id="f5e6a-114">There might be multiple members with the same name in a class or interface.</span></span> <span data-ttu-id="f5e6a-115">En ese caso, pase la firma del miembro para encontrar la coincidencia única.</span><span class="sxs-lookup"><span data-stu-id="f5e6a-115">In that case, pass the member's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="f5e6a-116">La firma `FindMember` que se pasa debe haberse generado en el ámbito actual, porque las firmas están enlazadas a un ámbito determinado.</span><span class="sxs-lookup"><span data-stu-id="f5e6a-116">The signature passed to `FindMember` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="f5e6a-117">Una firma puede incrustar un token que identifica la clase envolvente o el tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="f5e6a-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="f5e6a-118">El token es un índice en la tabla TypeDef local.</span><span class="sxs-lookup"><span data-stu-id="f5e6a-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="f5e6a-119">No puede crear una firma en tiempo de ejecución fuera del contexto `FindMember`del ámbito actual y usar esa firma como entrada para introducir .</span><span class="sxs-lookup"><span data-stu-id="f5e6a-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMember`.</span></span>  
  
 <span data-ttu-id="f5e6a-120">`FindMember`encuentra solo los miembros que se definieron directamente en la clase o interfaz; no encuentra miembros heredados.</span><span class="sxs-lookup"><span data-stu-id="f5e6a-120">`FindMember` finds only members that were defined directly in the class or interface; it does not find inherited members.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f5e6a-121">`FindMember`es un método auxiliar.</span><span class="sxs-lookup"><span data-stu-id="f5e6a-121">`FindMember` is a helper method.</span></span> <span data-ttu-id="f5e6a-122">Llama a [IMetaDataImport::FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); si esa llamada no `FindMember` encuentra una coincidencia, llama a [IMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).</span><span class="sxs-lookup"><span data-stu-id="f5e6a-122">It calls [IMetaDataImport::FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); if that call does not find a match, `FindMember` then calls [IMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5e6a-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f5e6a-123">Requirements</span></span>  
 <span data-ttu-id="f5e6a-124">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5e6a-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5e6a-125">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f5e6a-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f5e6a-126">**Biblioteca:** Incluido como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f5e6a-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f5e6a-127">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5e6a-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5e6a-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f5e6a-128">See also</span></span>

- [<span data-ttu-id="f5e6a-129">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f5e6a-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="f5e6a-130">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f5e6a-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
