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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a7d9874d4a609c353ae772b75a48af632bf4e85d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756546"
---
# <a name="imetadataimportenumpermissionsets-method"></a><span data-ttu-id="58b25-102">IMetaDataImport::EnumPermissionSets (Método)</span><span class="sxs-lookup"><span data-stu-id="58b25-102">IMetaDataImport::EnumPermissionSets Method</span></span>
<span data-ttu-id="58b25-103">Enumera los permisos de los objetos en un ámbito de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="58b25-103">Enumerates permissions for the objects in a specified metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58b25-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="58b25-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="58b25-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="58b25-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="58b25-106">[in, out] Un puntero en el enumerador.</span><span class="sxs-lookup"><span data-stu-id="58b25-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="58b25-107">Esto debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="58b25-107">This must be NULL for the first call of this method.</span></span>  
  
 `tk`  
 <span data-ttu-id="58b25-108">[in] Un token de metadatos que limita el ámbito de la búsqueda, o NULL para buscar el ámbito más amplio posible.</span><span class="sxs-lookup"><span data-stu-id="58b25-108">[in] A metadata token that limits the scope of the search, or NULL to search the widest scope possible.</span></span>  
  
 `dwActions`  
 <span data-ttu-id="58b25-109">[in] Marcas que representan el <xref:System.Security.Permissions.SecurityAction> valores que desea incluir en `rPermission`, o cero para devolver todas las acciones.</span><span class="sxs-lookup"><span data-stu-id="58b25-109">[in] Flags representing the <xref:System.Security.Permissions.SecurityAction> values to include in `rPermission`, or zero to return all actions.</span></span>  
  
 `rPermission`  
 <span data-ttu-id="58b25-110">[out] Matriz utilizada para almacenar los tokens de permiso.</span><span class="sxs-lookup"><span data-stu-id="58b25-110">[out] The array used to store the Permission tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="58b25-111">[in] Tamaño máximo de la matriz `rPermission`.</span><span class="sxs-lookup"><span data-stu-id="58b25-111">[in] The maximum size of the `rPermission` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="58b25-112">[out] El número de tokens de permiso que se devuelven en `rPermission`.</span><span class="sxs-lookup"><span data-stu-id="58b25-112">[out] The number of Permission tokens returned in `rPermission`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="58b25-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="58b25-113">Return Value</span></span>  
  
|<span data-ttu-id="58b25-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="58b25-114">HRESULT</span></span>|<span data-ttu-id="58b25-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="58b25-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="58b25-116">`EnumPermissionSets` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="58b25-116">`EnumPermissionSets` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="58b25-117">No hay ningún token para enumerar.</span><span class="sxs-lookup"><span data-stu-id="58b25-117">There are no tokens to enumerate.</span></span> <span data-ttu-id="58b25-118">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="58b25-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="58b25-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="58b25-119">Requirements</span></span>  
 <span data-ttu-id="58b25-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58b25-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58b25-121">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="58b25-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="58b25-122">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="58b25-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="58b25-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58b25-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58b25-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="58b25-124">See also</span></span>

- [<span data-ttu-id="58b25-125">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="58b25-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="58b25-126">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="58b25-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
