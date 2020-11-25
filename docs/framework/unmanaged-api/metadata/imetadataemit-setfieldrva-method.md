---
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
ms.openlocfilehash: 8468b0e7faa520fe2d27e17674af5503871d3b62
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730388"
---
# <a name="imetadataemitsetfieldrva-method"></a><span data-ttu-id="c1c6b-102">IMetaDataEmit::SetFieldRVA (Método)</span><span class="sxs-lookup"><span data-stu-id="c1c6b-102">IMetaDataEmit::SetFieldRVA Method</span></span>

<span data-ttu-id="c1c6b-103">Establece un valor de variable global para la dirección virtual relativa del campo al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="c1c6b-103">Sets a global variable value for the relative virtual address of the field referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1c6b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c1c6b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldRVA (
    [in]  mdFieldDef  fd,
    [in]  ULONG       ulRVA
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1c6b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c1c6b-105">Parameters</span></span>  

 `fd`  
 <span data-ttu-id="c1c6b-106">de El token para el campo de destino.</span><span class="sxs-lookup"><span data-stu-id="c1c6b-106">[in] The token for the target field.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="c1c6b-107">de Dirección de un código o área de datos.</span><span class="sxs-lookup"><span data-stu-id="c1c6b-107">[in] The address of a code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1c6b-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c1c6b-108">Requirements</span></span>  

 <span data-ttu-id="c1c6b-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1c6b-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1c6b-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c1c6b-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c1c6b-111">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c1c6b-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c1c6b-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1c6b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1c6b-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c1c6b-113">See also</span></span>

- [<span data-ttu-id="c1c6b-114">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c1c6b-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="c1c6b-115">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c1c6b-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
