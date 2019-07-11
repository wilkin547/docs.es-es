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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f77e6e9711f05262e494f2814750af8ef7cd9f64
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750902"
---
# <a name="imetadataemitsetpermissionsetprops-method"></a><span data-ttu-id="c93af-102">IMetaDataEmit::SetPermissionSetProps (Método)</span><span class="sxs-lookup"><span data-stu-id="c93af-102">IMetaDataEmit::SetPermissionSetProps Method</span></span>
<span data-ttu-id="c93af-103">Establece o actualiza las características de la firma de metadatos de un conjunto de permisos definido por una llamada anterior a [DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md).</span><span class="sxs-lookup"><span data-stu-id="c93af-103">Sets or updates features of the metadata signature of a permission set defined by a prior call to [IMetaDataEmit::DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c93af-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c93af-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPermissionSetProps (   
    [in]  mdToken         tk,   
    [in]  DWORD           dwAction,   
    [in]  void const      *pvPermission,   
    [in]  ULONG           cbPermission,   
    [out] mdPermission    *ppm   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c93af-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c93af-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="c93af-106">[in] Un token de metadatos que representa el objeto que va a ser representativo.</span><span class="sxs-lookup"><span data-stu-id="c93af-106">[in] A metadata token that represents the object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="c93af-107">[in] Un [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) valor que especifica el tipo de seguridad declarativa para usarse.</span><span class="sxs-lookup"><span data-stu-id="c93af-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="c93af-108">[in] El permiso de BLOB.</span><span class="sxs-lookup"><span data-stu-id="c93af-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="c93af-109">[in] El tamaño, en bytes, de `pvPermission`.</span><span class="sxs-lookup"><span data-stu-id="c93af-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="c93af-110">[out] Un `mdPermission` token de metadatos que representa los permisos actualizados.</span><span class="sxs-lookup"><span data-stu-id="c93af-110">[out] An `mdPermission` metadata token that represents the updated permissions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c93af-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c93af-111">Requirements</span></span>  
 <span data-ttu-id="c93af-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c93af-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c93af-113">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="c93af-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c93af-114">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c93af-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c93af-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c93af-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c93af-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c93af-116">See also</span></span>

- [<span data-ttu-id="c93af-117">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c93af-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="c93af-118">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c93af-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
