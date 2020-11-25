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
ms.openlocfilehash: c46a3bc34ba7efa760e50416e9a6c39779727813
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708934"
---
# <a name="imetadataassemblyemitsetmanifestresourceprops-method"></a><span data-ttu-id="91290-102">IMetaDataAssemblyEmit::SetManifestResourceProps (Método)</span><span class="sxs-lookup"><span data-stu-id="91290-102">IMetaDataAssemblyEmit::SetManifestResourceProps Method</span></span>

<span data-ttu-id="91290-103">Modifica la estructura de metadatos `ManifestResource` especificada.</span><span class="sxs-lookup"><span data-stu-id="91290-103">Modifies the specified `ManifestResource` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91290-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="91290-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManifestResourceProps (  
    [in] mdManifestResource  mr,  
    [in] mdToken             tkImplementation,
    [in] DWORD               dwOffset,  
    [in] DWORD               dwResourceFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91290-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="91290-105">Parameters</span></span>  

 `mr`  
 <span data-ttu-id="91290-106">de El token que especifica la `ManifestResource` estructura de metadatos que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="91290-106">[in] The token that specifies the `ManifestResource` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="91290-107">de Token, de tipo `File` o `AssemblyRef` , que se asigna al proveedor de recursos.</span><span class="sxs-lookup"><span data-stu-id="91290-107">[in] The token, of type `File` or `AssemblyRef`, that maps to the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="91290-108">de Desplazamiento al principio del recurso dentro del archivo.</span><span class="sxs-lookup"><span data-stu-id="91290-108">[in] The offset to the beginning of the resource within the file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="91290-109">de Combinación bit a bit de valores de marca que especifican los atributos del recurso.</span><span class="sxs-lookup"><span data-stu-id="91290-109">[in] A bitwise combination of flag values that specify the attributes of the resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91290-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="91290-110">Remarks</span></span>  

 <span data-ttu-id="91290-111">Para crear una `ManifestResource` estructura de metadatos, use el método [IMetaDataAssemblyEmit::D efinemanifestresource](imetadataassemblyemit-definemanifestresource-method.md) .</span><span class="sxs-lookup"><span data-stu-id="91290-111">To create a `ManifestResource` metadata structure, use the [IMetaDataAssemblyEmit::DefineManifestResource](imetadataassemblyemit-definemanifestresource-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91290-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="91290-112">Requirements</span></span>  

 <span data-ttu-id="91290-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91290-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91290-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="91290-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="91290-115">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="91290-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="91290-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91290-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91290-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="91290-117">See also</span></span>

- [<span data-ttu-id="91290-118">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="91290-118">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
