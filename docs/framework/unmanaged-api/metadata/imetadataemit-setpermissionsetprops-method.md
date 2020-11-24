---
title: IMetaDataEmit::SetPermissionSetProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPermissionSetProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPermissionSetProps
helpviewer_keywords:
- SetPermissionSetProps method [.NET Framework metadata]
- IMetaDataEmit::SetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 8eaee971-40bf-45e2-a3d8-6e57674213b6
topic_type:
- apiref
ms.openlocfilehash: 4c3e0953d71020ba62ee4ab68aa9e21ea3f0f521
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675040"
---
# <a name="imetadataemitsetpermissionsetprops-method"></a><span data-ttu-id="5d08d-102">IMetaDataEmit::SetPermissionSetProps (Método)</span><span class="sxs-lookup"><span data-stu-id="5d08d-102">IMetaDataEmit::SetPermissionSetProps Method</span></span>

<span data-ttu-id="5d08d-103">Establece o actualiza las características de la firma de metadatos de un conjunto de permisos definido por una llamada anterior a [IMetaDataEmit::D efinepermissionset](imetadataemit-definepermissionset-method.md).</span><span class="sxs-lookup"><span data-stu-id="5d08d-103">Sets or updates features of the metadata signature of a permission set defined by a prior call to [IMetaDataEmit::DefinePermissionSet](imetadataemit-definepermissionset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d08d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5d08d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPermissionSetProps (
    [in]  mdToken         tk,
    [in]  DWORD           dwAction,
    [in]  void const      *pvPermission,
    [in]  ULONG           cbPermission,
    [out] mdPermission    *ppm
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d08d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5d08d-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="5d08d-106">de Token de metadatos que representa el objeto que se va a decorar.</span><span class="sxs-lookup"><span data-stu-id="5d08d-106">[in] A metadata token that represents the object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="5d08d-107">de Valor [cordeclsecurity (](cordeclsecurity-enumeration.md) que especifica el tipo de seguridad declarativa que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="5d08d-107">[in] A [CorDeclSecurity](cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="5d08d-108">de El BLOB de permiso.</span><span class="sxs-lookup"><span data-stu-id="5d08d-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="5d08d-109">de Tamaño, en bytes, de `pvPermission` .</span><span class="sxs-lookup"><span data-stu-id="5d08d-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="5d08d-110">enuncia `mdPermission` Token de metadatos que representa los permisos actualizados.</span><span class="sxs-lookup"><span data-stu-id="5d08d-110">[out] An `mdPermission` metadata token that represents the updated permissions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d08d-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5d08d-111">Requirements</span></span>  

 <span data-ttu-id="5d08d-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d08d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d08d-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5d08d-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5d08d-114">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5d08d-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5d08d-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d08d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d08d-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5d08d-116">See also</span></span>

- [<span data-ttu-id="5d08d-117">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5d08d-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="5d08d-118">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5d08d-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
