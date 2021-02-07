---
description: 'Más información sobre: IMetaDataImport:: Getmodulefromscope ((método)'
title: IMetaDataImport::GetModuleFromScope (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetModuleFromScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetModuleFromScope
helpviewer_keywords:
- GetModuleFromScope method [.NET Framework metadata]
- IMetaDataImport::GetModuleFromScope method [.NET Framework metadata]
ms.assetid: add68d3f-45fd-4bef-af94-eb5273f26b11
topic_type:
- apiref
ms.openlocfilehash: 8c1e952a45b3827717102428fbd18ceac3951baf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753372"
---
# <a name="imetadataimportgetmodulefromscope-method"></a><span data-ttu-id="2a9c0-103">IMetaDataImport::GetModuleFromScope (Método)</span><span class="sxs-lookup"><span data-stu-id="2a9c0-103">IMetaDataImport::GetModuleFromScope Method</span></span>

<span data-ttu-id="2a9c0-104">Obtiene un símbolo (token) de metadatos para el módulo al que se hace referencia en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="2a9c0-104">Gets a metadata token for the module referenced in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a9c0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2a9c0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleFromScope (  
   [out] mdModule    *pmd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a9c0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2a9c0-106">Parameters</span></span>  

 `pmd`  
 <span data-ttu-id="2a9c0-107">enuncia Puntero al token que representa el módulo al que se hace referencia en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="2a9c0-107">[out] A pointer to the token representing the module referenced in the current metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a9c0-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2a9c0-108">Requirements</span></span>  

 <span data-ttu-id="2a9c0-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a9c0-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a9c0-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2a9c0-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2a9c0-111">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2a9c0-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2a9c0-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a9c0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a9c0-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a9c0-113">See also</span></span>

- [<span data-ttu-id="2a9c0-114">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2a9c0-114">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="2a9c0-115">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2a9c0-115">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
