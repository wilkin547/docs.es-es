---
title: "IMetaDataEmit::SetPermissionSetProps (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetPermissionSetProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetPermissionSetProps
helpviewer_keywords:
- SetPermissionSetProps method [.NET Framework metadata]
- IMetaDataEmit::SetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 8eaee971-40bf-45e2-a3d8-6e57674213b6
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 34f2357de8d7ec522b4d10212eb82e351df8d152
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitsetpermissionsetprops-method"></a><span data-ttu-id="e9a38-102">IMetaDataEmit::SetPermissionSetProps (Método)</span><span class="sxs-lookup"><span data-stu-id="e9a38-102">IMetaDataEmit::SetPermissionSetProps Method</span></span>
<span data-ttu-id="e9a38-103">Establece o actualiza las características de la firma de metadatos de un conjunto de permisos definido por una llamada anterior a [IMetaDataEmit:: DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md).</span><span class="sxs-lookup"><span data-stu-id="e9a38-103">Sets or updates features of the metadata signature of a permission set defined by a prior call to [IMetaDataEmit::DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9a38-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e9a38-104">Syntax</span></span>  
  
```  
HRESULT SetPermissionSetProps (   
    [in]  mdToken         tk,   
    [in]  DWORD           dwAction,   
    [in]  void const      *pvPermission,   
    [in]  ULONG           cbPermission,   
    [out] mdPermission    *ppm   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e9a38-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e9a38-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="e9a38-106">[in] Símbolo (token) de metadatos que representa el objeto que va a ser representativo.</span><span class="sxs-lookup"><span data-stu-id="e9a38-106">[in] A metadata token that represents the object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="e9a38-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) valor que especifica el tipo de seguridad declarativa que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="e9a38-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="e9a38-108">[in] El BLOB de permiso.</span><span class="sxs-lookup"><span data-stu-id="e9a38-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="e9a38-109">[in] El tamaño, en bytes, de `pvPermission`.</span><span class="sxs-lookup"><span data-stu-id="e9a38-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="e9a38-110">[out] Un `mdPermission` símbolo (token) de metadatos que representa los permisos actualizados.</span><span class="sxs-lookup"><span data-stu-id="e9a38-110">[out] An `mdPermission` metadata token that represents the updated permissions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9a38-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e9a38-111">Requirements</span></span>  
 <span data-ttu-id="e9a38-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9a38-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9a38-113">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e9a38-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e9a38-114">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e9a38-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9a38-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9a38-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9a38-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9a38-116">See Also</span></span>  
 [<span data-ttu-id="e9a38-117">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e9a38-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="e9a38-118">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e9a38-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
