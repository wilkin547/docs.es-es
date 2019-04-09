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
ms.openlocfilehash: c6fbc3f41e95730e93bd907762dd8cd4205037c8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59187309"
---
# <a name="imetadataassemblyemitsetmanifestresourceprops-method"></a><span data-ttu-id="bd3df-102">IMetaDataAssemblyEmit::SetManifestResourceProps (Método)</span><span class="sxs-lookup"><span data-stu-id="bd3df-102">IMetaDataAssemblyEmit::SetManifestResourceProps Method</span></span>
<span data-ttu-id="bd3df-103">Modifica la estructura de metadatos `ManifestResource` especificada.</span><span class="sxs-lookup"><span data-stu-id="bd3df-103">Modifies the specified `ManifestResource` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd3df-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bd3df-104">Syntax</span></span>  
  
```  
HRESULT SetManifestResourceProps (  
    [in] mdManifestResource  mr,  
    [in] mdToken             tkImplementation,   
    [in] DWORD               dwOffset,  
    [in] DWORD               dwResourceFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd3df-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bd3df-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="bd3df-106">[in] El símbolo (token) que especifica el `ManifestResource` estructura de metadatos que se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="bd3df-106">[in] The token that specifies the `ManifestResource` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="bd3df-107">[in] El token de tipo `File` o `AssemblyRef`, que se asigna al proveedor de recursos.</span><span class="sxs-lookup"><span data-stu-id="bd3df-107">[in] The token, of type `File` or `AssemblyRef`, that maps to the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="bd3df-108">[in] El desplazamiento al principio del recurso dentro del archivo.</span><span class="sxs-lookup"><span data-stu-id="bd3df-108">[in] The offset to the beginning of the resource within the file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="bd3df-109">[in] Una combinación bit a bit de valores de indicador que especifican los atributos del recurso.</span><span class="sxs-lookup"><span data-stu-id="bd3df-109">[in] A bitwise combination of flag values that specify the attributes of the resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd3df-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bd3df-110">Remarks</span></span>  
 <span data-ttu-id="bd3df-111">Para crear un `ManifestResource` estructura de los metadatos, use el [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="bd3df-111">To create a `ManifestResource` metadata structure, use the [IMetaDataAssemblyEmit::DefineManifestResource](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd3df-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bd3df-112">Requirements</span></span>  
 <span data-ttu-id="bd3df-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd3df-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd3df-114">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="bd3df-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bd3df-115">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bd3df-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="bd3df-116">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="bd3df-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bd3df-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd3df-117">See also</span></span>

- [<span data-ttu-id="bd3df-118">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bd3df-118">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
