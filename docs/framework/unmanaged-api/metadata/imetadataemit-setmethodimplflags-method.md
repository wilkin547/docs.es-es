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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a437ff11114ea8d577b2fc3b81cd981cebb8c8d6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751069"
---
# <a name="imetadataemitsetmethodimplflags-method"></a><span data-ttu-id="516ea-102">IMetaDataEmit::SetMethodImplFlags (Método)</span><span class="sxs-lookup"><span data-stu-id="516ea-102">IMetaDataEmit::SetMethodImplFlags Method</span></span>
<span data-ttu-id="516ea-103">Establece o actualiza la firma de metadatos de la implementación del método heredado que se hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="516ea-103">Sets or updates the metadata signature of the inherited method implementation that is referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="516ea-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="516ea-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodImplFlags (   
    [in]  mdMethodDef   md,   
    [in]  DWORD         dwImplFlags   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="516ea-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="516ea-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="516ea-106">[in] El token para el método que se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="516ea-106">[in] The token for the method to be changed.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="516ea-107">[in] Una combinación de los valores de la [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeración que especifica las características de implementación del método.</span><span class="sxs-lookup"><span data-stu-id="516ea-107">[in] A combination of the values of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the method implementation features.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="516ea-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="516ea-108">Requirements</span></span>  
 <span data-ttu-id="516ea-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="516ea-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="516ea-110">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="516ea-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="516ea-111">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="516ea-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="516ea-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="516ea-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="516ea-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="516ea-113">See also</span></span>

- [<span data-ttu-id="516ea-114">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="516ea-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="516ea-115">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="516ea-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
