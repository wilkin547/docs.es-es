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
ms.openlocfilehash: 375c4b2cece0bdfd763ae383c5412c9e25614baf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177543"
---
# <a name="imetadataemitsethandler-method"></a><span data-ttu-id="98882-102">IMetaDataEmit::SetHandler (Método)</span><span class="sxs-lookup"><span data-stu-id="98882-102">IMetaDataEmit::SetHandler Method</span></span>
<span data-ttu-id="98882-103">Establece el método al `IUnknown` que hace referencia el puntero especificado como una devolución de llamada de notificación para las reasignaciones de tokens.</span><span class="sxs-lookup"><span data-stu-id="98882-103">Sets the method referenced by the specified `IUnknown` pointer as a notification callback for token remaps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98882-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="98882-104">Syntax</span></span>  
  
```cpp  
HRESULT SetHandler (
    [in]  IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98882-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="98882-105">Parameters</span></span>  
 `pUnk`  
 <span data-ttu-id="98882-106">[en] El controlador que se debe registrar.</span><span class="sxs-lookup"><span data-stu-id="98882-106">[in] The handler to register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98882-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="98882-107">Remarks</span></span>  
 <span data-ttu-id="98882-108">El motor de metadatos envía una notificación mediante el método proporcionado por `SetHandler`, a los compiladores que no generan registros de forma optimizada y que desean optimizar los registros guardados.</span><span class="sxs-lookup"><span data-stu-id="98882-108">The metadata engine sends notification by using the method that is provided by `SetHandler`, to compilers that do not generate records in an optimized way and that would like to optimize saved records.</span></span>  
  
 <span data-ttu-id="98882-109">Si el método de `SetHandler`devolución de llamada no se proporciona a través de `IMapToken` , no se realizará ninguna optimización al guardar, excepto cuando se han combinado varios ámbitos de importación mediante la combinación para cada ámbito.</span><span class="sxs-lookup"><span data-stu-id="98882-109">If the callback method is not provided through `SetHandler`, no optimization will be performed on save except where several import scopes have been merged using `IMapToken` on merge for each scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98882-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="98882-110">Requirements</span></span>  
 <span data-ttu-id="98882-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98882-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98882-112">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="98882-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="98882-113">**Biblioteca:** Se utiliza como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="98882-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="98882-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98882-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98882-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="98882-115">See also</span></span>

- [<span data-ttu-id="98882-116">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="98882-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="98882-117">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="98882-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
