---
title: "IMetaDataAssemblyEmit::DefineManifestResource (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.DefineManifestResource
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::DefineManifestResource
helpviewer_keywords:
- DefineManifestResource method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineManifestResource method [.NET Framework metadata]
ms.assetid: 27f6d295-0fe9-4cda-b77e-6e7d5c53df09
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 516099f0735e83982fcbab62936bb398c4f7b02d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyemitdefinemanifestresource-method"></a><span data-ttu-id="80a1f-102">IMetaDataAssemblyEmit::DefineManifestResource (Método)</span><span class="sxs-lookup"><span data-stu-id="80a1f-102">IMetaDataAssemblyEmit::DefineManifestResource Method</span></span>
<span data-ttu-id="80a1f-103">Crea una estructura `ManifestResource` que contiene los metadatos para el recurso de manifiesto especificado y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="80a1f-103">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80a1f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="80a1f-104">Syntax</span></span>  
  
```  
HRESULT DefineManifestResource (  
    [in] LPCWSTR                szName,   
    [in] mdToken                tkImplementation,   
    [in] DWORD                  dwOffset,   
    [in] DWORD                  dwResourceFlags,  
    [out] mdManifestResource    *pmdmr  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="80a1f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="80a1f-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="80a1f-106">[in] El nombre del recurso.</span><span class="sxs-lookup"><span data-stu-id="80a1f-106">[in] The name of the resource.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="80a1f-107">[in] Un token de metadatos del tipo `mdtFile` o `mdtAssemblyRef` que se asigna al proveedor de recursos.</span><span class="sxs-lookup"><span data-stu-id="80a1f-107">[in] A metadata token of type `mdtFile` or `mdtAssemblyRef` that maps to the resource provider.</span></span> <span data-ttu-id="80a1f-108">Un valor NULL indica que el archivo en el que se incrustan los metadatos es el proveedor de recursos.</span><span class="sxs-lookup"><span data-stu-id="80a1f-108">A NULL value indicates that the file in which the metadata is embedded is the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="80a1f-109">[in] El desplazamiento al principio del recurso dentro del archivo.</span><span class="sxs-lookup"><span data-stu-id="80a1f-109">[in] The offset to the beginning of the resource within the file.</span></span> <span data-ttu-id="80a1f-110">Para obtener recursos en archivos independientes, siempre será cero.</span><span class="sxs-lookup"><span data-stu-id="80a1f-110">For resources in standalone files, this will always be zero.</span></span> <span data-ttu-id="80a1f-111">Si el recurso está incrustado en un archivo de PE (ejecutable portable), esto es un desplazamiento del recurso BLOB, que comienza en la ubicación especificada en el archivo de encabezado cor.h.</span><span class="sxs-lookup"><span data-stu-id="80a1f-111">If the resource is embedded in a PE (portable executable) file, this is an offset of the resource BLOB, which starts at the location specified in the cor.h header file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="80a1f-112">[in] Una combinación bit a bit de valores de indicador que especifican los valores de propiedad para la definición de recursos.</span><span class="sxs-lookup"><span data-stu-id="80a1f-112">[in] A bitwise combination of flag values that specify property settings for the resource definition.</span></span>  
  
 `pmdmr`  
 <span data-ttu-id="80a1f-113">[out] Un puntero al token de metadatos devuelto.</span><span class="sxs-lookup"><span data-stu-id="80a1f-113">[out] A pointer to the returned metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80a1f-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="80a1f-114">Remarks</span></span>  
 <span data-ttu-id="80a1f-115">Una `ManifestResource` se debe definir la estructura de los metadatos para cada recurso que se implementa en cada uno de los archivos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="80a1f-115">One `ManifestResource` metadata structure must be defined for each resource that is implemented in each of the assembly's files.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80a1f-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="80a1f-116">Requirements</span></span>  
 <span data-ttu-id="80a1f-117">**Plataforma:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80a1f-117">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80a1f-118">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="80a1f-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="80a1f-119">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="80a1f-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="80a1f-120">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80a1f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80a1f-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="80a1f-121">See Also</span></span>  
 [<span data-ttu-id="80a1f-122">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="80a1f-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
