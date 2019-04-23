---
title: IMetaDataImport::GetScopeProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetScopeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetScopeProps
helpviewer_keywords:
- IMetaDataImport::GetScopeProps method [.NET Framework metadata]
- GetScopeProps method [.NET Framework metadata]
ms.assetid: c8ba42d2-d9fa-43cb-bbc0-f33e1e592cb6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 17568a46c8e946989af0e401366d7eaa885886da
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59220973"
---
# <a name="imetadataimportgetscopeprops-method"></a><span data-ttu-id="ea5b2-102">IMetaDataImport::GetScopeProps (Método)</span><span class="sxs-lookup"><span data-stu-id="ea5b2-102">IMetaDataImport::GetScopeProps Method</span></span>
<span data-ttu-id="ea5b2-103">Obtiene el nombre y, si quiere, el identificador de versión del ensamblado o el módulo en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="ea5b2-103">Gets the name and optionally the version identifier of the assembly or module in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea5b2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ea5b2-104">Syntax</span></span>  
  
```  
HRESULT GetScopeProps (  
   [out] LPWSTR           szName,  
   [in]  ULONG            cchName,  
   [out] ULONG            *pchName,  
   [out, optional] GUID   *pmvid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea5b2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ea5b2-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="ea5b2-106">[out] Un búfer para el nombre de ensamblado o módulo.</span><span class="sxs-lookup"><span data-stu-id="ea5b2-106">[out] A buffer for the assembly or module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="ea5b2-107">[in] El tamaño en caracteres anchos de `szName`.</span><span class="sxs-lookup"><span data-stu-id="ea5b2-107">[in] The size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="ea5b2-108">[out] El número de caracteres anchos que se devuelven en `szName`.</span><span class="sxs-lookup"><span data-stu-id="ea5b2-108">[out] The number of wide characters returned in `szName`.</span></span>  
  
 `pmvid`  
 <span data-ttu-id="ea5b2-109">[out, optional] Un puntero a un GUID que identifica la versión del ensamblado o módulo.</span><span class="sxs-lookup"><span data-stu-id="ea5b2-109">[out, optional] A pointer to a GUID that uniquely identifies the version of the assembly or module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea5b2-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ea5b2-110">Remarks</span></span>  
 <span data-ttu-id="ea5b2-111">El [SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) método se usa para establecer estas propiedades.</span><span class="sxs-lookup"><span data-stu-id="ea5b2-111">The [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) method is used to set these properties.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea5b2-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ea5b2-112">Requirements</span></span>  
 <span data-ttu-id="ea5b2-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea5b2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea5b2-114">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="ea5b2-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ea5b2-115">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ea5b2-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ea5b2-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea5b2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea5b2-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea5b2-117">See also</span></span>

- [<span data-ttu-id="ea5b2-118">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ea5b2-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="ea5b2-119">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ea5b2-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
