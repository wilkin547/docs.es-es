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
ms.openlocfilehash: de4cfdf2a9353eebdebaf4df9e481d06d776ff04
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177487"
---
# <a name="imetadataemitsetpermissionsetprops-method"></a><span data-ttu-id="7d2dd-102">IMetaDataEmit::SetPermissionSetProps (Método)</span><span class="sxs-lookup"><span data-stu-id="7d2dd-102">IMetaDataEmit::SetPermissionSetProps Method</span></span>
<span data-ttu-id="7d2dd-103">Establece o actualiza las características de la firma de metadatos de un conjunto de permisos definido por una llamada anterior a [IMetaDataEmit::DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md).</span><span class="sxs-lookup"><span data-stu-id="7d2dd-103">Sets or updates features of the metadata signature of a permission set defined by a prior call to [IMetaDataEmit::DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d2dd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7d2dd-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPermissionSetProps (
    [in]  mdToken         tk,
    [in]  DWORD           dwAction,
    [in]  void const      *pvPermission,
    [in]  ULONG           cbPermission,
    [out] mdPermission    *ppm
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d2dd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7d2dd-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="7d2dd-106">[en] Un token de metadatos que representa el objeto que se va a decorar.</span><span class="sxs-lookup"><span data-stu-id="7d2dd-106">[in] A metadata token that represents the object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="7d2dd-107">[en] Un [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) valor que especifica el tipo de seguridad declarativa que se usará.</span><span class="sxs-lookup"><span data-stu-id="7d2dd-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="7d2dd-108">[en] El permiso BLOB.</span><span class="sxs-lookup"><span data-stu-id="7d2dd-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="7d2dd-109">[en] El tamaño, en `pvPermission`bytes, de .</span><span class="sxs-lookup"><span data-stu-id="7d2dd-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="7d2dd-110">[fuera] Un `mdPermission` token de metadatos que representa los permisos actualizados.</span><span class="sxs-lookup"><span data-stu-id="7d2dd-110">[out] An `mdPermission` metadata token that represents the updated permissions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d2dd-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7d2dd-111">Requirements</span></span>  
 <span data-ttu-id="7d2dd-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d2dd-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d2dd-113">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7d2dd-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7d2dd-114">**Biblioteca:** Se utiliza como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7d2dd-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7d2dd-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d2dd-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d2dd-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7d2dd-116">See also</span></span>

- [<span data-ttu-id="7d2dd-117">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7d2dd-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="7d2dd-118">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7d2dd-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
