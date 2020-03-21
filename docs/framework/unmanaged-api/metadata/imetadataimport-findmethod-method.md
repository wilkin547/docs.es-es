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
ms.openlocfilehash: 53b3d94e8b1e273fcbc041d25a5bf586a12735c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177251"
---
# <a name="imetadataimportfindmethod-method"></a><span data-ttu-id="0266b-102">IMetaDataImport::FindMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="0266b-102">IMetaDataImport::FindMethod Method</span></span>
<span data-ttu-id="0266b-103">Obtiene un puntero al token MethodDef para el método incluido <xref:System.Type> en el especificado y que tiene el nombre y la firma de metadatos especificados.</span><span class="sxs-lookup"><span data-stu-id="0266b-103">Gets a pointer to the MethodDef token for the method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0266b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0266b-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,
   [in]  PCCOR_SIGNATURE    pvSigBlob,
   [in]  ULONG              cbSigBlob,
   [out] mdMethodDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0266b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0266b-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="0266b-106">[en] El `mdTypeDef` token para el tipo (una clase o interfaz) que encierra el miembro que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="0266b-106">[in] The `mdTypeDef` token for the type (a class or interface) that encloses the member to search for.</span></span> <span data-ttu-id="0266b-107">Si este `mdTokenNil`valor es , la búsqueda se realiza para una función global.</span><span class="sxs-lookup"><span data-stu-id="0266b-107">If this value is `mdTokenNil`, then the lookup is done for a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="0266b-108">[en] El nombre del método que se va a buscar.</span><span class="sxs-lookup"><span data-stu-id="0266b-108">[in] The name of the method to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="0266b-109">[en] Un puntero a la firma de metadatos binarios del método.</span><span class="sxs-lookup"><span data-stu-id="0266b-109">[in] A pointer to the binary metadata signature of the method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="0266b-110">[en] El tamaño en `pvSigBlob`bytes de .</span><span class="sxs-lookup"><span data-stu-id="0266b-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="0266b-111">[fuera] Un puntero al token MethodDef coincidente.</span><span class="sxs-lookup"><span data-stu-id="0266b-111">[out] A pointer to the matching MethodDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0266b-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0266b-112">Remarks</span></span>  
 <span data-ttu-id="0266b-113">El método se especifica utilizando su`td`clase o`szName`interfaz envolvente (`pvSigBlob`), su nombre ( ) y, opcionalmente, su firma ( ).</span><span class="sxs-lookup"><span data-stu-id="0266b-113">You specify the method using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="0266b-114">Puede haber varios métodos con el mismo nombre en una clase o interfaz.</span><span class="sxs-lookup"><span data-stu-id="0266b-114">There might be multiple methods with the same name in a class or interface.</span></span> <span data-ttu-id="0266b-115">En ese caso, pase la firma del método para encontrar la coincidencia única.</span><span class="sxs-lookup"><span data-stu-id="0266b-115">In that case, pass the method's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="0266b-116">La firma `FindMethod` que se pasa debe haberse generado en el ámbito actual, porque las firmas están enlazadas a un ámbito determinado.</span><span class="sxs-lookup"><span data-stu-id="0266b-116">The signature passed to `FindMethod` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="0266b-117">Una firma puede incrustar un token que identifica la clase envolvente o el tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="0266b-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="0266b-118">El token es un índice en la tabla TypeDef local.</span><span class="sxs-lookup"><span data-stu-id="0266b-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="0266b-119">No puede crear una firma en tiempo de ejecución fuera del contexto `FindMethod`del ámbito actual y usar esa firma como entrada para introducir .</span><span class="sxs-lookup"><span data-stu-id="0266b-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMethod`.</span></span>  
  
 <span data-ttu-id="0266b-120">`FindMethod`encuentra sólo los métodos que se definieron directamente en la clase o interfaz; no encuentra métodos heredados.</span><span class="sxs-lookup"><span data-stu-id="0266b-120">`FindMethod` finds only methods that were defined directly in the class or interface; it does not find inherited methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0266b-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0266b-121">Requirements</span></span>  
 <span data-ttu-id="0266b-122">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0266b-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0266b-123">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0266b-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0266b-124">**Biblioteca:** Incluido como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0266b-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0266b-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0266b-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0266b-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0266b-126">See also</span></span>

- <xref:System.Reflection.MethodInfo>
- [<span data-ttu-id="0266b-127">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0266b-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="0266b-128">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0266b-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
