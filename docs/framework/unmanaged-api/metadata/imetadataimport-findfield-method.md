---
title: IMetaDataImport::FindField (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindField
helpviewer_keywords:
- IMetaDataImport::FindField method [.NET Framework metadata]
- FindField method [.NET Framework metadata]
ms.assetid: 38cd4e16-fbb2-471c-aa73-ac51a1931ad2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1baee71b5b8575f51eb54fbc8a037a5dddd24500
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782525"
---
# <a name="imetadataimportfindfield-method"></a><span data-ttu-id="9d720-102">IMetaDataImport::FindField (Método)</span><span class="sxs-lookup"><span data-stu-id="9d720-102">IMetaDataImport::FindField Method</span></span>
<span data-ttu-id="9d720-103">Obtiene un puntero a la FieldDef token para el campo que se incluye por especificado <xref:System.Type> y que tiene la firma de nombre y los metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="9d720-103">Gets a pointer to the FieldDef token for the field that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d720-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9d720-104">Syntax</span></span>  
  
```cpp  
HRESULT FindField (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,  
   [in]  PCCOR_SIGNATURE   pvSigBlob,  
   [in]  ULONG             cbSigBlob,  
   [out] mdFieldDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d720-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9d720-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="9d720-106">[in] El token de TypeDef para la clase o interfaz que incluye el campo que se busca.</span><span class="sxs-lookup"><span data-stu-id="9d720-106">[in] The TypeDef token for the class or interface that encloses the field to search for.</span></span> <span data-ttu-id="9d720-107">Si este valor es `mdTokenNil`, la búsqueda se realiza de una variable global.</span><span class="sxs-lookup"><span data-stu-id="9d720-107">If this value is `mdTokenNil`, the lookup is done for a global variable.</span></span>  
  
 `szName`  
 <span data-ttu-id="9d720-108">[in] El nombre del campo que se busca.</span><span class="sxs-lookup"><span data-stu-id="9d720-108">[in] The name of the field to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="9d720-109">[in] Un puntero a la firma de metadatos binaria del campo.</span><span class="sxs-lookup"><span data-stu-id="9d720-109">[in] A pointer to the binary metadata signature of the field.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="9d720-110">[in] El tamaño en bytes de `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="9d720-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="9d720-111">[out] Un puntero al token de FieldDef coincidente.</span><span class="sxs-lookup"><span data-stu-id="9d720-111">[out] A pointer to the matching FieldDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d720-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9d720-112">Remarks</span></span>  
 <span data-ttu-id="9d720-113">Especifique el campo con su clase o interfaz envolvente (`td`), su nombre (`szName`) y, opcionalmente, su firma (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="9d720-113">You specify the field using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="9d720-114">La firma pasa a `FindField` deben haberse generado en el ámbito actual, porque las firmas están enlazadas a un ámbito determinado.</span><span class="sxs-lookup"><span data-stu-id="9d720-114">The signature passed to `FindField` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="9d720-115">Una firma puede incrustar un token que identifica el tipo de valor o la clase envolvente.</span><span class="sxs-lookup"><span data-stu-id="9d720-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="9d720-116">(El token es un índice en la tabla TypeDef local).</span><span class="sxs-lookup"><span data-stu-id="9d720-116">(The token is an index into the local TypeDef table).</span></span> <span data-ttu-id="9d720-117">No se puede generar una firma de tiempo de ejecución fuera del contexto del ámbito actual y use esa firma como entrada para `FindField`.</span><span class="sxs-lookup"><span data-stu-id="9d720-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindField`.</span></span>  
  
 <span data-ttu-id="9d720-118">`FindField` Busca solo los campos que se definieron directamente en la clase o interfaz; no se encuentra campos heredados.</span><span class="sxs-lookup"><span data-stu-id="9d720-118">`FindField` finds only fields that were defined directly in the class or interface; it does not find inherited fields.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d720-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9d720-119">Requirements</span></span>  
 <span data-ttu-id="9d720-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d720-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d720-121">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="9d720-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9d720-122">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9d720-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9d720-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d720-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d720-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d720-124">See also</span></span>

- [<span data-ttu-id="9d720-125">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9d720-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="9d720-126">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9d720-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
