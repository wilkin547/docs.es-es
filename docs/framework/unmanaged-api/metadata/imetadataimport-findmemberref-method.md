---
title: IMetaDataImport::FindMemberRef (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMemberRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMemberRef
helpviewer_keywords:
- IMetaDataImport::FindMemberRef method [.NET Framework metadata]
- FindMemberRef method [.NET Framework metadata]
ms.assetid: 1ccda329-d752-4d89-abe8-511af3c3f4c9
topic_type:
- apiref
ms.openlocfilehash: d8b8bfd0e70e75c702f32555c10f433a1ff4ae10
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175426"
---
# <a name="imetadataimportfindmemberref-method"></a><span data-ttu-id="1bcef-102">IMetaDataImport::FindMemberRef (Método)</span><span class="sxs-lookup"><span data-stu-id="1bcef-102">IMetaDataImport::FindMemberRef Method</span></span>
<span data-ttu-id="1bcef-103">Obtiene un puntero al token MemberRef para la referencia de <xref:System.Type> miembro que está delimitada por el especificado y que tiene el nombre especificado y la firma de metadatos.</span><span class="sxs-lookup"><span data-stu-id="1bcef-103">Gets a pointer to the MemberRef token for the member reference that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bcef-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1bcef-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMemberRef (  
   [in]  mdTypeRef          td,  
   [in]  LPCWSTR            szName,
   [in]  PCCOR_SIGNATURE    pvSigBlob,
   [in]  ULONG              cbSigBlob,
   [out] mdMemberRef        *pmr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1bcef-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1bcef-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="1bcef-106">[en] El token TypeRef para la clase o interfaz que encierra la referencia de miembro que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="1bcef-106">[in] The TypeRef token for the class or interface that encloses the member reference to search for.</span></span> <span data-ttu-id="1bcef-107">Si este `mdTokenNil`valor es , la búsqueda se realiza para una variable global o una referencia de función global.</span><span class="sxs-lookup"><span data-stu-id="1bcef-107">If this value is `mdTokenNil`, the lookup is done for a global variable or a global-function reference.</span></span>  
  
 `szName`  
 <span data-ttu-id="1bcef-108">[en] El nombre de la referencia de miembro que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="1bcef-108">[in] The name of the member reference to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="1bcef-109">[en] Un puntero a la firma de metadatos binarios de la referencia de miembro.</span><span class="sxs-lookup"><span data-stu-id="1bcef-109">[in] A pointer to the binary metadata signature of the member reference.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="1bcef-110">[en] El tamaño en `pvSigBlob`bytes de .</span><span class="sxs-lookup"><span data-stu-id="1bcef-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="1bcef-111">[fuera] Un puntero al token MemberRef coincidente.</span><span class="sxs-lookup"><span data-stu-id="1bcef-111">[out] A pointer to the matching MemberRef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1bcef-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1bcef-112">Remarks</span></span>  
 <span data-ttu-id="1bcef-113">El miembro se especifica utilizando su`td`clase o`szName`interfaz envolvente (`pvSigBlob`), su nombre ( ) y, opcionalmente, su firma ( ).</span><span class="sxs-lookup"><span data-stu-id="1bcef-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="1bcef-114">La firma `FindMemberRef` que se pasa debe haberse generado en el ámbito actual, porque las firmas están enlazadas a un ámbito determinado.</span><span class="sxs-lookup"><span data-stu-id="1bcef-114">The signature passed to `FindMemberRef` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="1bcef-115">Una firma puede incrustar un token que identifica la clase envolvente o el tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="1bcef-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="1bcef-116">El token es un índice en la tabla TypeDef local.</span><span class="sxs-lookup"><span data-stu-id="1bcef-116">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="1bcef-117">No puede crear una firma en tiempo de ejecución fuera del `FindMemberRef`contexto del ámbito actual y usar esa firma como entrada para .</span><span class="sxs-lookup"><span data-stu-id="1bcef-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindMemberRef`.</span></span>  
  
 <span data-ttu-id="1bcef-118">`FindMemberRef`encuentra solo las referencias de miembro que se definieron directamente en la clase o interfaz; no encuentra referencias de miembros heredadas.</span><span class="sxs-lookup"><span data-stu-id="1bcef-118">`FindMemberRef` finds only member references that were defined directly in the class or interface; it does not find inherited member references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bcef-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1bcef-119">Requirements</span></span>  
 <span data-ttu-id="1bcef-120">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1bcef-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bcef-121">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1bcef-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1bcef-122">**Biblioteca:** Incluido como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1bcef-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1bcef-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1bcef-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bcef-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1bcef-124">See also</span></span>

- [<span data-ttu-id="1bcef-125">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1bcef-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="1bcef-126">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1bcef-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
