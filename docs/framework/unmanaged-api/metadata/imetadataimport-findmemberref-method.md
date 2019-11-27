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
ms.openlocfilehash: 59512cc1c1b280d7fe6deb2f9d721ad53547e356
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437956"
---
# <a name="imetadataimportfindmemberref-method"></a><span data-ttu-id="55b31-102">IMetaDataImport::FindMemberRef (Método)</span><span class="sxs-lookup"><span data-stu-id="55b31-102">IMetaDataImport::FindMemberRef Method</span></span>
<span data-ttu-id="55b31-103">Obtiene un puntero al token MemberRef para la referencia de miembro que está incluido en el <xref:System.Type> especificado y que tiene el nombre y la firma de metadatos especificados.</span><span class="sxs-lookup"><span data-stu-id="55b31-103">Gets a pointer to the MemberRef token for the member reference that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55b31-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="55b31-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMemberRef (  
   [in]  mdTypeRef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMemberRef        *pmr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55b31-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="55b31-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="55b31-106">de El token TypeRef de la clase o interfaz que incluye la referencia de miembro que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="55b31-106">[in] The TypeRef token for the class or interface that encloses the member reference to search for.</span></span> <span data-ttu-id="55b31-107">Si este valor se `mdTokenNil`, la búsqueda se realiza para una variable global o una referencia de función global.</span><span class="sxs-lookup"><span data-stu-id="55b31-107">If this value is `mdTokenNil`, the lookup is done for a global variable or a global-function reference.</span></span>  
  
 `szName`  
 <span data-ttu-id="55b31-108">de Nombre de la referencia de miembro que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="55b31-108">[in] The name of the member reference to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="55b31-109">de Puntero a la firma de metadatos binarios de la referencia de miembro.</span><span class="sxs-lookup"><span data-stu-id="55b31-109">[in] A pointer to the binary metadata signature of the member reference.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="55b31-110">de Tamaño en bytes de `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="55b31-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="55b31-111">enuncia Puntero al token de MemberRef correspondiente.</span><span class="sxs-lookup"><span data-stu-id="55b31-111">[out] A pointer to the matching MemberRef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55b31-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="55b31-112">Remarks</span></span>  
 <span data-ttu-id="55b31-113">El miembro se especifica mediante su clase o interfaz envolvente (`td`), su nombre (`szName`) y, opcionalmente, su firma (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="55b31-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="55b31-114">La firma pasada a `FindMemberRef` debe haberse generado en el ámbito actual, porque las firmas están enlazadas a un ámbito determinado.</span><span class="sxs-lookup"><span data-stu-id="55b31-114">The signature passed to `FindMemberRef` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="55b31-115">Una firma puede insertar un token que identifica la clase envolvente o el tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="55b31-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="55b31-116">El token es un índice en la tabla TypeDef local.</span><span class="sxs-lookup"><span data-stu-id="55b31-116">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="55b31-117">No se puede crear una firma de tiempo de ejecución fuera del contexto del ámbito actual y usar esa firma como entrada para `FindMemberRef`.</span><span class="sxs-lookup"><span data-stu-id="55b31-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindMemberRef`.</span></span>  
  
 <span data-ttu-id="55b31-118">`FindMemberRef` encuentra solo las referencias de miembro definidas directamente en la clase o la interfaz; no se encuentran las referencias de miembros heredados.</span><span class="sxs-lookup"><span data-stu-id="55b31-118">`FindMemberRef` finds only member references that were defined directly in the class or interface; it does not find inherited member references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55b31-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="55b31-119">Requirements</span></span>  
 <span data-ttu-id="55b31-120">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55b31-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55b31-121">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="55b31-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="55b31-122">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="55b31-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="55b31-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55b31-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55b31-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="55b31-124">See also</span></span>

- [<span data-ttu-id="55b31-125">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="55b31-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="55b31-126">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="55b31-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
