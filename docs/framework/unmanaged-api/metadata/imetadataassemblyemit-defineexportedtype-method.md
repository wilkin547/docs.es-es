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
ms.openlocfilehash: 388f227377ddf73fe1297e1c777bb1c0607c13d2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177875"
---
# <a name="imetadataassemblyemitdefineexportedtype-method"></a><span data-ttu-id="a8869-102">IMetaDataAssemblyEmit::DefineExportedType (Método)</span><span class="sxs-lookup"><span data-stu-id="a8869-102">IMetaDataAssemblyEmit::DefineExportedType Method</span></span>
<span data-ttu-id="a8869-103">Crea una estructura `ExportedType` que contiene los metadatos para el tipo exportado especificado y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="a8869-103">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8869-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a8869-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineExportedType (  
    [in]  LPCWSTR             szName,  
    [in]  mdToken             tkImplementation,
    [in]  mdTypeDef           tkTypeDef,  
    [in]  DWORD               dwExportedTypeFlags,  
    [out] mdExportedType      *pmdct  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8869-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a8869-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="a8869-106">[en] El nombre del tipo que se va a exportar.</span><span class="sxs-lookup"><span data-stu-id="a8869-106">[in] The name of type to be exported.</span></span> <span data-ttu-id="a8869-107">Para la versión 1.1 de Common Language Runtime, el nombre del `TypeDef` tipo exportado debe coincidir exactamente con el nombre especificado en el para el tipo.</span><span class="sxs-lookup"><span data-stu-id="a8869-107">For version 1.1 of the common language runtime, the name of the exported type must exactly match the name given in the `TypeDef` for the type.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="a8869-108">[en] Un token que especifica dónde se implementa el tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="a8869-108">[in] A token specifying where the exported type is implemented.</span></span> <span data-ttu-id="a8869-109">Los valores válidos y sus significados asociados son:</span><span class="sxs-lookup"><span data-stu-id="a8869-109">The valid values and their associated meanings are:</span></span>  
  
- <span data-ttu-id="a8869-110">`mdFile`El tipo se implementa en un archivo diferente dentro de este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a8869-110">`mdFile` The type is implemented in a different file within this assembly.</span></span>  
  
- <span data-ttu-id="a8869-111">`mdAssemblyRef`El tipo se implementa en un ensamblado diferente.</span><span class="sxs-lookup"><span data-stu-id="a8869-111">`mdAssemblyRef` The type is implemented in a different assembly.</span></span>  
  
- <span data-ttu-id="a8869-112">`mdExportedTYpe`El tipo está anidado dentro de algún otro tipo.</span><span class="sxs-lookup"><span data-stu-id="a8869-112">`mdExportedTYpe` The type is nested within some other type.</span></span>  
  
- <span data-ttu-id="a8869-113">`mdFileNil`El tipo está en el mismo archivo que el manifiesto y no es un tipo anidado.</span><span class="sxs-lookup"><span data-stu-id="a8869-113">`mdFileNil` The type is in the same file as the manifest and is not a nested type.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="a8869-114">[en] Un token para los metadatos que especifica el tipo que se va a exportar.</span><span class="sxs-lookup"><span data-stu-id="a8869-114">[in] A token to the metadata that specifies the type to be exported.</span></span> <span data-ttu-id="a8869-115">Este valor se `TypeDef` introduce en la tabla del archivo que implementa el tipo y sólo es relevante si ese archivo está en este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a8869-115">This value is entered in the `TypeDef` table in the file that implements the type and is relevant only if that file is in this assembly.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="a8869-116">[en] Combinación bit a bit de valores de enumeración [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) que definen la configuración de propiedad para el tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="a8869-116">[in] A bitwise combination of [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) enumeration values that define the property settings for the exported type.</span></span>  
  
 `pmdct`  
 <span data-ttu-id="a8869-117">[fuera] Puntero al token de metadatos devuelto que indica el tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="a8869-117">[out] A pointer to the returned metadata token that indicates the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8869-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a8869-118">Remarks</span></span>  
 <span data-ttu-id="a8869-119">Se `ExportedType` debe definir una estructura de metadatos para cada tipo expuesto por este ensamblado y que se implementa en un módulo distinto del que contiene el manifiesto.</span><span class="sxs-lookup"><span data-stu-id="a8869-119">An `ExportedType` metadata structure must be defined for each type that is exposed by this assembly and that is implemented in a module other than the one containing the manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8869-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a8869-120">Requirements</span></span>  
 <span data-ttu-id="a8869-121">**Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8869-121">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8869-122">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a8869-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a8869-123">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a8869-123">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a8869-124">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8869-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8869-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a8869-125">See also</span></span>

- [<span data-ttu-id="a8869-126">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a8869-126">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
