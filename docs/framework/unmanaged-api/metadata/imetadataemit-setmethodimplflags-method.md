---
title: IMetaDataEmit::SetMethodImplFlags (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetMethodImplFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodImplFlags
helpviewer_keywords:
- IMetaDataEmit::SetMethodImplFlags method [.NET Framework metadata]
- SetMethodImpFlags method [.NET Framework metadata]
ms.assetid: 4bc82d9b-9544-4be3-ba51-a2d4d806158a
topic_type:
- apiref
ms.openlocfilehash: 7ed7770f26ea4620d79f3be3f67e72f73c75057d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175634"
---
# <a name="imetadataemitsetmethodimplflags-method"></a><span data-ttu-id="d2a24-102">IMetaDataEmit::SetMethodImplFlags (Método)</span><span class="sxs-lookup"><span data-stu-id="d2a24-102">IMetaDataEmit::SetMethodImplFlags Method</span></span>
<span data-ttu-id="d2a24-103">Establece o actualiza la firma de metadatos de la implementación del método heredado a la que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="d2a24-103">Sets or updates the metadata signature of the inherited method implementation that is referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2a24-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d2a24-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodImplFlags (
    [in]  mdMethodDef   md,
    [in]  DWORD         dwImplFlags
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2a24-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d2a24-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="d2a24-106">[en] El token para el método que se va a cambiar.</span><span class="sxs-lookup"><span data-stu-id="d2a24-106">[in] The token for the method to be changed.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="d2a24-107">[en] Combinación de los valores de la enumeración [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) que especifica las características de implementación del método.</span><span class="sxs-lookup"><span data-stu-id="d2a24-107">[in] A combination of the values of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the method implementation features.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2a24-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d2a24-108">Requirements</span></span>  
 <span data-ttu-id="d2a24-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2a24-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2a24-110">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d2a24-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d2a24-111">**Biblioteca:** Se utiliza como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d2a24-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d2a24-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2a24-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2a24-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d2a24-113">See also</span></span>

- [<span data-ttu-id="d2a24-114">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d2a24-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="d2a24-115">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d2a24-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
