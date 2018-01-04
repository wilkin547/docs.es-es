---
title: "IMetaDataAssemblyEmit::DefineExportedType (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.DefineExportedType
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::DefineExportedType
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineExportedType method [.NET Framework metadata]
- DefineExportedType method [.NET Framework metadata]
ms.assetid: fad01d7a-3178-4c8c-9f0a-4641e3701c9b
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 59aae188e404ebc717a140fb7918e3fbf69f3f70
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyemitdefineexportedtype-method"></a><span data-ttu-id="ede6a-102">IMetaDataAssemblyEmit::DefineExportedType (Método)</span><span class="sxs-lookup"><span data-stu-id="ede6a-102">IMetaDataAssemblyEmit::DefineExportedType Method</span></span>
<span data-ttu-id="ede6a-103">Crea una estructura `ExportedType` que contiene los metadatos para el tipo exportado especificado y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="ede6a-103">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ede6a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ede6a-104">Syntax</span></span>  
  
```  
HRESULT DefineExportedType (  
    [in]  LPCWSTR             szName,  
    [in]  mdToken             tkImplementation,   
    [in]  mdTypeDef           tkTypeDef,  
    [in]  DWORD               dwExportedTypeFlags,  
    [out] mdExportedType      *pmdct  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ede6a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ede6a-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="ede6a-106">[in] El nombre de tipo que se exportarán.</span><span class="sxs-lookup"><span data-stu-id="ede6a-106">[in] The name of type to be exported.</span></span> <span data-ttu-id="ede6a-107">Para la versión 1.1 de common language runtime, el nombre del tipo exportado debe coincidir exactamente con el nombre proporcionado en el `TypeDef` para el tipo.</span><span class="sxs-lookup"><span data-stu-id="ede6a-107">For version 1.1 of the common language runtime, the name of the exported type must exactly match the name given in the `TypeDef` for the type.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="ede6a-108">[in] Un token que especifica donde se implementa el tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="ede6a-108">[in] A token specifying where the exported type is implemented.</span></span> <span data-ttu-id="ede6a-109">Los valores válidos y sus significados asociados son:</span><span class="sxs-lookup"><span data-stu-id="ede6a-109">The valid values and their associated meanings are:</span></span>  
  
-   <span data-ttu-id="ede6a-110">`mdFile`El tipo se implementa en un archivo diferente dentro de este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ede6a-110">`mdFile` The type is implemented in a different file within this assembly.</span></span>  
  
-   <span data-ttu-id="ede6a-111">`mdAssemblyRef`El tipo se implementa en un ensamblado diferente.</span><span class="sxs-lookup"><span data-stu-id="ede6a-111">`mdAssemblyRef` The type is implemented in a different assembly.</span></span>  
  
-   <span data-ttu-id="ede6a-112">`mdExportedTYpe`El tipo está anidado dentro de otro tipo.</span><span class="sxs-lookup"><span data-stu-id="ede6a-112">`mdExportedTYpe` The type is nested within some other type.</span></span>  
  
-   <span data-ttu-id="ede6a-113">`mdFileNil`El tipo está en el mismo archivo que el manifiesto y no es un tipo anidado.</span><span class="sxs-lookup"><span data-stu-id="ede6a-113">`mdFileNil` The type is in the same file as the manifest and is not a nested type.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="ede6a-114">[in] Un token de los metadatos que especifica el tipo que se exportarán.</span><span class="sxs-lookup"><span data-stu-id="ede6a-114">[in] A token to the metadata that specifies the type to be exported.</span></span> <span data-ttu-id="ede6a-115">Este valor se introduce en el `TypeDef` tabla en el archivo que implementa el tipo y solo es pertinente si ese archivo está en este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ede6a-115">This value is entered in the `TypeDef` table in the file that implements the type and is relevant only if that file is in this assembly.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="ede6a-116">[in] Una combinación bit a bit de [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) valores de enumeración que definen los valores de propiedad para el tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="ede6a-116">[in] A bitwise combination of [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumeration values that define the property settings for the exported type.</span></span>  
  
 `pmdct`  
 <span data-ttu-id="ede6a-117">[out] Un puntero al token de metadatos devuelto que indica el tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="ede6a-117">[out] A pointer to the returned metadata token that indicates the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ede6a-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ede6a-118">Remarks</span></span>  
 <span data-ttu-id="ede6a-119">Un `ExportedType` estructura de los metadatos se debe definir para cada tipo que está expuesto por este ensamblado y que se implementa en un módulo distinto del que contiene el manifiesto.</span><span class="sxs-lookup"><span data-stu-id="ede6a-119">An `ExportedType` metadata structure must be defined for each type that is exposed by this assembly and that is implemented in a module other than the one containing the manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ede6a-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ede6a-120">Requirements</span></span>  
 <span data-ttu-id="ede6a-121">**Plataforma:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ede6a-121">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ede6a-122">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ede6a-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ede6a-123">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ede6a-123">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ede6a-124">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ede6a-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ede6a-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="ede6a-125">See Also</span></span>  
 [<span data-ttu-id="ede6a-126">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ede6a-126">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
