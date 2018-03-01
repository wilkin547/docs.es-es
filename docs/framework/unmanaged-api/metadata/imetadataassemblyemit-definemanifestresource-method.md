---
title: "IMetaDataAssemblyEmit::DefineManifestResource (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataAssemblyEmit.DefineManifestResource
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineManifestResource
helpviewer_keywords:
- DefineManifestResource method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineManifestResource method [.NET Framework metadata]
ms.assetid: 27f6d295-0fe9-4cda-b77e-6e7d5c53df09
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a435c946e13950faad7545e3da78ce373ee7fa0d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyemitdefinemanifestresource-method"></a><span data-ttu-id="3de7e-102">IMetaDataAssemblyEmit::DefineManifestResource (Método)</span><span class="sxs-lookup"><span data-stu-id="3de7e-102">IMetaDataAssemblyEmit::DefineManifestResource Method</span></span>
<span data-ttu-id="3de7e-103">Crea una estructura `ManifestResource` que contiene los metadatos para el recurso de manifiesto especificado y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="3de7e-103">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3de7e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3de7e-104">Syntax</span></span>  
  
```  
HRESULT DefineManifestResource (  
    [in] LPCWSTR                szName,   
    [in] mdToken                tkImplementation,   
    [in] DWORD                  dwOffset,   
    [in] DWORD                  dwResourceFlags,  
    [out] mdManifestResource    *pmdmr  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3de7e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3de7e-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="3de7e-106">[in] El nombre del recurso.</span><span class="sxs-lookup"><span data-stu-id="3de7e-106">[in] The name of the resource.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="3de7e-107">[in] Un token de metadatos del tipo `mdtFile` o `mdtAssemblyRef` que se asigna al proveedor de recursos.</span><span class="sxs-lookup"><span data-stu-id="3de7e-107">[in] A metadata token of type `mdtFile` or `mdtAssemblyRef` that maps to the resource provider.</span></span> <span data-ttu-id="3de7e-108">Un valor NULL indica que el archivo en el que se incrustan los metadatos es el proveedor de recursos.</span><span class="sxs-lookup"><span data-stu-id="3de7e-108">A NULL value indicates that the file in which the metadata is embedded is the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="3de7e-109">[in] El desplazamiento al principio del recurso dentro del archivo.</span><span class="sxs-lookup"><span data-stu-id="3de7e-109">[in] The offset to the beginning of the resource within the file.</span></span> <span data-ttu-id="3de7e-110">Para obtener recursos en archivos independientes, siempre será cero.</span><span class="sxs-lookup"><span data-stu-id="3de7e-110">For resources in standalone files, this will always be zero.</span></span> <span data-ttu-id="3de7e-111">Si el recurso está incrustado en un archivo de PE (ejecutable portable), esto es un desplazamiento del recurso BLOB, que comienza en la ubicación especificada en el archivo de encabezado cor.h.</span><span class="sxs-lookup"><span data-stu-id="3de7e-111">If the resource is embedded in a PE (portable executable) file, this is an offset of the resource BLOB, which starts at the location specified in the cor.h header file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="3de7e-112">[in] Una combinación bit a bit de valores de indicador que especifican los valores de propiedad para la definición de recursos.</span><span class="sxs-lookup"><span data-stu-id="3de7e-112">[in] A bitwise combination of flag values that specify property settings for the resource definition.</span></span>  
  
 `pmdmr`  
 <span data-ttu-id="3de7e-113">[out] Un puntero al token de metadatos devuelto.</span><span class="sxs-lookup"><span data-stu-id="3de7e-113">[out] A pointer to the returned metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3de7e-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3de7e-114">Remarks</span></span>  
 <span data-ttu-id="3de7e-115">Una `ManifestResource` se debe definir la estructura de los metadatos para cada recurso que se implementa en cada uno de los archivos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3de7e-115">One `ManifestResource` metadata structure must be defined for each resource that is implemented in each of the assembly's files.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3de7e-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3de7e-116">Requirements</span></span>  
 <span data-ttu-id="3de7e-117">**Plataforma:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3de7e-117">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3de7e-118">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3de7e-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3de7e-119">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3de7e-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3de7e-120">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3de7e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3de7e-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="3de7e-121">See Also</span></span>  
 [<span data-ttu-id="3de7e-122">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3de7e-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
