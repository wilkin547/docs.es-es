---
title: IMetaDataAssemblyEmit::DefineManifestResource (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: 5aa5d78faa8ca9261594e2a649b11088e1d78ee7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177870"
---
# <a name="imetadataassemblyemitdefinemanifestresource-method"></a><span data-ttu-id="52f19-102">IMetaDataAssemblyEmit::DefineManifestResource (Método)</span><span class="sxs-lookup"><span data-stu-id="52f19-102">IMetaDataAssemblyEmit::DefineManifestResource Method</span></span>
<span data-ttu-id="52f19-103">Crea una estructura `ManifestResource` que contiene los metadatos para el recurso de manifiesto especificado y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="52f19-103">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52f19-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52f19-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineManifestResource (  
    [in] LPCWSTR                szName,
    [in] mdToken                tkImplementation,
    [in] DWORD                  dwOffset,
    [in] DWORD                  dwResourceFlags,  
    [out] mdManifestResource    *pmdmr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52f19-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="52f19-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="52f19-106">[in] Nombre del recurso.</span><span class="sxs-lookup"><span data-stu-id="52f19-106">[in] The name of the resource.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="52f19-107">[en] Un token de `mdtFile` `mdtAssemblyRef` metadatos de tipo o que se asigna al proveedor de recursos.</span><span class="sxs-lookup"><span data-stu-id="52f19-107">[in] A metadata token of type `mdtFile` or `mdtAssemblyRef` that maps to the resource provider.</span></span> <span data-ttu-id="52f19-108">Un valor NULL indica que el archivo en el que se incrustan los metadatos es el proveedor de recursos.</span><span class="sxs-lookup"><span data-stu-id="52f19-108">A NULL value indicates that the file in which the metadata is embedded is the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="52f19-109">[en] Desplazamiento al principio del recurso dentro del archivo.</span><span class="sxs-lookup"><span data-stu-id="52f19-109">[in] The offset to the beginning of the resource within the file.</span></span> <span data-ttu-id="52f19-110">Para los recursos en archivos independientes, esto siempre será cero.</span><span class="sxs-lookup"><span data-stu-id="52f19-110">For resources in standalone files, this will always be zero.</span></span> <span data-ttu-id="52f19-111">Si el recurso está incrustado en un archivo PE (ejecutable portátil), se trata de un desplazamiento del recurso BLOB, que comienza en la ubicación especificada en el archivo de encabezado cor.h.</span><span class="sxs-lookup"><span data-stu-id="52f19-111">If the resource is embedded in a PE (portable executable) file, this is an offset of the resource BLOB, which starts at the location specified in the cor.h header file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="52f19-112">[en] Combinación bit a bit de valores de marca que especifican la configuración de propiedades para la definición de recursos.</span><span class="sxs-lookup"><span data-stu-id="52f19-112">[in] A bitwise combination of flag values that specify property settings for the resource definition.</span></span>  
  
 `pmdmr`  
 <span data-ttu-id="52f19-113">[fuera] Un puntero al token de metadatos devuelto.</span><span class="sxs-lookup"><span data-stu-id="52f19-113">[out] A pointer to the returned metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52f19-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="52f19-114">Remarks</span></span>  
 <span data-ttu-id="52f19-115">Se `ManifestResource` debe definir una estructura de metadatos para cada recurso que se implementa en cada uno de los archivos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="52f19-115">One `ManifestResource` metadata structure must be defined for each resource that is implemented in each of the assembly's files.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52f19-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="52f19-116">Requirements</span></span>  
 <span data-ttu-id="52f19-117">**Plataforma:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52f19-117">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52f19-118">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="52f19-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="52f19-119">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="52f19-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="52f19-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52f19-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52f19-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="52f19-121">See also</span></span>

- [<span data-ttu-id="52f19-122">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="52f19-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
