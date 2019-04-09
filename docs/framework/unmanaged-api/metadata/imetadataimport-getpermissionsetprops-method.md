---
title: IMetaDataImport::GetPermissionSetProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPermissionSetProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPermissionSetProps
helpviewer_keywords:
- GetPermissionSetProps method [.NET Framework metadata]
- IMetaDataImport::GetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 9855f0e4-12c0-4d3d-ab5d-d6bc52d25eae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3ff91a24dec7f8507989b701ea24b569c1670c89
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59109720"
---
# <a name="imetadataimportgetpermissionsetprops-method"></a><span data-ttu-id="fc3cf-102">IMetaDataImport::GetPermissionSetProps (Método)</span><span class="sxs-lookup"><span data-stu-id="fc3cf-102">IMetaDataImport::GetPermissionSetProps Method</span></span>
<span data-ttu-id="fc3cf-103">Obtiene los metadatos asociados con el <xref:System.Security.PermissionSet?displayProperty=nameWithType> representado por el token de permiso especificado.</span><span class="sxs-lookup"><span data-stu-id="fc3cf-103">Gets the metadata associated with the <xref:System.Security.PermissionSet?displayProperty=nameWithType> represented by the specified Permission token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc3cf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc3cf-104">Syntax</span></span>  
  
```  
HRESULT GetPermissionSetProps (  
   [in]  mdPermission      pm,  
   [out] DWORD             *pdwAction,   
   [out] void const        **ppvPermission,   
   [out] ULONG             *pcbPermission  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc3cf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fc3cf-105">Parameters</span></span>  
 `pm`  
 <span data-ttu-id="fc3cf-106">[in] El token de metadatos de permiso que representa el permiso establecido para obtener las propiedades de metadatos.</span><span class="sxs-lookup"><span data-stu-id="fc3cf-106">[in] The Permission metadata token that represents the permission set to get the metadata properties for.</span></span>  
  
 `pdwAction`  
 <span data-ttu-id="fc3cf-107">[out] Un puntero al conjunto de permisos.</span><span class="sxs-lookup"><span data-stu-id="fc3cf-107">[out] A pointer to the permission set.</span></span>  
  
 `ppvPermission`  
 <span data-ttu-id="fc3cf-108">[out] Un puntero a la firma de metadatos binaria del conjunto de permisos.</span><span class="sxs-lookup"><span data-stu-id="fc3cf-108">[out] A pointer to the binary metadata signature of the permission set.</span></span>  
  
 `pcbPermission`  
 <span data-ttu-id="fc3cf-109">[out] El tamaño en bytes de `ppvPermission`.</span><span class="sxs-lookup"><span data-stu-id="fc3cf-109">[out] The size in bytes of `ppvPermission`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc3cf-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fc3cf-110">Requirements</span></span>  
 <span data-ttu-id="fc3cf-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc3cf-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc3cf-112">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="fc3cf-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fc3cf-113">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fc3cf-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="fc3cf-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="fc3cf-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fc3cf-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc3cf-115">See also</span></span>

- <xref:System.Security.PermissionSet>
- [<span data-ttu-id="fc3cf-116">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fc3cf-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="fc3cf-117">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fc3cf-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
