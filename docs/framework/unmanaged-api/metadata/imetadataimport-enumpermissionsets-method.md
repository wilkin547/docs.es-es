---
title: IMetaDataImport::EnumPermissionSets (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumPermissionSets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumPermissionSets
helpviewer_keywords:
- EnumPermissionSets method [.NET Framework metadata]
- IMetaDataImport::EnumPermissionSets method [.NET Framework metadata]
ms.assetid: 347d7e5c-c90f-45ad-bd1e-2c7912b0b19c
topic_type:
- apiref
ms.openlocfilehash: e628cf5dab8006b0df0ab6c60dc995cd0c6bb29d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175452"
---
# <a name="imetadataimportenumpermissionsets-method"></a><span data-ttu-id="24547-102">IMetaDataImport::EnumPermissionSets (Método)</span><span class="sxs-lookup"><span data-stu-id="24547-102">IMetaDataImport::EnumPermissionSets Method</span></span>
<span data-ttu-id="24547-103">Enumera los permisos de los objetos en un ámbito de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="24547-103">Enumerates permissions for the objects in a specified metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24547-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="24547-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumPermissionSets  
   [in, out] HCORENUM      *phEnum,
   [in]      mdToken       tk,
   [in]      DWORD         dwActions,  
   [out]     mdPermission  rPermission[],  
   [in]      ULONG         cMax,  
   [out]     ULONG         *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24547-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="24547-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="24547-106">[adentro, fuera] Un puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="24547-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="24547-107">Debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="24547-107">This must be NULL for the first call of this method.</span></span>  
  
 `tk`  
 <span data-ttu-id="24547-108">[en] Un token de metadatos que limita el ámbito de la búsqueda o NULL para buscar en el ámbito más amplio posible.</span><span class="sxs-lookup"><span data-stu-id="24547-108">[in] A metadata token that limits the scope of the search, or NULL to search the widest scope possible.</span></span>  
  
 `dwActions`  
 <span data-ttu-id="24547-109">[en] Indicadores <xref:System.Security.Permissions.SecurityAction> que representan `rPermission`los valores que se van a incluir en , o cero para devolver todas las acciones.</span><span class="sxs-lookup"><span data-stu-id="24547-109">[in] Flags representing the <xref:System.Security.Permissions.SecurityAction> values to include in `rPermission`, or zero to return all actions.</span></span>  
  
 `rPermission`  
 <span data-ttu-id="24547-110">[fuera] Matriz utilizada para almacenar los tokens de permiso.</span><span class="sxs-lookup"><span data-stu-id="24547-110">[out] The array used to store the Permission tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="24547-111">[in] Tamaño máximo de la matriz `rPermission`.</span><span class="sxs-lookup"><span data-stu-id="24547-111">[in] The maximum size of the `rPermission` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="24547-112">[fuera] El número de tokens `rPermission`de permiso devueltos en .</span><span class="sxs-lookup"><span data-stu-id="24547-112">[out] The number of Permission tokens returned in `rPermission`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="24547-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="24547-113">Return Value</span></span>  
  
|<span data-ttu-id="24547-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="24547-114">HRESULT</span></span>|<span data-ttu-id="24547-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="24547-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="24547-116">`EnumPermissionSets`regresó con éxito.</span><span class="sxs-lookup"><span data-stu-id="24547-116">`EnumPermissionSets` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="24547-117">No hay tokens para enumerar.</span><span class="sxs-lookup"><span data-stu-id="24547-117">There are no tokens to enumerate.</span></span> <span data-ttu-id="24547-118">En ese `pcTokens` caso, es cero.</span><span class="sxs-lookup"><span data-stu-id="24547-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="24547-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="24547-119">Requirements</span></span>  
 <span data-ttu-id="24547-120">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24547-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24547-121">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="24547-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="24547-122">**Biblioteca:** Incluido como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="24547-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="24547-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24547-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24547-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="24547-124">See also</span></span>

- [<span data-ttu-id="24547-125">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="24547-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="24547-126">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="24547-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
