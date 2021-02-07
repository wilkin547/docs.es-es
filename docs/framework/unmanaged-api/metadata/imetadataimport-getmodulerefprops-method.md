---
description: 'Más información sobre: IMetaDataImport:: GetModuleRefProps ((método)'
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
ms.openlocfilehash: 3e6b212ddad5eefb06942c3fd4b89411b277f761
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753359"
---
# <a name="imetadataimportgetmodulerefprops-method"></a><span data-ttu-id="d4b79-103">IMetaDataImport::GetModuleRefProps (Método)</span><span class="sxs-lookup"><span data-stu-id="d4b79-103">IMetaDataImport::GetModuleRefProps Method</span></span>

<span data-ttu-id="d4b79-104">Obtiene el nombre del módulo al que hace referencia el token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="d4b79-104">Gets the name of the module referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4b79-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d4b79-105">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleRefProps (  
   [in]  mdModuleRef         mur,  
   [out] LPWSTR              szName,
   [in]  ULONG               cchName,
   [out] ULONG               *pchName
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4b79-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d4b79-106">Parameters</span></span>  

 `mur`  
 <span data-ttu-id="d4b79-107">de Token de metadatos de ModuleRef que hace referencia al módulo para el que se va a obtener información de metadatos.</span><span class="sxs-lookup"><span data-stu-id="d4b79-107">[in] The ModuleRef metadata token that references the module to get metadata information for.</span></span>  
  
 `szName`  
 <span data-ttu-id="d4b79-108">enuncia Búfer que contiene el nombre del módulo.</span><span class="sxs-lookup"><span data-stu-id="d4b79-108">[out] A buffer to hold the module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="d4b79-109">de Tamaño solicitado de `szName` caracteres anchos.</span><span class="sxs-lookup"><span data-stu-id="d4b79-109">[in] The requested size of `szName` in wide characters.</span></span>  
  
 `pchName`  
 <span data-ttu-id="d4b79-110">enuncia Tamaño devuelto de `szName` en caracteres anchos.</span><span class="sxs-lookup"><span data-stu-id="d4b79-110">[out] The returned size of `szName` in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4b79-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d4b79-111">Requirements</span></span>  

 <span data-ttu-id="d4b79-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4b79-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4b79-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d4b79-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d4b79-114">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d4b79-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d4b79-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4b79-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4b79-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4b79-116">See also</span></span>

- [<span data-ttu-id="d4b79-117">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d4b79-117">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="d4b79-118">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d4b79-118">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
