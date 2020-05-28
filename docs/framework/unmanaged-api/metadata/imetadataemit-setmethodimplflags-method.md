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
ms.openlocfilehash: a02456393680169ce33369ee5914f6c5216081c6
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009228"
---
# <a name="imetadataemitsetmethodimplflags-method"></a><span data-ttu-id="ca28a-102">IMetaDataEmit::SetMethodImplFlags (Método)</span><span class="sxs-lookup"><span data-stu-id="ca28a-102">IMetaDataEmit::SetMethodImplFlags Method</span></span>
<span data-ttu-id="ca28a-103">Establece o actualiza la firma de metadatos de la implementación del método heredado a la que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="ca28a-103">Sets or updates the metadata signature of the inherited method implementation that is referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca28a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ca28a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodImplFlags (
    [in]  mdMethodDef   md,
    [in]  DWORD         dwImplFlags
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca28a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ca28a-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="ca28a-106">de Token para el método que se va a cambiar.</span><span class="sxs-lookup"><span data-stu-id="ca28a-106">[in] The token for the method to be changed.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="ca28a-107">de Una combinación de los valores de la enumeración [CorMethodImpl (](cormethodimpl-enumeration.md) que especifica las características de implementación del método.</span><span class="sxs-lookup"><span data-stu-id="ca28a-107">[in] A combination of the values of the [CorMethodImpl](cormethodimpl-enumeration.md) enumeration that specifies the method implementation features.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca28a-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ca28a-108">Requirements</span></span>  
 <span data-ttu-id="ca28a-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca28a-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca28a-110">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ca28a-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ca28a-111">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ca28a-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ca28a-112">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca28a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca28a-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ca28a-113">See also</span></span>

- [<span data-ttu-id="ca28a-114">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ca28a-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="ca28a-115">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ca28a-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
