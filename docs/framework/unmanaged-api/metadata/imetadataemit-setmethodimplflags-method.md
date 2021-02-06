---
description: 'Más información sobre: IMetaDataEmit:: Setmethodimplflags ((método)'
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
ms.openlocfilehash: ea7f3122a21c8651014e60de3629db87eeaf6260
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657843"
---
# <a name="imetadataemitsetmethodimplflags-method"></a><span data-ttu-id="4828f-103">IMetaDataEmit::SetMethodImplFlags (Método)</span><span class="sxs-lookup"><span data-stu-id="4828f-103">IMetaDataEmit::SetMethodImplFlags Method</span></span>

<span data-ttu-id="4828f-104">Establece o actualiza la firma de metadatos de la implementación del método heredado a la que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="4828f-104">Sets or updates the metadata signature of the inherited method implementation that is referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4828f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4828f-105">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodImplFlags (
    [in]  mdMethodDef   md,
    [in]  DWORD         dwImplFlags
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4828f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4828f-106">Parameters</span></span>  

 `md`  
 <span data-ttu-id="4828f-107">de Token para el método que se va a cambiar.</span><span class="sxs-lookup"><span data-stu-id="4828f-107">[in] The token for the method to be changed.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="4828f-108">de Una combinación de los valores de la enumeración [CorMethodImpl (](cormethodimpl-enumeration.md) que especifica las características de implementación del método.</span><span class="sxs-lookup"><span data-stu-id="4828f-108">[in] A combination of the values of the [CorMethodImpl](cormethodimpl-enumeration.md) enumeration that specifies the method implementation features.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4828f-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4828f-109">Requirements</span></span>  

 <span data-ttu-id="4828f-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4828f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4828f-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4828f-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4828f-112">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4828f-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4828f-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4828f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4828f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="4828f-114">See also</span></span>

- [<span data-ttu-id="4828f-115">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4828f-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="4828f-116">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4828f-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
