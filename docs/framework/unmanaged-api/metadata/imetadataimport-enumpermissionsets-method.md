---
description: 'Más información sobre: IMetaDataImport:: Enumpermissionsets ((método)'
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
ms.openlocfilehash: 7138cb2a89ecbea1afbf3e9fccfcac26e7e0fd7a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688759"
---
# <a name="imetadataimportenumpermissionsets-method"></a><span data-ttu-id="befd9-103">IMetaDataImport::EnumPermissionSets (Método)</span><span class="sxs-lookup"><span data-stu-id="befd9-103">IMetaDataImport::EnumPermissionSets Method</span></span>

<span data-ttu-id="befd9-104">Enumera los permisos de los objetos en un ámbito de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="befd9-104">Enumerates permissions for the objects in a specified metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="befd9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="befd9-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="befd9-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="befd9-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="befd9-107">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="befd9-107">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="befd9-108">Debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="befd9-108">This must be NULL for the first call of this method.</span></span>  
  
 `tk`  
 <span data-ttu-id="befd9-109">de Un token de metadatos que limita el ámbito de la búsqueda o NULL para buscar el ámbito más amplio posible.</span><span class="sxs-lookup"><span data-stu-id="befd9-109">[in] A metadata token that limits the scope of the search, or NULL to search the widest scope possible.</span></span>  
  
 `dwActions`  
 <span data-ttu-id="befd9-110">de Marcas que representan los <xref:System.Security.Permissions.SecurityAction> valores que se van a incluir en `rPermission` , o cero, para devolver todas las acciones.</span><span class="sxs-lookup"><span data-stu-id="befd9-110">[in] Flags representing the <xref:System.Security.Permissions.SecurityAction> values to include in `rPermission`, or zero to return all actions.</span></span>  
  
 `rPermission`  
 <span data-ttu-id="befd9-111">enuncia Matriz utilizada para almacenar los tokens de permiso.</span><span class="sxs-lookup"><span data-stu-id="befd9-111">[out] The array used to store the Permission tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="befd9-112">[in] Tamaño máximo de la matriz `rPermission`.</span><span class="sxs-lookup"><span data-stu-id="befd9-112">[in] The maximum size of the `rPermission` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="befd9-113">enuncia El número de tokens de permiso devueltos en `rPermission` .</span><span class="sxs-lookup"><span data-stu-id="befd9-113">[out] The number of Permission tokens returned in `rPermission`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="befd9-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="befd9-114">Return Value</span></span>  
  
|<span data-ttu-id="befd9-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="befd9-115">HRESULT</span></span>|<span data-ttu-id="befd9-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="befd9-116">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="befd9-117">`EnumPermissionSets` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="befd9-117">`EnumPermissionSets` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="befd9-118">No hay tokens que enumerar.</span><span class="sxs-lookup"><span data-stu-id="befd9-118">There are no tokens to enumerate.</span></span> <span data-ttu-id="befd9-119">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="befd9-119">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="befd9-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="befd9-120">Requirements</span></span>  

 <span data-ttu-id="befd9-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="befd9-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="befd9-122">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="befd9-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="befd9-123">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="befd9-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="befd9-124">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="befd9-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="befd9-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="befd9-125">See also</span></span>

- [<span data-ttu-id="befd9-126">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="befd9-126">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="befd9-127">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="befd9-127">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
