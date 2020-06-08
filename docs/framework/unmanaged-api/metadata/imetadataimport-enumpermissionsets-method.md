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
ms.openlocfilehash: 79b1493d262288c1d85a56538810e35a73441595
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491776"
---
# <a name="imetadataimportenumpermissionsets-method"></a><span data-ttu-id="84a67-102">IMetaDataImport::EnumPermissionSets (Método)</span><span class="sxs-lookup"><span data-stu-id="84a67-102">IMetaDataImport::EnumPermissionSets Method</span></span>
<span data-ttu-id="84a67-103">Enumera los permisos de los objetos en un ámbito de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="84a67-103">Enumerates permissions for the objects in a specified metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84a67-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="84a67-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="84a67-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="84a67-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="84a67-106">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="84a67-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="84a67-107">Debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="84a67-107">This must be NULL for the first call of this method.</span></span>  
  
 `tk`  
 <span data-ttu-id="84a67-108">de Un token de metadatos que limita el ámbito de la búsqueda o NULL para buscar el ámbito más amplio posible.</span><span class="sxs-lookup"><span data-stu-id="84a67-108">[in] A metadata token that limits the scope of the search, or NULL to search the widest scope possible.</span></span>  
  
 `dwActions`  
 <span data-ttu-id="84a67-109">de Marcas que representan los <xref:System.Security.Permissions.SecurityAction> valores que se van a incluir en `rPermission` , o cero, para devolver todas las acciones.</span><span class="sxs-lookup"><span data-stu-id="84a67-109">[in] Flags representing the <xref:System.Security.Permissions.SecurityAction> values to include in `rPermission`, or zero to return all actions.</span></span>  
  
 `rPermission`  
 <span data-ttu-id="84a67-110">enuncia Matriz utilizada para almacenar los tokens de permiso.</span><span class="sxs-lookup"><span data-stu-id="84a67-110">[out] The array used to store the Permission tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="84a67-111">[in] Tamaño máximo de la matriz `rPermission`.</span><span class="sxs-lookup"><span data-stu-id="84a67-111">[in] The maximum size of the `rPermission` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="84a67-112">enuncia El número de tokens de permiso devueltos en `rPermission` .</span><span class="sxs-lookup"><span data-stu-id="84a67-112">[out] The number of Permission tokens returned in `rPermission`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="84a67-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="84a67-113">Return Value</span></span>  
  
|<span data-ttu-id="84a67-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="84a67-114">HRESULT</span></span>|<span data-ttu-id="84a67-115">Description</span><span class="sxs-lookup"><span data-stu-id="84a67-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="84a67-116">`EnumPermissionSets`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="84a67-116">`EnumPermissionSets` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="84a67-117">No hay tokens que enumerar.</span><span class="sxs-lookup"><span data-stu-id="84a67-117">There are no tokens to enumerate.</span></span> <span data-ttu-id="84a67-118">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="84a67-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="84a67-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="84a67-119">Requirements</span></span>  
 <span data-ttu-id="84a67-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84a67-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84a67-121">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="84a67-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="84a67-122">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="84a67-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="84a67-123">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84a67-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84a67-124">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="84a67-124">See also</span></span>

- [<span data-ttu-id="84a67-125">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="84a67-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="84a67-126">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="84a67-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
