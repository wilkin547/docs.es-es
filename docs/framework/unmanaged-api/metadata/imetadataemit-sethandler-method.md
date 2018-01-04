---
title: "IMetaDataEmit::SetHandler (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetHandler
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetHandler
helpviewer_keywords:
- IMetaDataEmit::SetHandler method [.NET Framework metadata]
- SetHandler method [.NET Framework metadata]
ms.assetid: c6c1aaaf-e2cd-407c-b73e-fbe6ffd83bb3
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ccb35c12e1d9c2fade9d8760d0a2e39807c92de9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitsethandler-method"></a><span data-ttu-id="7b8d3-102">IMetaDataEmit::SetHandler (Método)</span><span class="sxs-lookup"><span data-stu-id="7b8d3-102">IMetaDataEmit::SetHandler Method</span></span>
<span data-ttu-id="7b8d3-103">Establece el método al que hace referencia especificado `IUnknown` puntero como una devolución de llamada de notificación para reasigna cada símbolo (token).</span><span class="sxs-lookup"><span data-stu-id="7b8d3-103">Sets the method referenced by the specified `IUnknown` pointer as a notification callback for token remaps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b8d3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7b8d3-104">Syntax</span></span>  
  
```  
HRESULT SetHandler (   
    [in]  IUnknown    *pUnk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7b8d3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7b8d3-105">Parameters</span></span>  
 `pUnk`  
 <span data-ttu-id="7b8d3-106">[in] El controlador para registrar.</span><span class="sxs-lookup"><span data-stu-id="7b8d3-106">[in] The handler to register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b8d3-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7b8d3-107">Remarks</span></span>  
 <span data-ttu-id="7b8d3-108">El motor de metadatos envía la notificación mediante el método proporcionado por `SetHandler`, a los compiladores que no generan registros de forma optimizada y que le gustaría optimizar registros guardados.</span><span class="sxs-lookup"><span data-stu-id="7b8d3-108">The metadata engine sends notification by using the method that is provided by `SetHandler`, to compilers that do not generate records in an optimized way and that would like to optimize saved records.</span></span>  
  
 <span data-ttu-id="7b8d3-109">Si el método de devolución de llamada no se proporciona a través de `SetHandler`, no se realizará ninguna optimización en Guardar excepto donde importación varios ámbitos se han combinado con `IMapToken` en cada ámbito de replicación de mezcla.</span><span class="sxs-lookup"><span data-stu-id="7b8d3-109">If the callback method is not provided through `SetHandler`, no optimization will be performed on save except where several import scopes have been merged using `IMapToken` on merge for each scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b8d3-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7b8d3-110">Requirements</span></span>  
 <span data-ttu-id="7b8d3-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b8d3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b8d3-112">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7b8d3-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7b8d3-113">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7b8d3-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7b8d3-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b8d3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b8d3-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b8d3-115">See Also</span></span>  
 [<span data-ttu-id="7b8d3-116">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7b8d3-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="7b8d3-117">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7b8d3-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
