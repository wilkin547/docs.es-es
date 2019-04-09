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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4ebde1d506a120a99e1c637c660b45d698994f5a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59181680"
---
# <a name="imetadataemitsetfieldrva-method"></a><span data-ttu-id="aa9c8-102">IMetaDataEmit::SetFieldRVA (Método)</span><span class="sxs-lookup"><span data-stu-id="aa9c8-102">IMetaDataEmit::SetFieldRVA Method</span></span>
<span data-ttu-id="aa9c8-103">Establece un valor de la variable global para la dirección virtual relativa del campo al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="aa9c8-103">Sets a global variable value for the relative virtual address of the field referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa9c8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aa9c8-104">Syntax</span></span>  
  
```  
HRESULT SetFieldRVA (   
    [in]  mdFieldDef  fd,   
    [in]  ULONG       ulRVA   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa9c8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aa9c8-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="aa9c8-106">[in] El token para el campo de destino.</span><span class="sxs-lookup"><span data-stu-id="aa9c8-106">[in] The token for the target field.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="aa9c8-107">[in] La dirección de un área de código o datos.</span><span class="sxs-lookup"><span data-stu-id="aa9c8-107">[in] The address of a code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa9c8-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aa9c8-108">Requirements</span></span>  
 <span data-ttu-id="aa9c8-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa9c8-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa9c8-110">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="aa9c8-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="aa9c8-111">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="aa9c8-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="aa9c8-112">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="aa9c8-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="aa9c8-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa9c8-113">See also</span></span>

- [<span data-ttu-id="aa9c8-114">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa9c8-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="aa9c8-115">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa9c8-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
