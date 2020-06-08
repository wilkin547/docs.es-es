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
ms.openlocfilehash: f1784c9f3085ce188f9e540887dd02064f8448f3
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503588"
---
# <a name="imetadataimportgetmodulerefprops-method"></a><span data-ttu-id="45820-102">IMetaDataImport::GetModuleRefProps (Método)</span><span class="sxs-lookup"><span data-stu-id="45820-102">IMetaDataImport::GetModuleRefProps Method</span></span>
<span data-ttu-id="45820-103">Obtiene el nombre del módulo al que hace referencia el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="45820-103">Gets the name of the module referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45820-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="45820-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleRefProps (  
   [in]  mdModuleRef         mur,  
   [out] LPWSTR              szName,
   [in]  ULONG               cchName,
   [out] ULONG               *pchName
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45820-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="45820-105">Parameters</span></span>  
 `mur`  
 <span data-ttu-id="45820-106">de Token de metadatos de ModuleRef que hace referencia al módulo para el que se va a obtener información de metadatos.</span><span class="sxs-lookup"><span data-stu-id="45820-106">[in] The ModuleRef metadata token that references the module to get metadata information for.</span></span>  
  
 `szName`  
 <span data-ttu-id="45820-107">enuncia Búfer que contiene el nombre del módulo.</span><span class="sxs-lookup"><span data-stu-id="45820-107">[out] A buffer to hold the module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="45820-108">de Tamaño solicitado de `szName` caracteres anchos.</span><span class="sxs-lookup"><span data-stu-id="45820-108">[in] The requested size of `szName` in wide characters.</span></span>  
  
 `pchName`  
 <span data-ttu-id="45820-109">enuncia Tamaño devuelto de `szName` en caracteres anchos.</span><span class="sxs-lookup"><span data-stu-id="45820-109">[out] The returned size of `szName` in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45820-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="45820-110">Requirements</span></span>  
 <span data-ttu-id="45820-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45820-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45820-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="45820-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="45820-113">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="45820-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="45820-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45820-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45820-115">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="45820-115">See also</span></span>

- [<span data-ttu-id="45820-116">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="45820-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="45820-117">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="45820-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
