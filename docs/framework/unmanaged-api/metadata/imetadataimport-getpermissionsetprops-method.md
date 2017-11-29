---
title: "IMetaDataImport::GetPermissionSetProps (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetPermissionSetProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetPermissionSetProps
helpviewer_keywords:
- GetPermissionSetProps method [.NET Framework metadata]
- IMetaDataImport::GetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 9855f0e4-12c0-4d3d-ab5d-d6bc52d25eae
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2556c0beee7a21d2f01c403ab141054e5bf68177
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetpermissionsetprops-method"></a><span data-ttu-id="5e9c9-102">IMetaDataImport::GetPermissionSetProps (Método)</span><span class="sxs-lookup"><span data-stu-id="5e9c9-102">IMetaDataImport::GetPermissionSetProps Method</span></span>
<span data-ttu-id="5e9c9-103">Obtiene los metadatos asociados a la <xref:System.Security.PermissionSet?displayProperty=nameWithType> representado por el token de permiso especificado.</span><span class="sxs-lookup"><span data-stu-id="5e9c9-103">Gets the metadata associated with the <xref:System.Security.PermissionSet?displayProperty=nameWithType> represented by the specified Permission token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e9c9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5e9c9-104">Syntax</span></span>  
  
```  
HRESULT GetPermissionSetProps (  
   [in]  mdPermission      pm,  
   [out] DWORD             *pdwAction,   
   [out] void const        **ppvPermission,   
   [out] ULONG             *pcbPermission  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5e9c9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5e9c9-105">Parameters</span></span>  
 `pm`  
 <span data-ttu-id="5e9c9-106">[in] El token de metadatos de permiso que representa el permiso establecido para obtener las propiedades de metadatos.</span><span class="sxs-lookup"><span data-stu-id="5e9c9-106">[in] The Permission metadata token that represents the permission set to get the metadata properties for.</span></span>  
  
 `pdwAction`  
 <span data-ttu-id="5e9c9-107">[out] Un puntero al conjunto de permisos.</span><span class="sxs-lookup"><span data-stu-id="5e9c9-107">[out] A pointer to the permission set.</span></span>  
  
 `ppvPermission`  
 <span data-ttu-id="5e9c9-108">[out] Un puntero a la firma de metadatos binaria del conjunto de permisos.</span><span class="sxs-lookup"><span data-stu-id="5e9c9-108">[out] A pointer to the binary metadata signature of the permission set.</span></span>  
  
 `pcbPermission`  
 <span data-ttu-id="5e9c9-109">[out] El tamaño en bytes de `ppvPermission`.</span><span class="sxs-lookup"><span data-stu-id="5e9c9-109">[out] The size in bytes of `ppvPermission`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e9c9-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5e9c9-110">Requirements</span></span>  
 <span data-ttu-id="5e9c9-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e9c9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e9c9-112">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5e9c9-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5e9c9-113">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5e9c9-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5e9c9-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e9c9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e9c9-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e9c9-115">See Also</span></span>  
 <xref:System.Security.PermissionSet>  
 [<span data-ttu-id="5e9c9-116">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5e9c9-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="5e9c9-117">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5e9c9-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
