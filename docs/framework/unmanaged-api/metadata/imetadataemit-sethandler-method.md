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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ada84df2a08b992aa178c2fb63c713b05a8937a2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57503221"
---
# <a name="imetadataemitsethandler-method"></a><span data-ttu-id="f2e53-102">IMetaDataEmit::SetHandler (Método)</span><span class="sxs-lookup"><span data-stu-id="f2e53-102">IMetaDataEmit::SetHandler Method</span></span>
<span data-ttu-id="f2e53-103">Establece el método al que hace referencia especificado `IUnknown` puntero como una devolución de llamada de notificación para las reasignaciones de token.</span><span class="sxs-lookup"><span data-stu-id="f2e53-103">Sets the method referenced by the specified `IUnknown` pointer as a notification callback for token remaps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2e53-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f2e53-104">Syntax</span></span>  
  
```  
HRESULT SetHandler (   
    [in]  IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2e53-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f2e53-105">Parameters</span></span>  
 `pUnk`  
 <span data-ttu-id="f2e53-106">[in] Para registrar el controlador.</span><span class="sxs-lookup"><span data-stu-id="f2e53-106">[in] The handler to register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2e53-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f2e53-107">Remarks</span></span>  
 <span data-ttu-id="f2e53-108">El motor de metadatos envía la notificación mediante el método proporcionado por `SetHandler`, a los compiladores que no generan registros de forma optimizada y que le gustaría optimizar registros guardados.</span><span class="sxs-lookup"><span data-stu-id="f2e53-108">The metadata engine sends notification by using the method that is provided by `SetHandler`, to compilers that do not generate records in an optimized way and that would like to optimize saved records.</span></span>  
  
 <span data-ttu-id="f2e53-109">Si el método de devolución de llamada no se proporciona a través de `SetHandler`, no se realizará ninguna optimización en Guardar, excepto donde importación varios ámbitos se han combinado mediante `IMapToken` en cada ámbito de replicación de mezcla.</span><span class="sxs-lookup"><span data-stu-id="f2e53-109">If the callback method is not provided through `SetHandler`, no optimization will be performed on save except where several import scopes have been merged using `IMapToken` on merge for each scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2e53-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f2e53-110">Requirements</span></span>  
 <span data-ttu-id="f2e53-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2e53-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2e53-112">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="f2e53-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f2e53-113">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f2e53-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f2e53-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2e53-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2e53-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2e53-115">See also</span></span>
- [<span data-ttu-id="f2e53-116">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f2e53-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="f2e53-117">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f2e53-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
