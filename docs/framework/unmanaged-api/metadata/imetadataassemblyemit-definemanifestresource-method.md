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
ms.openlocfilehash: 026f5efe195cdb34999b65c5f47de6f68d30e11a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008136"
---
# <a name="imetadataassemblyemitdefinemanifestresource-method"></a><span data-ttu-id="6eeca-102">IMetaDataAssemblyEmit::DefineManifestResource (Método)</span><span class="sxs-lookup"><span data-stu-id="6eeca-102">IMetaDataAssemblyEmit::DefineManifestResource Method</span></span>
<span data-ttu-id="6eeca-103">Crea una estructura `ManifestResource` que contiene los metadatos para el recurso de manifiesto especificado y devuelve el token de metadatos asociado.</span><span class="sxs-lookup"><span data-stu-id="6eeca-103">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6eeca-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6eeca-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineManifestResource (  
    [in] LPCWSTR                szName,
    [in] mdToken                tkImplementation,
    [in] DWORD                  dwOffset,
    [in] DWORD                  dwResourceFlags,  
    [out] mdManifestResource    *pmdmr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6eeca-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6eeca-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="6eeca-106">[in] Nombre del recurso.</span><span class="sxs-lookup"><span data-stu-id="6eeca-106">[in] The name of the resource.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="6eeca-107">de Símbolo (token) de metadatos de tipo `mdtFile` o `mdtAssemblyRef` que se asigna al proveedor de recursos.</span><span class="sxs-lookup"><span data-stu-id="6eeca-107">[in] A metadata token of type `mdtFile` or `mdtAssemblyRef` that maps to the resource provider.</span></span> <span data-ttu-id="6eeca-108">Un valor NULL indica que el archivo en el que se incrustan los metadatos es el proveedor de recursos.</span><span class="sxs-lookup"><span data-stu-id="6eeca-108">A NULL value indicates that the file in which the metadata is embedded is the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="6eeca-109">de Desplazamiento al principio del recurso dentro del archivo.</span><span class="sxs-lookup"><span data-stu-id="6eeca-109">[in] The offset to the beginning of the resource within the file.</span></span> <span data-ttu-id="6eeca-110">En el caso de los recursos de archivos independientes, siempre será cero.</span><span class="sxs-lookup"><span data-stu-id="6eeca-110">For resources in standalone files, this will always be zero.</span></span> <span data-ttu-id="6eeca-111">Si el recurso está incrustado en un archivo PE (portable ejecutable), se trata de un desplazamiento del BLOB de recursos, que se inicia en la ubicación especificada en el archivo de encabezado Cor. h.</span><span class="sxs-lookup"><span data-stu-id="6eeca-111">If the resource is embedded in a PE (portable executable) file, this is an offset of the resource BLOB, which starts at the location specified in the cor.h header file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="6eeca-112">de Combinación bit a bit de valores de marca que especifican los valores de propiedad para la definición de recursos.</span><span class="sxs-lookup"><span data-stu-id="6eeca-112">[in] A bitwise combination of flag values that specify property settings for the resource definition.</span></span>  
  
 `pmdmr`  
 <span data-ttu-id="6eeca-113">enuncia Puntero al token de metadatos devuelto.</span><span class="sxs-lookup"><span data-stu-id="6eeca-113">[out] A pointer to the returned metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6eeca-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6eeca-114">Remarks</span></span>  
 <span data-ttu-id="6eeca-115">`ManifestResource`Se debe definir una estructura de metadatos para cada recurso que se implementa en cada uno de los archivos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="6eeca-115">One `ManifestResource` metadata structure must be defined for each resource that is implemented in each of the assembly's files.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6eeca-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6eeca-116">Requirements</span></span>  
 <span data-ttu-id="6eeca-117">**Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6eeca-117">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6eeca-118">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6eeca-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6eeca-119">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6eeca-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6eeca-120">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6eeca-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6eeca-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6eeca-121">See also</span></span>

- [<span data-ttu-id="6eeca-122">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6eeca-122">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
