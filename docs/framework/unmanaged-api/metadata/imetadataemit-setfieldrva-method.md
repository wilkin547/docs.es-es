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
ms.openlocfilehash: 501199bedec3b7a65d95c80cdef178831a65fd01
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428418"
---
# <a name="imetadataemitsetfieldrva-method"></a><span data-ttu-id="4865a-102">IMetaDataEmit::SetFieldRVA (Método)</span><span class="sxs-lookup"><span data-stu-id="4865a-102">IMetaDataEmit::SetFieldRVA Method</span></span>
<span data-ttu-id="4865a-103">Establece un valor de variable global para la dirección virtual relativa del campo al que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="4865a-103">Sets a global variable value for the relative virtual address of the field referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4865a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4865a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldRVA (   
    [in]  mdFieldDef  fd,   
    [in]  ULONG       ulRVA   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4865a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4865a-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="4865a-106">de El token para el campo de destino.</span><span class="sxs-lookup"><span data-stu-id="4865a-106">[in] The token for the target field.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="4865a-107">de Dirección de un código o área de datos.</span><span class="sxs-lookup"><span data-stu-id="4865a-107">[in] The address of a code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4865a-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4865a-108">Requirements</span></span>  
 <span data-ttu-id="4865a-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4865a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4865a-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4865a-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4865a-111">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4865a-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4865a-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4865a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4865a-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="4865a-113">See also</span></span>

- [<span data-ttu-id="4865a-114">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4865a-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="4865a-115">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4865a-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
