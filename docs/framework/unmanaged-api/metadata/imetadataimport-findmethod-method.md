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
ms.openlocfilehash: 28aa8313e7ba0c071187d0f1f6d78431b16fc005
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59164806"
---
# <a name="imetadataimportfindmethod-method"></a><span data-ttu-id="1c668-102">IMetaDataImport::FindMethod (Método)</span><span class="sxs-lookup"><span data-stu-id="1c668-102">IMetaDataImport::FindMethod Method</span></span>
<span data-ttu-id="1c668-103">Obtiene un puntero a MethodDef token para el método que se incluye por especificado <xref:System.Type> y que tiene la firma de nombre y los metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="1c668-103">Gets a pointer to the MethodDef token for the method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c668-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1c668-104">Syntax</span></span>  
  
```  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMethodDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c668-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1c668-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="1c668-106">[in] El `mdTypeDef` token para el tipo (una clase o interfaz) que incluye el miembro que se busca.</span><span class="sxs-lookup"><span data-stu-id="1c668-106">[in] The `mdTypeDef` token for the type (a class or interface) that encloses the member to search for.</span></span> <span data-ttu-id="1c668-107">Si este valor es `mdTokenNil`, a continuación, la búsqueda se realiza para una función global.</span><span class="sxs-lookup"><span data-stu-id="1c668-107">If this value is `mdTokenNil`, then the lookup is done for a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="1c668-108">[in] El nombre del método que se busca.</span><span class="sxs-lookup"><span data-stu-id="1c668-108">[in] The name of the method to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="1c668-109">[in] Un puntero a la firma de metadatos binaria del método.</span><span class="sxs-lookup"><span data-stu-id="1c668-109">[in] A pointer to the binary metadata signature of the method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="1c668-110">[in] El tamaño en bytes de `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="1c668-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="1c668-111">[out] Un puntero al token MethodDef coincidente.</span><span class="sxs-lookup"><span data-stu-id="1c668-111">[out] A pointer to the matching MethodDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c668-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1c668-112">Remarks</span></span>  
 <span data-ttu-id="1c668-113">Especifique el método con su clase o interfaz envolvente (`td`), su nombre (`szName`) y, opcionalmente, su firma (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="1c668-113">You specify the method using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="1c668-114">Puede haber varios métodos con el mismo nombre en una clase o interfaz.</span><span class="sxs-lookup"><span data-stu-id="1c668-114">There might be multiple methods with the same name in a class or interface.</span></span> <span data-ttu-id="1c668-115">En ese caso, pase la firma del método para buscar a una coincidencia única.</span><span class="sxs-lookup"><span data-stu-id="1c668-115">In that case, pass the method's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="1c668-116">La firma pasa a `FindMethod` deben haberse generado en el ámbito actual, porque las firmas están enlazadas a un ámbito determinado.</span><span class="sxs-lookup"><span data-stu-id="1c668-116">The signature passed to `FindMethod` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="1c668-117">Una firma puede incrustar un token que identifica el tipo de valor o la clase envolvente.</span><span class="sxs-lookup"><span data-stu-id="1c668-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="1c668-118">El token es un índice en la tabla TypeDef local.</span><span class="sxs-lookup"><span data-stu-id="1c668-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="1c668-119">No se puede generar una firma de tiempo de ejecución fuera del contexto del ámbito actual y use esa firma como entrada a `FindMethod`.</span><span class="sxs-lookup"><span data-stu-id="1c668-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMethod`.</span></span>  
  
 `FindMethod` <span data-ttu-id="1c668-120">Busca solo los métodos que se definieron directamente en la clase o interfaz; no se encuentra métodos heredados.</span><span class="sxs-lookup"><span data-stu-id="1c668-120">finds only methods that were defined directly in the class or interface; it does not find inherited methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c668-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1c668-121">Requirements</span></span>  
 <span data-ttu-id="1c668-122">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c668-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c668-123">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="1c668-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1c668-124">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1c668-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="1c668-125">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="1c668-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1c668-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c668-126">See also</span></span>

- <xref:System.Reflection.MethodInfo>
- [<span data-ttu-id="1c668-127">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1c668-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="1c668-128">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1c668-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
