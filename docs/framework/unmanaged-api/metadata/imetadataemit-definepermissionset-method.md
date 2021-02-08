---
description: 'Más información acerca de: IMetaDataEmit::D método efinePermissionSet'
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
ms.openlocfilehash: f5c3f1466217713cb3970c805079d8f65fd429c0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784085"
---
# <a name="imetadataemitdefinepermissionset-method"></a><span data-ttu-id="fa342-103">IMetaDataEmit::DefinePermissionSet (Método)</span><span class="sxs-lookup"><span data-stu-id="fa342-103">IMetaDataEmit::DefinePermissionSet Method</span></span>

<span data-ttu-id="fa342-104">Crea una definición para un conjunto de permisos con la firma de metadatos especificada y obtiene un token para esa definición de conjunto de permisos.</span><span class="sxs-lookup"><span data-stu-id="fa342-104">Creates a definition for a permission set with the specified metadata signature, and gets a token to that permission set definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa342-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa342-105">Syntax</span></span>  
  
```cpp  
HRESULT DefinePermissionSet (  
    [in]  mdToken        tk,
    [in]  DWORD          dwAction,
    [in]  void const     *pvPermission,
    [in]  ULONG          cbPermission,
    [out] mdPermission   *ppm
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa342-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fa342-106">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="fa342-107">de Objeto que se va a decorar.</span><span class="sxs-lookup"><span data-stu-id="fa342-107">[in] The object to be decorated.</span></span>  
  
 `dwAction`  
 <span data-ttu-id="fa342-108">de Valor [cordeclsecurity (](cordeclsecurity-enumeration.md) que especifica el tipo de seguridad declarativa que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="fa342-108">[in] A [CorDeclSecurity](cordeclsecurity-enumeration.md) value that specifies the type of declarative security to be used.</span></span>  
  
 `pvPermission`  
 <span data-ttu-id="fa342-109">de El BLOB de permiso.</span><span class="sxs-lookup"><span data-stu-id="fa342-109">[in] The permission BLOB.</span></span>  
  
 `cbPermission`  
 <span data-ttu-id="fa342-110">de Tamaño, en bytes, de `pvPermission` .</span><span class="sxs-lookup"><span data-stu-id="fa342-110">[in] The size, in bytes, of `pvPermission`.</span></span>  
  
 `ppm`  
 <span data-ttu-id="fa342-111">enuncia El token de permiso devuelto.</span><span class="sxs-lookup"><span data-stu-id="fa342-111">[out] The returned permission token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa342-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fa342-112">Requirements</span></span>  

 <span data-ttu-id="fa342-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa342-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa342-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fa342-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fa342-115">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fa342-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fa342-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa342-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa342-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa342-117">See also</span></span>

- [<span data-ttu-id="fa342-118">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fa342-118">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="fa342-119">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fa342-119">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
