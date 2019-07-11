---
title: IMetaDataAssemblyEmit::SetManifestResourceProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetManifestResourceProps
helpviewer_keywords:
- SetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetManifestResourceProps method [.NET Framework metadata]
ms.assetid: ef77efd1-849c-4e51-ba92-7ee3d2bf0339
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d080a3077df2cb4ad57ef463b5e02a3a28d8429d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779402"
---
# <a name="imetadataassemblyemitsetmanifestresourceprops-method"></a><span data-ttu-id="a9f35-102">IMetaDataAssemblyEmit::SetManifestResourceProps (Método)</span><span class="sxs-lookup"><span data-stu-id="a9f35-102">IMetaDataAssemblyEmit::SetManifestResourceProps Method</span></span>
<span data-ttu-id="a9f35-103">Modifica la estructura de metadatos `ManifestResource` especificada.</span><span class="sxs-lookup"><span data-stu-id="a9f35-103">Modifies the specified `ManifestResource` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9f35-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9f35-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManifestResourceProps (  
    [in] mdManifestResource  mr,  
    [in] mdToken             tkImplementation,   
    [in] DWORD               dwOffset,  
    [in] DWORD               dwResourceFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9f35-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a9f35-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="a9f35-106">[in] El símbolo (token) que especifica el `ManifestResource` estructura de metadatos que se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="a9f35-106">[in] The token that specifies the `ManifestResource` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="a9f35-107">[in] El token de tipo `File` o `AssemblyRef`, que se asigna al proveedor de recursos.</span><span class="sxs-lookup"><span data-stu-id="a9f35-107">[in] The token, of type `File` or `AssemblyRef`, that maps to the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="a9f35-108">[in] El desplazamiento al principio del recurso dentro del archivo.</span><span class="sxs-lookup"><span data-stu-id="a9f35-108">[in] The offset to the beginning of the resource within the file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="a9f35-109">[in] Una combinación bit a bit de valores de indicador que especifican los atributos del recurso.</span><span class="sxs-lookup"><span data-stu-id="a9f35-109">[in] A bitwise combination of flag values that specify the attributes of the resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9f35-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a9f35-110">Remarks</span></span>  
 <span data-ttu-id="a9f35-111">Para crear un `ManifestResource` estructura de los metadatos, use el [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="a9f35-111">To create a `ManifestResource` metadata structure, use the [IMetaDataAssemblyEmit::DefineManifestResource](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9f35-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9f35-112">Requirements</span></span>  
 <span data-ttu-id="a9f35-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9f35-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9f35-114">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="a9f35-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a9f35-115">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a9f35-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a9f35-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9f35-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9f35-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9f35-117">See also</span></span>

- [<span data-ttu-id="a9f35-118">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a9f35-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
