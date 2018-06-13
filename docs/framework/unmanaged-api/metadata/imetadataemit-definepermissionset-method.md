---
title: IMetaDataEmit::DefinePermissionSet (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefinePermissionSet
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefinePermissionSet
helpviewer_keywords:
- DefinePermissionSet method [.NET Framework metadata]
- IMetaDataEmit::DefinePermissionSet method [.NET Framework metadata]
ms.assetid: 36cffbf7-82ca-4cf9-bf60-50ab491ac2d9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 05339787b112ad029cb9870e8c6ffca37e55e631
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445194"
---
# <a name="imetadataemitdefinepermissionset-method"></a><span data-ttu-id="7211f-102">IMetaDataEmit::DefinePermissionSet (Método)</span><span class="sxs-lookup"><span data-stu-id="7211f-102">IMetaDataEmit::DefinePermissionSet Method</span></span>
<span data-ttu-id="7211f-103">Crea una definición para un conjunto de permisos con la firma de metadatos especificada y obtiene un símbolo (token) para dicha definición de conjunto de permisos.</span><span class="sxs-lookup"><span data-stu-id="7211f-103">Creates a definition for a permission set with the specified metadata signature, and gets a token to that permission set definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7211f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7211f-104">Syntax</span></span>  
  
```  
HRESULT DefinePermissionSet (  
    [in]  mdToken        tk,   
    [in]  DWORD          dwAction,   
    [in]  void const     *pvPermission,   
    [in]  ULONG          cbPermission,   
    [out] mdPermission   *ppm   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7211f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7211f-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="7211f-106">[in] El objeto que va a ser representativo.</span><span class="sxs-lookup"><span data-stu-id="7211f-106">[in] The object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="7211f-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) valor que especifica el tipo de seguridad declarativa que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="7211f-107">[in] A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="7211f-108">[in] El BLOB de permiso.</span><span class="sxs-lookup"><span data-stu-id="7211f-108">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="7211f-109">[in] El tamaño, en bytes, de `pvPermission`.</span><span class="sxs-lookup"><span data-stu-id="7211f-109">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="7211f-110">[out] El token de permiso devuelto.</span><span class="sxs-lookup"><span data-stu-id="7211f-110">[out] The returned permission token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7211f-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7211f-111">Requirements</span></span>  
 <span data-ttu-id="7211f-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7211f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7211f-113">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7211f-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7211f-114">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7211f-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7211f-115">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7211f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7211f-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="7211f-116">See Also</span></span>  
 [<span data-ttu-id="7211f-117">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7211f-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="7211f-118">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7211f-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
