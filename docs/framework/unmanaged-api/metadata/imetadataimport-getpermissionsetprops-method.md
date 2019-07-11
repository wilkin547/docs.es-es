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
ms.openlocfilehash: 48cd62f89f1112a1007a5661dc55fe2977dace2b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778915"
---
# <a name="imetadataimportgetpermissionsetprops-method"></a><span data-ttu-id="0597e-102">IMetaDataImport::GetPermissionSetProps (Método)</span><span class="sxs-lookup"><span data-stu-id="0597e-102">IMetaDataImport::GetPermissionSetProps Method</span></span>
<span data-ttu-id="0597e-103">Obtiene los metadatos asociados con el <xref:System.Security.PermissionSet?displayProperty=nameWithType> representado por el token de permiso especificado.</span><span class="sxs-lookup"><span data-stu-id="0597e-103">Gets the metadata associated with the <xref:System.Security.PermissionSet?displayProperty=nameWithType> represented by the specified Permission token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0597e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0597e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPermissionSetProps (  
   [in]  mdPermission      pm,  
   [out] DWORD             *pdwAction,   
   [out] void const        **ppvPermission,   
   [out] ULONG             *pcbPermission  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0597e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0597e-105">Parameters</span></span>  
 `pm`  
 <span data-ttu-id="0597e-106">[in] El token de metadatos de permiso que representa el permiso establecido para obtener las propiedades de metadatos.</span><span class="sxs-lookup"><span data-stu-id="0597e-106">[in] The Permission metadata token that represents the permission set to get the metadata properties for.</span></span>  
  
 `pdwAction`  
 <span data-ttu-id="0597e-107">[out] Un puntero al conjunto de permisos.</span><span class="sxs-lookup"><span data-stu-id="0597e-107">[out] A pointer to the permission set.</span></span>  
  
 `ppvPermission`  
 <span data-ttu-id="0597e-108">[out] Un puntero a la firma de metadatos binaria del conjunto de permisos.</span><span class="sxs-lookup"><span data-stu-id="0597e-108">[out] A pointer to the binary metadata signature of the permission set.</span></span>  
  
 `pcbPermission`  
 <span data-ttu-id="0597e-109">[out] El tamaño en bytes de `ppvPermission`.</span><span class="sxs-lookup"><span data-stu-id="0597e-109">[out] The size in bytes of `ppvPermission`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0597e-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0597e-110">Requirements</span></span>  
 <span data-ttu-id="0597e-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0597e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0597e-112">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="0597e-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0597e-113">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0597e-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0597e-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0597e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0597e-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="0597e-115">See also</span></span>

- <xref:System.Security.PermissionSet>
- [<span data-ttu-id="0597e-116">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0597e-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="0597e-117">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0597e-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
