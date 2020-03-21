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
ms.openlocfilehash: 5faf1a6ae89045b2ef17fab789ee6e5bf23eecf2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175348"
---
# <a name="imetadataimportgetpermissionsetprops-method"></a><span data-ttu-id="aeffc-102">IMetaDataImport::GetPermissionSetProps (Método)</span><span class="sxs-lookup"><span data-stu-id="aeffc-102">IMetaDataImport::GetPermissionSetProps Method</span></span>
<span data-ttu-id="aeffc-103">Obtiene los metadatos asociados con el <xref:System.Security.PermissionSet?displayProperty=nameWithType> representado por el token de permiso especificado.</span><span class="sxs-lookup"><span data-stu-id="aeffc-103">Gets the metadata associated with the <xref:System.Security.PermissionSet?displayProperty=nameWithType> represented by the specified Permission token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aeffc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aeffc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPermissionSetProps (  
   [in]  mdPermission      pm,  
   [out] DWORD             *pdwAction,
   [out] void const        **ppvPermission,
   [out] ULONG             *pcbPermission  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aeffc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aeffc-105">Parameters</span></span>  
 `pm`  
 <span data-ttu-id="aeffc-106">[en] El token de metadatos Permission que representa el conjunto de permisos para el que se obtienen las propiedades de metadatos.</span><span class="sxs-lookup"><span data-stu-id="aeffc-106">[in] The Permission metadata token that represents the permission set to get the metadata properties for.</span></span>  
  
 `pdwAction`  
 <span data-ttu-id="aeffc-107">[fuera] Un puntero al conjunto de permisos.</span><span class="sxs-lookup"><span data-stu-id="aeffc-107">[out] A pointer to the permission set.</span></span>  
  
 `ppvPermission`  
 <span data-ttu-id="aeffc-108">[fuera] Puntero a la firma de metadatos binarios del conjunto de permisos.</span><span class="sxs-lookup"><span data-stu-id="aeffc-108">[out] A pointer to the binary metadata signature of the permission set.</span></span>  
  
 `pcbPermission`  
 <span data-ttu-id="aeffc-109">[fuera] El tamaño en `ppvPermission`bytes de .</span><span class="sxs-lookup"><span data-stu-id="aeffc-109">[out] The size in bytes of `ppvPermission`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aeffc-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aeffc-110">Requirements</span></span>  
 <span data-ttu-id="aeffc-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aeffc-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aeffc-112">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="aeffc-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="aeffc-113">**Biblioteca:** Incluido como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="aeffc-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="aeffc-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aeffc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aeffc-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aeffc-115">See also</span></span>

- <xref:System.Security.PermissionSet>
- [<span data-ttu-id="aeffc-116">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aeffc-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="aeffc-117">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aeffc-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
