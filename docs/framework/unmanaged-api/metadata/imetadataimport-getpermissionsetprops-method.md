---
description: 'Más información sobre: IMetaDataImport:: Getpermissionsetprops ((método)'
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
ms.openlocfilehash: 9dc10b7bf531b6eec389334d80cf6a1cece20ee9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789195"
---
# <a name="imetadataimportgetpermissionsetprops-method"></a><span data-ttu-id="c545a-103">IMetaDataImport::GetPermissionSetProps (Método)</span><span class="sxs-lookup"><span data-stu-id="c545a-103">IMetaDataImport::GetPermissionSetProps Method</span></span>

<span data-ttu-id="c545a-104">Obtiene los metadatos asociados al <xref:System.Security.PermissionSet?displayProperty=nameWithType> representado por el token de permiso especificado.</span><span class="sxs-lookup"><span data-stu-id="c545a-104">Gets the metadata associated with the <xref:System.Security.PermissionSet?displayProperty=nameWithType> represented by the specified Permission token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c545a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c545a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetPermissionSetProps (  
   [in]  mdPermission      pm,  
   [out] DWORD             *pdwAction,
   [out] void const        **ppvPermission,
   [out] ULONG             *pcbPermission  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c545a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c545a-106">Parameters</span></span>  

 `pm`  
 <span data-ttu-id="c545a-107">de Token de metadatos de permiso que representa el conjunto de permisos para el que se van a obtener las propiedades de metadatos.</span><span class="sxs-lookup"><span data-stu-id="c545a-107">[in] The Permission metadata token that represents the permission set to get the metadata properties for.</span></span>  
  
 `pdwAction`  
 <span data-ttu-id="c545a-108">enuncia Puntero al conjunto de permisos.</span><span class="sxs-lookup"><span data-stu-id="c545a-108">[out] A pointer to the permission set.</span></span>  
  
 `ppvPermission`  
 <span data-ttu-id="c545a-109">enuncia Puntero a la firma de metadatos binarios del conjunto de permisos.</span><span class="sxs-lookup"><span data-stu-id="c545a-109">[out] A pointer to the binary metadata signature of the permission set.</span></span>  
  
 `pcbPermission`  
 <span data-ttu-id="c545a-110">enuncia Tamaño en bytes de `ppvPermission` .</span><span class="sxs-lookup"><span data-stu-id="c545a-110">[out] The size in bytes of `ppvPermission`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c545a-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c545a-111">Requirements</span></span>  

 <span data-ttu-id="c545a-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c545a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c545a-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c545a-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c545a-114">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c545a-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c545a-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c545a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c545a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c545a-116">See also</span></span>

- <xref:System.Security.PermissionSet>
- [<span data-ttu-id="c545a-117">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c545a-117">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="c545a-118">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c545a-118">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
