---
description: 'Más información sobre: IMetaDataEmit:: Setfieldrva ((método)'
title: IMetaDataEmit::SetFieldRVA (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldRVA
helpviewer_keywords:
- IMetaDataEmit::SetFieldRVA method [.NET Framework metadata]
- SetFieldRVA method [.NET Framework metadata]
ms.assetid: 6dc37f9d-87ee-4cb3-9216-ced600184ce8
topic_type:
- apiref
ms.openlocfilehash: 5d78880b892dc948337aa1ec1a471a5d380f1e2f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657936"
---
# <a name="imetadataemitsetfieldrva-method"></a><span data-ttu-id="dc6a7-103">IMetaDataEmit::SetFieldRVA (Método)</span><span class="sxs-lookup"><span data-stu-id="dc6a7-103">IMetaDataEmit::SetFieldRVA Method</span></span>

<span data-ttu-id="dc6a7-104">Establece un valor de variable global para la dirección virtual relativa del campo al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="dc6a7-104">Sets a global variable value for the relative virtual address of the field referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc6a7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dc6a7-105">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldRVA (
    [in]  mdFieldDef  fd,
    [in]  ULONG       ulRVA
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc6a7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="dc6a7-106">Parameters</span></span>  

 `fd`  
 <span data-ttu-id="dc6a7-107">de El token para el campo de destino.</span><span class="sxs-lookup"><span data-stu-id="dc6a7-107">[in] The token for the target field.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="dc6a7-108">de Dirección de un código o área de datos.</span><span class="sxs-lookup"><span data-stu-id="dc6a7-108">[in] The address of a code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc6a7-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dc6a7-109">Requirements</span></span>  

 <span data-ttu-id="dc6a7-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc6a7-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc6a7-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="dc6a7-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dc6a7-112">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dc6a7-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dc6a7-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc6a7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc6a7-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc6a7-114">See also</span></span>

- [<span data-ttu-id="dc6a7-115">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dc6a7-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="dc6a7-116">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dc6a7-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
