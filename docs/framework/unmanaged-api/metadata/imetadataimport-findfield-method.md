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
ms.openlocfilehash: ac69bab45ccd39b6a055fe4d2f74950ab47da779
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447037"
---
# <a name="imetadataimportfindfield-method"></a><span data-ttu-id="f5972-102">IMetaDataImport::FindField (Método)</span><span class="sxs-lookup"><span data-stu-id="f5972-102">IMetaDataImport::FindField Method</span></span>
<span data-ttu-id="f5972-103">Obtiene un puntero a la FieldDef token para el campo que se encierra entre según los valores especificados <xref:System.Type> y que tiene la firma de nombre y los metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="f5972-103">Gets a pointer to the FieldDef token for the field that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5972-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f5972-104">Syntax</span></span>  
  
```  
HRESULT FindField (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,  
   [in]  PCCOR_SIGNATURE   pvSigBlob,  
   [in]  ULONG             cbSigBlob,  
   [out] mdFieldDef        *pmb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f5972-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f5972-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="f5972-106">[in] El token de TypeDef para la clase o interfaz que incluye el campo que se busca.</span><span class="sxs-lookup"><span data-stu-id="f5972-106">[in] The TypeDef token for the class or interface that encloses the field to search for.</span></span> <span data-ttu-id="f5972-107">Si este valor es `mdTokenNil`, se realiza la búsqueda de una variable global.</span><span class="sxs-lookup"><span data-stu-id="f5972-107">If this value is `mdTokenNil`, the lookup is done for a global variable.</span></span>  
  
 `szName`  
 <span data-ttu-id="f5972-108">[in] El nombre del campo que se busca.</span><span class="sxs-lookup"><span data-stu-id="f5972-108">[in] The name of the field to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="f5972-109">[in] Un puntero a la firma de metadatos binaria del campo.</span><span class="sxs-lookup"><span data-stu-id="f5972-109">[in] A pointer to the binary metadata signature of the field.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="f5972-110">[in] El tamaño en bytes de `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="f5972-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="f5972-111">[out] Un puntero al token de FieldDef correspondiente.</span><span class="sxs-lookup"><span data-stu-id="f5972-111">[out] A pointer to the matching FieldDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5972-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f5972-112">Remarks</span></span>  
 <span data-ttu-id="f5972-113">Especifique el campo mediante su clase o interfaz envolvente (`td`), su nombre (`szName`) y, opcionalmente, su firma (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="f5972-113">You specify the field using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="f5972-114">La firma se pasa a `FindField` deben haberse generado en el ámbito actual, porque las firmas están enlazadas a un ámbito determinado.</span><span class="sxs-lookup"><span data-stu-id="f5972-114">The signature passed to `FindField` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="f5972-115">Una firma puede incrustar un símbolo (token) que identifica el tipo de valor o clase envolvente.</span><span class="sxs-lookup"><span data-stu-id="f5972-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="f5972-116">(El token es un índice en la tabla TypeDef local).</span><span class="sxs-lookup"><span data-stu-id="f5972-116">(The token is an index into the local TypeDef table).</span></span> <span data-ttu-id="f5972-117">No se puede compilar una firma en tiempo de ejecución fuera del contexto del ámbito actual y utilizar esa firma como entrada para `FindField`.</span><span class="sxs-lookup"><span data-stu-id="f5972-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindField`.</span></span>  
  
 <span data-ttu-id="f5972-118">`FindField` Busca solo los campos que se definieron directamente en la clase o interfaz; no se encuentra campos heredados.</span><span class="sxs-lookup"><span data-stu-id="f5972-118">`FindField` finds only fields that were defined directly in the class or interface; it does not find inherited fields.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5972-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f5972-119">Requirements</span></span>  
 <span data-ttu-id="f5972-120">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5972-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5972-121">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f5972-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f5972-122">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f5972-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f5972-123">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5972-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5972-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5972-124">See Also</span></span>  
 [<span data-ttu-id="f5972-125">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f5972-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="f5972-126">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f5972-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
