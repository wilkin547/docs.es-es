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
ms.openlocfilehash: 74111a175b0decbc1beef7c8df5ade59d31d845b
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009150"
---
# <a name="imetadataassemblyemitsetmanifestresourceprops-method"></a><span data-ttu-id="dcc86-102">IMetaDataAssemblyEmit::SetManifestResourceProps (Método)</span><span class="sxs-lookup"><span data-stu-id="dcc86-102">IMetaDataAssemblyEmit::SetManifestResourceProps Method</span></span>
<span data-ttu-id="dcc86-103">Modifica la estructura de metadatos `ManifestResource` especificada.</span><span class="sxs-lookup"><span data-stu-id="dcc86-103">Modifies the specified `ManifestResource` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcc86-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dcc86-104">Syntax</span></span>  
  
```cpp  
HRESULT SetManifestResourceProps (  
    [in] mdManifestResource  mr,  
    [in] mdToken             tkImplementation,
    [in] DWORD               dwOffset,  
    [in] DWORD               dwResourceFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dcc86-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dcc86-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="dcc86-106">de El token que especifica la `ManifestResource` estructura de metadatos que se va a modificar.</span><span class="sxs-lookup"><span data-stu-id="dcc86-106">[in] The token that specifies the `ManifestResource` metadata structure to be modified.</span></span>  
  
 `tkImplementation`  
 <span data-ttu-id="dcc86-107">de Token, de tipo `File` o `AssemblyRef` , que se asigna al proveedor de recursos.</span><span class="sxs-lookup"><span data-stu-id="dcc86-107">[in] The token, of type `File` or `AssemblyRef`, that maps to the resource provider.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="dcc86-108">de Desplazamiento al principio del recurso dentro del archivo.</span><span class="sxs-lookup"><span data-stu-id="dcc86-108">[in] The offset to the beginning of the resource within the file.</span></span>  
  
 `dwResourceFlags`  
 <span data-ttu-id="dcc86-109">de Combinación bit a bit de valores de marca que especifican los atributos del recurso.</span><span class="sxs-lookup"><span data-stu-id="dcc86-109">[in] A bitwise combination of flag values that specify the attributes of the resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dcc86-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dcc86-110">Remarks</span></span>  
 <span data-ttu-id="dcc86-111">Para crear una `ManifestResource` estructura de metadatos, use el método [IMetaDataAssemblyEmit::D efinemanifestresource](imetadataassemblyemit-definemanifestresource-method.md) .</span><span class="sxs-lookup"><span data-stu-id="dcc86-111">To create a `ManifestResource` metadata structure, use the [IMetaDataAssemblyEmit::DefineManifestResource](imetadataassemblyemit-definemanifestresource-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcc86-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dcc86-112">Requirements</span></span>  
 <span data-ttu-id="dcc86-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dcc86-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcc86-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="dcc86-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dcc86-115">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="dcc86-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dcc86-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcc86-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcc86-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dcc86-117">See also</span></span>

- [<span data-ttu-id="dcc86-118">IMetaDataAssemblyEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dcc86-118">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
