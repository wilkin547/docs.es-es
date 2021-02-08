---
description: 'Más información sobre: IMetaDataEmit:: Setpermissionsetprops ((método)'
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
ms.openlocfilehash: 1e2786a21a1024f32328e36878a1a2427af54f51
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99771891"
---
# <a name="imetadataemitsetpermissionsetprops-method"></a><span data-ttu-id="6f2ad-103">IMetaDataEmit::SetPermissionSetProps (Método)</span><span class="sxs-lookup"><span data-stu-id="6f2ad-103">IMetaDataEmit::SetPermissionSetProps Method</span></span>

<span data-ttu-id="6f2ad-104">Establece o actualiza las características de la firma de metadatos de un conjunto de permisos definido por una llamada anterior a [IMetaDataEmit::D efinepermissionset](imetadataemit-definepermissionset-method.md).</span><span class="sxs-lookup"><span data-stu-id="6f2ad-104">Sets or updates features of the metadata signature of a permission set defined by a prior call to [IMetaDataEmit::DefinePermissionSet](imetadataemit-definepermissionset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f2ad-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6f2ad-105">Syntax</span></span>  
  
```cpp  
HRESULT SetPermissionSetProps (
    [in]  mdToken         tk,
    [in]  DWORD           dwAction,
    [in]  void const      *pvPermission,
    [in]  ULONG           cbPermission,
    [out] mdPermission    *ppm
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f2ad-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6f2ad-106">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="6f2ad-107">de Token de metadatos que representa el objeto que se va a decorar.</span><span class="sxs-lookup"><span data-stu-id="6f2ad-107">[in] A metadata token that represents the object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="6f2ad-108">de Valor [cordeclsecurity (](cordeclsecurity-enumeration.md) que especifica el tipo de seguridad declarativa que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="6f2ad-108">[in] A [CorDeclSecurity](cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="6f2ad-109">de El BLOB de permiso.</span><span class="sxs-lookup"><span data-stu-id="6f2ad-109">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="6f2ad-110">de Tamaño, en bytes, de `pvPermission` .</span><span class="sxs-lookup"><span data-stu-id="6f2ad-110">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="6f2ad-111">enuncia `mdPermission` Token de metadatos que representa los permisos actualizados.</span><span class="sxs-lookup"><span data-stu-id="6f2ad-111">[out] An `mdPermission` metadata token that represents the updated permissions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f2ad-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6f2ad-112">Requirements</span></span>  

 <span data-ttu-id="6f2ad-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f2ad-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f2ad-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6f2ad-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6f2ad-115">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6f2ad-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6f2ad-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f2ad-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f2ad-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f2ad-117">See also</span></span>

- [<span data-ttu-id="6f2ad-118">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6f2ad-118">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="6f2ad-119">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6f2ad-119">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
