---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6b68d4e3d51fdb50290319de804a78c1a78a07a4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447393"
---
# <a name="imetadataimportfindmethod-method"></a><span data-ttu-id="35050-102">IMetaDataImport::FindMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="35050-102">IMetaDataImport::FindMethod Method</span></span>
<span data-ttu-id="35050-103">Obtiene un puntero al MethodDef token para el método que se encierra entre según los valores especificados <xref:System.Type> y que tiene la firma de nombre y los metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="35050-103">Gets a pointer to the MethodDef token for the method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35050-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="35050-104">Syntax</span></span>  
  
```  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMethodDef        *pmb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="35050-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="35050-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="35050-106">[in] El `mdTypeDef` token para el tipo (una clase o interfaz) que incluye el miembro que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="35050-106">[in] The `mdTypeDef` token for the type (a class or interface) that encloses the member to search for.</span></span> <span data-ttu-id="35050-107">Si este valor es `mdTokenNil`, a continuación, se realiza la búsqueda de una función global.</span><span class="sxs-lookup"><span data-stu-id="35050-107">If this value is `mdTokenNil`, then the lookup is done for a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="35050-108">[in] El nombre del método que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="35050-108">[in] The name of the method to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="35050-109">[in] Un puntero a la firma de metadatos binaria del método.</span><span class="sxs-lookup"><span data-stu-id="35050-109">[in] A pointer to the binary metadata signature of the method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="35050-110">[in] El tamaño en bytes de `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="35050-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="35050-111">[out] Un puntero al token MethodDef correspondiente.</span><span class="sxs-lookup"><span data-stu-id="35050-111">[out] A pointer to the matching MethodDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35050-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="35050-112">Remarks</span></span>  
 <span data-ttu-id="35050-113">Especifique el método con su clase o interfaz envolvente (`td`), su nombre (`szName`) y, opcionalmente, su firma (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="35050-113">You specify the method using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="35050-114">Puede haber varios métodos con el mismo nombre en una clase o interfaz.</span><span class="sxs-lookup"><span data-stu-id="35050-114">There might be multiple methods with the same name in a class or interface.</span></span> <span data-ttu-id="35050-115">En ese caso, pase la firma del método para encontrar a una coincidencia única.</span><span class="sxs-lookup"><span data-stu-id="35050-115">In that case, pass the method's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="35050-116">La firma se pasa a `FindMethod` deben haberse generado en el ámbito actual, porque las firmas están enlazadas a un ámbito determinado.</span><span class="sxs-lookup"><span data-stu-id="35050-116">The signature passed to `FindMethod` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="35050-117">Una firma puede incrustar un símbolo (token) que identifica el tipo de valor o clase envolvente.</span><span class="sxs-lookup"><span data-stu-id="35050-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="35050-118">El token es un índice en la tabla TypeDef local.</span><span class="sxs-lookup"><span data-stu-id="35050-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="35050-119">No se puede compilar una firma en tiempo de ejecución fuera del contexto del ámbito actual y use esa firma como entrada a `FindMethod`.</span><span class="sxs-lookup"><span data-stu-id="35050-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMethod`.</span></span>  
  
 <span data-ttu-id="35050-120">`FindMethod` busca únicamente los métodos que se definieron directamente en la clase o interfaz; no se encuentra métodos heredados.</span><span class="sxs-lookup"><span data-stu-id="35050-120">`FindMethod` finds only methods that were defined directly in the class or interface; it does not find inherited methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35050-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="35050-121">Requirements</span></span>  
 <span data-ttu-id="35050-122">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35050-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35050-123">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="35050-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="35050-124">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="35050-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="35050-125">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35050-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35050-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="35050-126">See Also</span></span>  
 <xref:System.Reflection.MethodInfo>  
 [<span data-ttu-id="35050-127">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="35050-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="35050-128">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="35050-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
