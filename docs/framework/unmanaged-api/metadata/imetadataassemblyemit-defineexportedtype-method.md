---
title: IMetaDataAssemblyEmit::DefineExportedType (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineExportedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineExportedType
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineExportedType method [.NET Framework metadata]
- DefineExportedType method [.NET Framework metadata]
ms.assetid: fad01d7a-3178-4c8c-9f0a-4641e3701c9b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 984eef16ff576d63a445b199eba8c2364285f62e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57483879"
---
# <a name="imetadataassemblyemitdefineexportedtype-method"></a><span data-ttu-id="249d9-102">IMetaDataAssemblyEmit::DefineExportedType (Método)</span><span class="sxs-lookup"><span data-stu-id="249d9-102">IMetaDataAssemblyEmit::DefineExportedType Method</span></span>
<span data-ttu-id="249d9-103">Crea una estructura `ExportedType` que contiene los metadatos para el tipo exportado especificado y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="249d9-103">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="249d9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="249d9-104">Syntax</span></span>  
  
```  
HRESULT DefineExportedType (  
    [in]  LPCWSTR             szName,  
    [in]  mdToken             tkImplementation,   
    [in]  mdTypeDef           tkTypeDef,  
    [in]  DWORD               dwExportedTypeFlags,  
    [out] mdExportedType      *pmdct  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="249d9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="249d9-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="249d9-106">[in] Nombre del tipo que se exportarán.</span><span class="sxs-lookup"><span data-stu-id="249d9-106">[in] The name of type to be exported.</span></span> <span data-ttu-id="249d9-107">Para la versión 1.1 de common language runtime, el nombre del tipo exportado debe coincidir exactamente con el nombre proporcionado en el `TypeDef` para el tipo.</span><span class="sxs-lookup"><span data-stu-id="249d9-107">For version 1.1 of the common language runtime, the name of the exported type must exactly match the name given in the `TypeDef` for the type.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="249d9-108">[in] Un token que especifica donde se implementa el tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="249d9-108">[in] A token specifying where the exported type is implemented.</span></span> <span data-ttu-id="249d9-109">Los valores válidos y sus significados asociados son:</span><span class="sxs-lookup"><span data-stu-id="249d9-109">The valid values and their associated meanings are:</span></span>  
  
-   <span data-ttu-id="249d9-110">`mdFile` El tipo se implementa en un archivo diferente dentro de este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="249d9-110">`mdFile` The type is implemented in a different file within this assembly.</span></span>  
  
-   <span data-ttu-id="249d9-111">`mdAssemblyRef` El tipo se implementa en un ensamblado diferente.</span><span class="sxs-lookup"><span data-stu-id="249d9-111">`mdAssemblyRef` The type is implemented in a different assembly.</span></span>  
  
-   <span data-ttu-id="249d9-112">`mdExportedTYpe` El tipo está anidado dentro de otro tipo.</span><span class="sxs-lookup"><span data-stu-id="249d9-112">`mdExportedTYpe` The type is nested within some other type.</span></span>  
  
-   <span data-ttu-id="249d9-113">`mdFileNil` El tipo está en el mismo archivo que el manifiesto y no es un tipo anidado.</span><span class="sxs-lookup"><span data-stu-id="249d9-113">`mdFileNil` The type is in the same file as the manifest and is not a nested type.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="249d9-114">[in] Un token de los metadatos que especifica el tipo que se exportarán.</span><span class="sxs-lookup"><span data-stu-id="249d9-114">[in] A token to the metadata that specifies the type to be exported.</span></span> <span data-ttu-id="249d9-115">Este valor se introduce en el `TypeDef` tabla en el archivo que implementa el tipo y solo es pertinente si ese archivo se encuentra en este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="249d9-115">This value is entered in the `TypeDef` table in the file that implements the type and is relevant only if that file is in this assembly.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="249d9-116">[in] Una combinación bit a bit de [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) valores de enumeración que definen los valores de propiedad para el tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="249d9-116">[in] A bitwise combination of [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumeration values that define the property settings for the exported type.</span></span>  
  
 `pmdct`  
 <span data-ttu-id="249d9-117">[out] Un puntero al token de metadatos devuelto que indica el tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="249d9-117">[out] A pointer to the returned metadata token that indicates the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="249d9-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="249d9-118">Remarks</span></span>  
 <span data-ttu-id="249d9-119">Un `ExportedType` estructura de los metadatos debe definirse para cada tipo que está expuesto por este ensamblado y que se implementa en un módulo distinto del que contiene el manifiesto.</span><span class="sxs-lookup"><span data-stu-id="249d9-119">An `ExportedType` metadata structure must be defined for each type that is exposed by this assembly and that is implemented in a module other than the one containing the manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="249d9-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="249d9-120">Requirements</span></span>  
 <span data-ttu-id="249d9-121">**Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="249d9-121">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="249d9-122">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="249d9-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="249d9-123">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="249d9-123">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="249d9-124">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="249d9-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="249d9-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="249d9-125">See also</span></span>
- [<span data-ttu-id="249d9-126">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="249d9-126">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
