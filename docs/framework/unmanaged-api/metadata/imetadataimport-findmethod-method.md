---
description: 'Más información sobre: IMetaDataImport:: findMethod ((método)'
title: IMetaDataImport::FindMethod (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMethod
helpviewer_keywords:
- FindMethod method [.NET Framework metadata]
- IMetaDataImport::FindMethod method [.NET Framework metadata]
ms.assetid: 0f9bde1d-e306-438d-941b-d0925b322304
topic_type:
- apiref
ms.openlocfilehash: 0d2866554fcb4dcf3984310e4da24d501f1fc7b6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803560"
---
# <a name="imetadataimportfindmethod-method"></a><span data-ttu-id="704dc-103">IMetaDataImport::FindMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="704dc-103">IMetaDataImport::FindMethod Method</span></span>

<span data-ttu-id="704dc-104">Obtiene un puntero al token MethodDef para el método que está incluido en el especificado <xref:System.Type> y que tiene el nombre y la firma de metadatos especificados.</span><span class="sxs-lookup"><span data-stu-id="704dc-104">Gets a pointer to the MethodDef token for the method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="704dc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="704dc-105">Syntax</span></span>  
  
```cpp  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,
   [in]  PCCOR_SIGNATURE    pvSigBlob,
   [in]  ULONG              cbSigBlob,
   [out] mdMethodDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="704dc-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="704dc-106">Parameters</span></span>  

 `td`  
 <span data-ttu-id="704dc-107">de El `mdTypeDef` token para el tipo (una clase o interfaz) que incluye el miembro que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="704dc-107">[in] The `mdTypeDef` token for the type (a class or interface) that encloses the member to search for.</span></span> <span data-ttu-id="704dc-108">Si este valor es `mdTokenNil` , la búsqueda se realiza para una función global.</span><span class="sxs-lookup"><span data-stu-id="704dc-108">If this value is `mdTokenNil`, then the lookup is done for a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="704dc-109">de Nombre del método que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="704dc-109">[in] The name of the method to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="704dc-110">de Puntero a la firma de metadatos binarios del método.</span><span class="sxs-lookup"><span data-stu-id="704dc-110">[in] A pointer to the binary metadata signature of the method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="704dc-111">de Tamaño en bytes de `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="704dc-111">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="704dc-112">enuncia Puntero al token MethodDef coincidente.</span><span class="sxs-lookup"><span data-stu-id="704dc-112">[out] A pointer to the matching MethodDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="704dc-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="704dc-113">Remarks</span></span>  

 <span data-ttu-id="704dc-114">El método se especifica mediante su clase o interfaz envolvente ( `td` ), su nombre ( `szName` ) y, opcionalmente, su firma ( `pvSigBlob` ).</span><span class="sxs-lookup"><span data-stu-id="704dc-114">You specify the method using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="704dc-115">Puede haber varios métodos con el mismo nombre en una clase o interfaz.</span><span class="sxs-lookup"><span data-stu-id="704dc-115">There might be multiple methods with the same name in a class or interface.</span></span> <span data-ttu-id="704dc-116">En ese caso, pase la Signatura del método para buscar la coincidencia única.</span><span class="sxs-lookup"><span data-stu-id="704dc-116">In that case, pass the method's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="704dc-117">La firma que se pasa a `FindMethod` debe haberse generado en el ámbito actual, porque las firmas están enlazadas a un ámbito determinado.</span><span class="sxs-lookup"><span data-stu-id="704dc-117">The signature passed to `FindMethod` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="704dc-118">Una firma puede insertar un token que identifica la clase envolvente o el tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="704dc-118">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="704dc-119">El token es un índice en la tabla TypeDef local.</span><span class="sxs-lookup"><span data-stu-id="704dc-119">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="704dc-120">No se puede crear una firma de tiempo de ejecución fuera del contexto del ámbito actual y usar esa firma como entrada para la entrada a `FindMethod` .</span><span class="sxs-lookup"><span data-stu-id="704dc-120">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMethod`.</span></span>  
  
 <span data-ttu-id="704dc-121">`FindMethod` busca solo los métodos que se definieron directamente en la clase o la interfaz; no se encuentran los métodos heredados.</span><span class="sxs-lookup"><span data-stu-id="704dc-121">`FindMethod` finds only methods that were defined directly in the class or interface; it does not find inherited methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="704dc-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="704dc-122">Requirements</span></span>  

 <span data-ttu-id="704dc-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="704dc-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="704dc-124">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="704dc-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="704dc-125">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="704dc-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="704dc-126">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="704dc-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="704dc-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="704dc-127">See also</span></span>

- <xref:System.Reflection.MethodInfo>
- [<span data-ttu-id="704dc-128">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="704dc-128">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="704dc-129">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="704dc-129">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
