---
description: 'Más información sobre: IMetaDataEmit:: SetMethodProps ((método)'
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
ms.openlocfilehash: edecdc14abb386f8fa4cd70535f2b8c012bdc59f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772112"
---
# <a name="imetadataemitsetmethodprops-method"></a><span data-ttu-id="93f74-103">IMetaDataEmit::SetMethodProps (Método)</span><span class="sxs-lookup"><span data-stu-id="93f74-103">IMetaDataEmit::SetMethodProps Method</span></span>

<span data-ttu-id="93f74-104">Establece o actualiza la característica, almacenada en la dirección virtual relativa especificada, de un método definido por una llamada anterior a [IMetaDataEmit::D efinemethod](imetadataemit-definemethod-method.md).</span><span class="sxs-lookup"><span data-stu-id="93f74-104">Sets or updates the feature, stored at the specified relative virtual address, of a method defined by a prior call to [IMetaDataEmit::DefineMethod](imetadataemit-definemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93f74-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="93f74-105">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodProps (
    [in]  mdMethodDef md,
    [in]  DWORD       dwMethodFlags,  
    [in]  ULONG       ulCodeRVA,
    [in]  DWORD       dwImplFlags
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="93f74-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="93f74-106">Parameters</span></span>  

 `md`  
 <span data-ttu-id="93f74-107">de Token para el método que se va a cambiar.</span><span class="sxs-lookup"><span data-stu-id="93f74-107">[in] The token for the method to be changed.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="93f74-108">de Atributos de miembro.</span><span class="sxs-lookup"><span data-stu-id="93f74-108">[in] The member attributes.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="93f74-109">de Dirección del código.</span><span class="sxs-lookup"><span data-stu-id="93f74-109">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="93f74-110">de Marcas de implementación para el método.</span><span class="sxs-lookup"><span data-stu-id="93f74-110">[in] The implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93f74-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="93f74-111">Requirements</span></span>  

 <span data-ttu-id="93f74-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93f74-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93f74-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="93f74-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="93f74-114">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="93f74-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="93f74-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93f74-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93f74-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="93f74-116">See also</span></span>

- [<span data-ttu-id="93f74-117">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="93f74-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="93f74-118">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="93f74-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
