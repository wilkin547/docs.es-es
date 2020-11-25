---
title: IMetaDataEmit::SetMethodProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodProps
helpviewer_keywords:
- SetMethodProps method [.NET Framework metadata]
- IMetaDataEmit::SetMethodProps method [.NET Framework metadata]
ms.assetid: e0c6ac12-22ea-43f5-b799-8cda0faf3336
topic_type:
- apiref
ms.openlocfilehash: c461582cc22f7185ee2707db91be83bc1aa0ba4c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706851"
---
# <a name="imetadataemitsetmethodprops-method"></a><span data-ttu-id="645c6-102">IMetaDataEmit::SetMethodProps (Método)</span><span class="sxs-lookup"><span data-stu-id="645c6-102">IMetaDataEmit::SetMethodProps Method</span></span>

<span data-ttu-id="645c6-103">Establece o actualiza la característica, almacenada en la dirección virtual relativa especificada, de un método definido por una llamada anterior a [IMetaDataEmit::D efinemethod](imetadataemit-definemethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="645c6-103">Sets or updates the feature, stored at the specified relative virtual address, of a method defined by a prior call to [IMetaDataEmit::DefineMethod](imetadataemit-definemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="645c6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="645c6-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodProps (
    [in]  mdMethodDef md,
    [in]  DWORD       dwMethodFlags,  
    [in]  ULONG       ulCodeRVA,
    [in]  DWORD       dwImplFlags
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="645c6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="645c6-105">Parameters</span></span>  

 `md`  
 <span data-ttu-id="645c6-106">de Token para el método que se va a cambiar.</span><span class="sxs-lookup"><span data-stu-id="645c6-106">[in] The token for the method to be changed.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="645c6-107">de Atributos de miembro.</span><span class="sxs-lookup"><span data-stu-id="645c6-107">[in] The member attributes.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="645c6-108">de Dirección del código.</span><span class="sxs-lookup"><span data-stu-id="645c6-108">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="645c6-109">de Marcas de implementación para el método.</span><span class="sxs-lookup"><span data-stu-id="645c6-109">[in] The implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="645c6-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="645c6-110">Requirements</span></span>  

 <span data-ttu-id="645c6-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="645c6-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="645c6-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="645c6-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="645c6-113">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="645c6-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="645c6-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="645c6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="645c6-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="645c6-115">See also</span></span>

- [<span data-ttu-id="645c6-116">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="645c6-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="645c6-117">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="645c6-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
