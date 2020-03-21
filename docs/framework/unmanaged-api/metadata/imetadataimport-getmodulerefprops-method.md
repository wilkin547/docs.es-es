---
title: IMetaDataImport::GetModuleRefProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetModuleRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetModuleRefProps
helpviewer_keywords:
- GetModuleRefProps method [.NET Framework metadata]
- IMetaDataImport::GetModuleRefProps method [.NET Framework metadata]
ms.assetid: b558e766-4c11-4628-ae47-b4e0a1800168
topic_type:
- apiref
ms.openlocfilehash: f46033b9e643ef6b4a0063c4995b8c024b8c1f7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175361"
---
# <a name="imetadataimportgetmodulerefprops-method"></a><span data-ttu-id="41b60-102">IMetaDataImport::GetModuleRefProps (Método)</span><span class="sxs-lookup"><span data-stu-id="41b60-102">IMetaDataImport::GetModuleRefProps Method</span></span>
<span data-ttu-id="41b60-103">Obtiene el nombre del módulo al que hace referencia el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="41b60-103">Gets the name of the module referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41b60-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="41b60-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleRefProps (  
   [in]  mdModuleRef         mur,  
   [out] LPWSTR              szName,
   [in]  ULONG               cchName,
   [out] ULONG               *pchName
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41b60-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="41b60-105">Parameters</span></span>  
 `mur`  
 <span data-ttu-id="41b60-106">[en] El token de metadatos ModuleRef que hace referencia al módulo para el que se obtiene información de metadatos.</span><span class="sxs-lookup"><span data-stu-id="41b60-106">[in] The ModuleRef metadata token that references the module to get metadata information for.</span></span>  
  
 `szName`  
 <span data-ttu-id="41b60-107">[fuera] Un búfer para contener el nombre del módulo.</span><span class="sxs-lookup"><span data-stu-id="41b60-107">[out] A buffer to hold the module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="41b60-108">[en] El tamaño `szName` solicitado de caracteres anchos.</span><span class="sxs-lookup"><span data-stu-id="41b60-108">[in] The requested size of `szName` in wide characters.</span></span>  
  
 `pchName`  
 <span data-ttu-id="41b60-109">[fuera] El tamaño `szName` devuelto de los caracteres anchos.</span><span class="sxs-lookup"><span data-stu-id="41b60-109">[out] The returned size of `szName` in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41b60-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="41b60-110">Requirements</span></span>  
 <span data-ttu-id="41b60-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41b60-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41b60-112">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="41b60-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="41b60-113">**Biblioteca:** Incluido como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="41b60-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="41b60-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41b60-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41b60-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="41b60-115">See also</span></span>

- [<span data-ttu-id="41b60-116">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="41b60-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="41b60-117">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="41b60-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
