---
description: 'Más información acerca de: IMetaDataImport:: FindMember (método)'
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
ms.openlocfilehash: fdf02f57b8c4ff912d732515576fc05045474517
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799296"
---
# <a name="imetadataimportfindmember-method"></a><span data-ttu-id="a6001-103">IMetaDataImport::FindMember (Método)</span><span class="sxs-lookup"><span data-stu-id="a6001-103">IMetaDataImport::FindMember Method</span></span>

<span data-ttu-id="a6001-104">Obtiene un puntero al token de MemberDef para el campo o método que está incluido en el especificado <xref:System.Type> y que tiene el nombre y la firma de metadatos especificados.</span><span class="sxs-lookup"><span data-stu-id="a6001-104">Gets a pointer to the MemberDef token for field or method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6001-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a6001-105">Syntax</span></span>  
  
```cpp  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,
   [in]  PCCOR_SIGNATURE   pvSigBlob,
   [in]  ULONG             cbSigBlob,
   [out] mdToken           *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6001-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a6001-106">Parameters</span></span>  

 `td`  
 <span data-ttu-id="a6001-107">de El token TypeDef de la clase o interfaz que incluye el miembro que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="a6001-107">[in] The TypeDef token for the class or interface that encloses the member to search for.</span></span> <span data-ttu-id="a6001-108">Si este valor es `mdTokenNil` , la búsqueda se realiza para una variable global o una función global.</span><span class="sxs-lookup"><span data-stu-id="a6001-108">If this value is `mdTokenNil`, the lookup is done for a global-variable or global-function.</span></span>  
  
 `szName`  
 <span data-ttu-id="a6001-109">de Nombre del miembro que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="a6001-109">[in] The name of the member to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="a6001-110">de Puntero a la firma de metadatos binarios del miembro.</span><span class="sxs-lookup"><span data-stu-id="a6001-110">[in] A pointer to the binary metadata signature of the member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="a6001-111">de Tamaño en bytes de `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="a6001-111">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="a6001-112">enuncia Puntero al token de MemberDef coincidente.</span><span class="sxs-lookup"><span data-stu-id="a6001-112">[out] A pointer to the matching MemberDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6001-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a6001-113">Remarks</span></span>  

 <span data-ttu-id="a6001-114">El miembro se especifica mediante su clase o interfaz envolvente ( `td` ), su nombre ( `szName` ) y, opcionalmente, su firma ( `pvSigBlob` ).</span><span class="sxs-lookup"><span data-stu-id="a6001-114">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="a6001-115">Puede haber varios miembros con el mismo nombre en una clase o interfaz.</span><span class="sxs-lookup"><span data-stu-id="a6001-115">There might be multiple members with the same name in a class or interface.</span></span> <span data-ttu-id="a6001-116">En ese caso, pase la Signatura del miembro para encontrar la coincidencia única.</span><span class="sxs-lookup"><span data-stu-id="a6001-116">In that case, pass the member's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="a6001-117">La firma que se pasa a `FindMember` debe haberse generado en el ámbito actual, porque las firmas están enlazadas a un ámbito determinado.</span><span class="sxs-lookup"><span data-stu-id="a6001-117">The signature passed to `FindMember` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="a6001-118">Una firma puede insertar un token que identifica la clase envolvente o el tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="a6001-118">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="a6001-119">El token es un índice en la tabla TypeDef local.</span><span class="sxs-lookup"><span data-stu-id="a6001-119">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="a6001-120">No se puede crear una firma de tiempo de ejecución fuera del contexto del ámbito actual y usar esa firma como entrada para la entrada a `FindMember` .</span><span class="sxs-lookup"><span data-stu-id="a6001-120">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMember`.</span></span>  
  
 <span data-ttu-id="a6001-121">`FindMember` busca solo los miembros que se definieron directamente en la clase o la interfaz; no se encuentran los miembros heredados.</span><span class="sxs-lookup"><span data-stu-id="a6001-121">`FindMember` finds only members that were defined directly in the class or interface; it does not find inherited members.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a6001-122">`FindMember` es un método auxiliar.</span><span class="sxs-lookup"><span data-stu-id="a6001-122">`FindMember` is a helper method.</span></span> <span data-ttu-id="a6001-123">Llama a [IMetaDataImport:: findMethod (](imetadataimport-findmethod-method.md); Si esa llamada no encuentra ninguna coincidencia, `FindMember` llama a [IMetaDataImport:: FindField (](imetadataimport-findfield-method.md).</span><span class="sxs-lookup"><span data-stu-id="a6001-123">It calls [IMetaDataImport::FindMethod](imetadataimport-findmethod-method.md); if that call does not find a match, `FindMember` then calls [IMetaDataImport::FindField](imetadataimport-findfield-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6001-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a6001-124">Requirements</span></span>  

 <span data-ttu-id="a6001-125">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6001-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6001-126">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a6001-126">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a6001-127">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a6001-127">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a6001-128">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6001-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6001-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6001-129">See also</span></span>

- [<span data-ttu-id="a6001-130">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a6001-130">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="a6001-131">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a6001-131">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
