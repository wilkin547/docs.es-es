---
description: 'Más información acerca de: IMetaDataAssemblyEmit::D método efineExportedType'
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
ms.openlocfilehash: 0da1b1eb0880b0ba9df0ba9ad70b460163dffc39
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671118"
---
# <a name="imetadataassemblyemitdefineexportedtype-method"></a><span data-ttu-id="49ad7-103">IMetaDataAssemblyEmit::DefineExportedType (Método)</span><span class="sxs-lookup"><span data-stu-id="49ad7-103">IMetaDataAssemblyEmit::DefineExportedType Method</span></span>

<span data-ttu-id="49ad7-104">Crea una estructura `ExportedType` que contiene los metadatos para el tipo exportado especificado y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="49ad7-104">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49ad7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="49ad7-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineExportedType (  
    [in]  LPCWSTR             szName,  
    [in]  mdToken             tkImplementation,
    [in]  mdTypeDef           tkTypeDef,  
    [in]  DWORD               dwExportedTypeFlags,  
    [out] mdExportedType      *pmdct  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49ad7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="49ad7-106">Parameters</span></span>  

 `szName`  
 <span data-ttu-id="49ad7-107">de Nombre del tipo que se va a exportar.</span><span class="sxs-lookup"><span data-stu-id="49ad7-107">[in] The name of type to be exported.</span></span> <span data-ttu-id="49ad7-108">En la versión 1,1 del Common Language Runtime, el nombre del tipo exportado debe coincidir exactamente con el nombre dado en `TypeDef` para el tipo.</span><span class="sxs-lookup"><span data-stu-id="49ad7-108">For version 1.1 of the common language runtime, the name of the exported type must exactly match the name given in the `TypeDef` for the type.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="49ad7-109">de Token que especifica dónde se implementa el tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="49ad7-109">[in] A token specifying where the exported type is implemented.</span></span> <span data-ttu-id="49ad7-110">Los valores válidos y sus significados asociados son:</span><span class="sxs-lookup"><span data-stu-id="49ad7-110">The valid values and their associated meanings are:</span></span>  
  
- <span data-ttu-id="49ad7-111">`mdFile` El tipo se implementa en un archivo diferente dentro de este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="49ad7-111">`mdFile` The type is implemented in a different file within this assembly.</span></span>  
  
- <span data-ttu-id="49ad7-112">`mdAssemblyRef` El tipo se implementa en un ensamblado diferente.</span><span class="sxs-lookup"><span data-stu-id="49ad7-112">`mdAssemblyRef` The type is implemented in a different assembly.</span></span>  
  
- <span data-ttu-id="49ad7-113">`mdExportedTYpe` El tipo está anidado dentro de otro tipo.</span><span class="sxs-lookup"><span data-stu-id="49ad7-113">`mdExportedTYpe` The type is nested within some other type.</span></span>  
  
- <span data-ttu-id="49ad7-114">`mdFileNil` El tipo está en el mismo archivo que el manifiesto y no es un tipo anidado.</span><span class="sxs-lookup"><span data-stu-id="49ad7-114">`mdFileNil` The type is in the same file as the manifest and is not a nested type.</span></span>  
  
 `tkTypeDef`  
 <span data-ttu-id="49ad7-115">de Token a los metadatos que especifica el tipo que se va a exportar.</span><span class="sxs-lookup"><span data-stu-id="49ad7-115">[in] A token to the metadata that specifies the type to be exported.</span></span> <span data-ttu-id="49ad7-116">Este valor se especifica en la `TypeDef` tabla del archivo que implementa el tipo y solo es relevante si ese archivo está en este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="49ad7-116">This value is entered in the `TypeDef` table in the file that implements the type and is relevant only if that file is in this assembly.</span></span>  
  
 `dwExportedTypeFlags`  
 <span data-ttu-id="49ad7-117">de Combinación bit a bit de los valores de enumeración de [cortypeattr (](cortypeattr-enumeration.md) que definen los valores de propiedad para el tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="49ad7-117">[in] A bitwise combination of [CorTypeAttr](cortypeattr-enumeration.md) enumeration values that define the property settings for the exported type.</span></span>  
  
 `pmdct`  
 <span data-ttu-id="49ad7-118">enuncia Puntero al símbolo (token) de metadatos devuelto que indica el tipo exportado.</span><span class="sxs-lookup"><span data-stu-id="49ad7-118">[out] A pointer to the returned metadata token that indicates the exported type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49ad7-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="49ad7-119">Remarks</span></span>  

 <span data-ttu-id="49ad7-120">`ExportedType`Se debe definir una estructura de metadatos para cada tipo expuesto por este ensamblado y que se implementa en un módulo distinto del que contiene el manifiesto.</span><span class="sxs-lookup"><span data-stu-id="49ad7-120">An `ExportedType` metadata structure must be defined for each type that is exposed by this assembly and that is implemented in a module other than the one containing the manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49ad7-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="49ad7-121">Requirements</span></span>  

 <span data-ttu-id="49ad7-122">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49ad7-122">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49ad7-123">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="49ad7-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="49ad7-124">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="49ad7-124">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="49ad7-125">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49ad7-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49ad7-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="49ad7-126">See also</span></span>

- [<span data-ttu-id="49ad7-127">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="49ad7-127">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
