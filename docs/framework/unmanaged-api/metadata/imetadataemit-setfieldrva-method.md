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
ms.openlocfilehash: d429995e41006798aee5f796150bedbd6ae87f6f
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003879"
---
# <a name="imetadataemitsetfieldrva-method"></a><span data-ttu-id="1b8bb-102">IMetaDataEmit::SetFieldRVA (Método)</span><span class="sxs-lookup"><span data-stu-id="1b8bb-102">IMetaDataEmit::SetFieldRVA Method</span></span>
<span data-ttu-id="1b8bb-103">Establece un valor de variable global para la dirección virtual relativa del campo al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="1b8bb-103">Sets a global variable value for the relative virtual address of the field referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b8bb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1b8bb-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldRVA (
    [in]  mdFieldDef  fd,
    [in]  ULONG       ulRVA
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b8bb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1b8bb-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="1b8bb-106">de El token para el campo de destino.</span><span class="sxs-lookup"><span data-stu-id="1b8bb-106">[in] The token for the target field.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="1b8bb-107">de Dirección de un código o área de datos.</span><span class="sxs-lookup"><span data-stu-id="1b8bb-107">[in] The address of a code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b8bb-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1b8bb-108">Requirements</span></span>  
 <span data-ttu-id="1b8bb-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b8bb-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b8bb-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1b8bb-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1b8bb-111">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1b8bb-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1b8bb-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b8bb-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b8bb-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1b8bb-113">See also</span></span>

- [<span data-ttu-id="1b8bb-114">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1b8bb-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="1b8bb-115">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1b8bb-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
