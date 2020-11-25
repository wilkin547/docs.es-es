---
title: IMetaDataEmit::SetModuleProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetModuleProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetModuleProps
helpviewer_keywords:
- SetModuleProps method [.NET Framework metadata]
- IMetaDataEmit::SetModuleProps method [.NET Framework metadata]
ms.assetid: b74d7629-5f46-458f-8d67-2456a1e7030c
topic_type:
- apiref
ms.openlocfilehash: 1757662d2004dce3156182c35b37237ff91bae7f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730349"
---
# <a name="imetadataemitsetmoduleprops-method"></a><span data-ttu-id="8d9cd-102">IMetaDataEmit::SetModuleProps (Método)</span><span class="sxs-lookup"><span data-stu-id="8d9cd-102">IMetaDataEmit::SetModuleProps Method</span></span>

<span data-ttu-id="8d9cd-103">Actualiza las referencias a un módulo definido por una llamada anterior a [IMetaDataEmit::D efinemoduleref](imetadataemit-definemoduleref-method.md).</span><span class="sxs-lookup"><span data-stu-id="8d9cd-103">Updates references to a module defined by a prior call to [IMetaDataEmit::DefineModuleRef](imetadataemit-definemoduleref-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d9cd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8d9cd-104">Syntax</span></span>  
  
```cpp  
HRESULT SetModuleProps (
    [in]  LPCWSTR     szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d9cd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8d9cd-105">Parameters</span></span>  

 `szName`  
 <span data-ttu-id="8d9cd-106">de Nombre del módulo en Unicode.</span><span class="sxs-lookup"><span data-stu-id="8d9cd-106">[in] The module name in Unicode.</span></span> <span data-ttu-id="8d9cd-107">Este es el nombre de archivo únicamente y no el nombre completo de la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="8d9cd-107">This is the file name only and not the full path name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d9cd-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8d9cd-108">Requirements</span></span>  

 <span data-ttu-id="8d9cd-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d9cd-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d9cd-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8d9cd-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8d9cd-111">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8d9cd-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8d9cd-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d9cd-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d9cd-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8d9cd-113">See also</span></span>

- [<span data-ttu-id="8d9cd-114">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8d9cd-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="8d9cd-115">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8d9cd-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
