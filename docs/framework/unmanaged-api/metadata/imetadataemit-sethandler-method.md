---
title: IMetaDataEmit::SetHandler (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetHandler
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetHandler
helpviewer_keywords:
- IMetaDataEmit::SetHandler method [.NET Framework metadata]
- SetHandler method [.NET Framework metadata]
ms.assetid: c6c1aaaf-e2cd-407c-b73e-fbe6ffd83bb3
topic_type:
- apiref
ms.openlocfilehash: 4fa227d18b8cb10936d93fda9bcaf413ce63ca3b
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003962"
---
# <a name="imetadataemitsethandler-method"></a><span data-ttu-id="9691a-102">IMetaDataEmit::SetHandler (Método)</span><span class="sxs-lookup"><span data-stu-id="9691a-102">IMetaDataEmit::SetHandler Method</span></span>
<span data-ttu-id="9691a-103">Establece el método al que hace referencia el `IUnknown` puntero especificado como una devolución de llamada de notificación para las reasignaciones de token.</span><span class="sxs-lookup"><span data-stu-id="9691a-103">Sets the method referenced by the specified `IUnknown` pointer as a notification callback for token remaps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9691a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9691a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetHandler (
    [in]  IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9691a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9691a-105">Parameters</span></span>  
 `pUnk`  
 <span data-ttu-id="9691a-106">de Controlador que se va a registrar.</span><span class="sxs-lookup"><span data-stu-id="9691a-106">[in] The handler to register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9691a-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9691a-107">Remarks</span></span>  
 <span data-ttu-id="9691a-108">El motor de metadatos envía notificaciones mediante el método proporcionado por `SetHandler` , a los compiladores que no generan registros de una manera optimizada y que desean optimizar los registros guardados.</span><span class="sxs-lookup"><span data-stu-id="9691a-108">The metadata engine sends notification by using the method that is provided by `SetHandler`, to compilers that do not generate records in an optimized way and that would like to optimize saved records.</span></span>  
  
 <span data-ttu-id="9691a-109">Si no se proporciona el método de devolución de llamada a través de `SetHandler` , no se realizará ninguna optimización al guardar, excepto en el caso de que se hayan combinado varios ámbitos de importación mediante `IMapToken` Merge para cada ámbito.</span><span class="sxs-lookup"><span data-stu-id="9691a-109">If the callback method is not provided through `SetHandler`, no optimization will be performed on save except where several import scopes have been merged using `IMapToken` on merge for each scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9691a-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9691a-110">Requirements</span></span>  
 <span data-ttu-id="9691a-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9691a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9691a-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9691a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9691a-113">**Biblioteca:** Se utiliza como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9691a-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9691a-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9691a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9691a-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9691a-115">See also</span></span>

- [<span data-ttu-id="9691a-116">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9691a-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="9691a-117">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9691a-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
