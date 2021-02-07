---
description: 'Más información acerca de: IMetaDataAssemblyEmit::D método efineManifestResource'
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
ms.openlocfilehash: 53994f1777cbd2e019f14c0ccae375e6424de509
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678333"
---
# <a name="imetadataassemblyemitdefinemanifestresource-method"></a><span data-ttu-id="b13c8-103">IMetaDataAssemblyEmit::DefineManifestResource (Método)</span><span class="sxs-lookup"><span data-stu-id="b13c8-103">IMetaDataAssemblyEmit::DefineManifestResource Method</span></span>

<span data-ttu-id="b13c8-104">Crea una estructura `ManifestResource` que contiene los metadatos para el recurso de manifiesto especificado y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="b13c8-104">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b13c8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b13c8-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineManifestResource (  
    [in] LPCWSTR                szName,
    [in] mdToken                tkImplementation,
    [in] DWORD                  dwOffset,
    [in] DWORD                  dwResourceFlags,  
    [out] mdManifestResource    *pmdmr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b13c8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b13c8-106">Parameters</span></span>  

 `szName`  
 <span data-ttu-id="b13c8-107">[in] Nombre del recurso.</span><span class="sxs-lookup"><span data-stu-id="b13c8-107">[in] The name of the resource.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="b13c8-108">de Símbolo (token) de metadatos de tipo `mdtFile` o `mdtAssemblyRef` que se asigna al proveedor de recursos.</span><span class="sxs-lookup"><span data-stu-id="b13c8-108">[in] A metadata token of type `mdtFile` or `mdtAssemblyRef` that maps to the resource provider.</span></span> <span data-ttu-id="b13c8-109">Un valor NULL indica que el archivo en el que se incrustan los metadatos es el proveedor de recursos.</span><span class="sxs-lookup"><span data-stu-id="b13c8-109">A NULL value indicates that the file in which the metadata is embedded is the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="b13c8-110">de Desplazamiento al principio del recurso dentro del archivo.</span><span class="sxs-lookup"><span data-stu-id="b13c8-110">[in] The offset to the beginning of the resource within the file.</span></span> <span data-ttu-id="b13c8-111">En el caso de los recursos de archivos independientes, siempre será cero.</span><span class="sxs-lookup"><span data-stu-id="b13c8-111">For resources in standalone files, this will always be zero.</span></span> <span data-ttu-id="b13c8-112">Si el recurso está incrustado en un archivo PE (portable ejecutable), se trata de un desplazamiento del BLOB de recursos, que se inicia en la ubicación especificada en el archivo de encabezado Cor. h.</span><span class="sxs-lookup"><span data-stu-id="b13c8-112">If the resource is embedded in a PE (portable executable) file, this is an offset of the resource BLOB, which starts at the location specified in the cor.h header file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="b13c8-113">de Combinación bit a bit de valores de marca que especifican los valores de propiedad para la definición de recursos.</span><span class="sxs-lookup"><span data-stu-id="b13c8-113">[in] A bitwise combination of flag values that specify property settings for the resource definition.</span></span>  
  
 `pmdmr`  
 <span data-ttu-id="b13c8-114">enuncia Puntero al token de metadatos devuelto.</span><span class="sxs-lookup"><span data-stu-id="b13c8-114">[out] A pointer to the returned metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b13c8-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b13c8-115">Remarks</span></span>  

 <span data-ttu-id="b13c8-116">`ManifestResource`Se debe definir una estructura de metadatos para cada recurso que se implementa en cada uno de los archivos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b13c8-116">One `ManifestResource` metadata structure must be defined for each resource that is implemented in each of the assembly's files.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b13c8-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b13c8-117">Requirements</span></span>  

 <span data-ttu-id="b13c8-118">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b13c8-118">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b13c8-119">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b13c8-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b13c8-120">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b13c8-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b13c8-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b13c8-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b13c8-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="b13c8-122">See also</span></span>

- [<span data-ttu-id="b13c8-123">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b13c8-123">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
