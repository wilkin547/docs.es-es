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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 501c554f6e2e4ddd8abd21fe81b81d1898ea070b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54583630"
---
# <a name="imetadataimportgetmodulerefprops-method"></a><span data-ttu-id="746d5-102">IMetaDataImport::GetModuleRefProps (Método)</span><span class="sxs-lookup"><span data-stu-id="746d5-102">IMetaDataImport::GetModuleRefProps Method</span></span>
<span data-ttu-id="746d5-103">Obtiene el nombre del módulo al que hace referencia el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="746d5-103">Gets the name of the module referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="746d5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="746d5-104">Syntax</span></span>  
  
```  
HRESULT GetModuleRefProps (  
   [in]  mdModuleRef         mur,  
   [out] LPWSTR              szName,   
   [in]  ULONG               cchName,   
   [out] ULONG               *pchName   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="746d5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="746d5-105">Parameters</span></span>  
 `mur`  
 <span data-ttu-id="746d5-106">[in] El token de metadatos de ModuleRef que hace referencia al módulo para obtener información de metadatos.</span><span class="sxs-lookup"><span data-stu-id="746d5-106">[in] The ModuleRef metadata token that references the module to get metadata information for.</span></span>  
  
 `szName`  
 <span data-ttu-id="746d5-107">[out] Un búfer para almacenar el nombre del módulo.</span><span class="sxs-lookup"><span data-stu-id="746d5-107">[out] A buffer to hold the module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="746d5-108">[in] El tamaño solicitado del `szName` en caracteres anchos.</span><span class="sxs-lookup"><span data-stu-id="746d5-108">[in] The requested size of `szName` in wide characters.</span></span>  
  
 `pchName`  
 <span data-ttu-id="746d5-109">[out] El tamaño devuelto de `szName` en caracteres anchos.</span><span class="sxs-lookup"><span data-stu-id="746d5-109">[out] The returned size of `szName` in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="746d5-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="746d5-110">Requirements</span></span>  
 <span data-ttu-id="746d5-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="746d5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="746d5-112">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="746d5-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="746d5-113">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="746d5-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="746d5-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="746d5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="746d5-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="746d5-115">See also</span></span>
- [<span data-ttu-id="746d5-116">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="746d5-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="746d5-117">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="746d5-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
