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
ms.openlocfilehash: 068014732cee91147edaec29fa0f954a741d8b5c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491672"
---
# <a name="imetadataimportfindmemberref-method"></a><span data-ttu-id="a5bd7-102">IMetaDataImport::FindMemberRef (Método)</span><span class="sxs-lookup"><span data-stu-id="a5bd7-102">IMetaDataImport::FindMemberRef Method</span></span>
<span data-ttu-id="a5bd7-103">Obtiene un puntero al token MemberRef para la referencia de miembro que está delimitada por el especificado <xref:System.Type> y que tiene el nombre y la firma de metadatos especificados.</span><span class="sxs-lookup"><span data-stu-id="a5bd7-103">Gets a pointer to the MemberRef token for the member reference that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5bd7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a5bd7-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMemberRef (  
   [in]  mdTypeRef          td,  
   [in]  LPCWSTR            szName,
   [in]  PCCOR_SIGNATURE    pvSigBlob,
   [in]  ULONG              cbSigBlob,
   [out] mdMemberRef        *pmr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5bd7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a5bd7-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="a5bd7-106">de El token TypeRef de la clase o interfaz que incluye la referencia de miembro que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="a5bd7-106">[in] The TypeRef token for the class or interface that encloses the member reference to search for.</span></span> <span data-ttu-id="a5bd7-107">Si este valor es `mdTokenNil` , la búsqueda se realiza para una variable global o una referencia de función global.</span><span class="sxs-lookup"><span data-stu-id="a5bd7-107">If this value is `mdTokenNil`, the lookup is done for a global variable or a global-function reference.</span></span>  
  
 `szName`  
 <span data-ttu-id="a5bd7-108">de Nombre de la referencia de miembro que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="a5bd7-108">[in] The name of the member reference to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="a5bd7-109">de Puntero a la firma de metadatos binarios de la referencia de miembro.</span><span class="sxs-lookup"><span data-stu-id="a5bd7-109">[in] A pointer to the binary metadata signature of the member reference.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="a5bd7-110">de Tamaño en bytes de `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="a5bd7-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="a5bd7-111">enuncia Puntero al token de MemberRef correspondiente.</span><span class="sxs-lookup"><span data-stu-id="a5bd7-111">[out] A pointer to the matching MemberRef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5bd7-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a5bd7-112">Remarks</span></span>  
 <span data-ttu-id="a5bd7-113">El miembro se especifica mediante su clase o interfaz envolvente ( `td` ), su nombre ( `szName` ) y, opcionalmente, su firma ( `pvSigBlob` ).</span><span class="sxs-lookup"><span data-stu-id="a5bd7-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="a5bd7-114">La firma que se pasa a `FindMemberRef` debe haberse generado en el ámbito actual, porque las firmas están enlazadas a un ámbito determinado.</span><span class="sxs-lookup"><span data-stu-id="a5bd7-114">The signature passed to `FindMemberRef` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="a5bd7-115">Una firma puede insertar un token que identifica la clase envolvente o el tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="a5bd7-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="a5bd7-116">El token es un índice en la tabla TypeDef local.</span><span class="sxs-lookup"><span data-stu-id="a5bd7-116">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="a5bd7-117">No se puede crear una firma de tiempo de ejecución fuera del contexto del ámbito actual y usar esa firma como entrada para `FindMemberRef` .</span><span class="sxs-lookup"><span data-stu-id="a5bd7-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindMemberRef`.</span></span>  
  
 <span data-ttu-id="a5bd7-118">`FindMemberRef`busca solo las referencias de miembro definidas directamente en la clase o la interfaz; no se encuentran las referencias de miembros heredados.</span><span class="sxs-lookup"><span data-stu-id="a5bd7-118">`FindMemberRef` finds only member references that were defined directly in the class or interface; it does not find inherited member references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5bd7-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a5bd7-119">Requirements</span></span>  
 <span data-ttu-id="a5bd7-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5bd7-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5bd7-121">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a5bd7-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a5bd7-122">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a5bd7-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a5bd7-123">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5bd7-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5bd7-124">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="a5bd7-124">See also</span></span>

- [<span data-ttu-id="a5bd7-125">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a5bd7-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="a5bd7-126">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a5bd7-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
