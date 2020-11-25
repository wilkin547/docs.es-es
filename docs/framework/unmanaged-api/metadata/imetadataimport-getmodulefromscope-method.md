---
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
ms.openlocfilehash: 2eddd7a80c2b9c1b71f3e7fc5b1e4686ba11bccd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733170"
---
# <a name="imetadataimportgetmodulefromscope-method"></a><span data-ttu-id="a9caf-102">IMetaDataImport::GetModuleFromScope (Método)</span><span class="sxs-lookup"><span data-stu-id="a9caf-102">IMetaDataImport::GetModuleFromScope Method</span></span>

<span data-ttu-id="a9caf-103">Obtiene un símbolo (token) de metadatos para el módulo al que se hace referencia en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="a9caf-103">Gets a metadata token for the module referenced in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9caf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9caf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleFromScope (  
   [out] mdModule    *pmd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9caf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a9caf-105">Parameters</span></span>  

 `pmd`  
 <span data-ttu-id="a9caf-106">enuncia Puntero al token que representa el módulo al que se hace referencia en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="a9caf-106">[out] A pointer to the token representing the module referenced in the current metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9caf-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9caf-107">Requirements</span></span>  

 <span data-ttu-id="a9caf-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9caf-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9caf-109">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a9caf-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a9caf-110">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a9caf-110">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a9caf-111">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9caf-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9caf-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a9caf-112">See also</span></span>

- [<span data-ttu-id="a9caf-113">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a9caf-113">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="a9caf-114">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a9caf-114">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
