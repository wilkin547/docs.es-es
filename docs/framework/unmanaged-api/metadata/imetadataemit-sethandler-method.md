---
description: 'Más información acerca de: IMetaDataEmit:: SetHandler (método)'
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
ms.openlocfilehash: 07ebf8eef816d373e92a82fc84adacfe5a8599fb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657884"
---
# <a name="imetadataemitsethandler-method"></a><span data-ttu-id="b8214-103">IMetaDataEmit::SetHandler (Método)</span><span class="sxs-lookup"><span data-stu-id="b8214-103">IMetaDataEmit::SetHandler Method</span></span>

<span data-ttu-id="b8214-104">Establece el método al que hace referencia el `IUnknown` puntero especificado como una devolución de llamada de notificación para las reasignaciones de token.</span><span class="sxs-lookup"><span data-stu-id="b8214-104">Sets the method referenced by the specified `IUnknown` pointer as a notification callback for token remaps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8214-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b8214-105">Syntax</span></span>  
  
```cpp  
HRESULT SetHandler (
    [in]  IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8214-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b8214-106">Parameters</span></span>  

 `pUnk`  
 <span data-ttu-id="b8214-107">de Controlador que se va a registrar.</span><span class="sxs-lookup"><span data-stu-id="b8214-107">[in] The handler to register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8214-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b8214-108">Remarks</span></span>  

 <span data-ttu-id="b8214-109">El motor de metadatos envía notificaciones mediante el método proporcionado por `SetHandler` , a los compiladores que no generan registros de una manera optimizada y que desean optimizar los registros guardados.</span><span class="sxs-lookup"><span data-stu-id="b8214-109">The metadata engine sends notification by using the method that is provided by `SetHandler`, to compilers that do not generate records in an optimized way and that would like to optimize saved records.</span></span>  
  
 <span data-ttu-id="b8214-110">Si no se proporciona el método de devolución de llamada a través de `SetHandler` , no se realizará ninguna optimización al guardar, excepto en el caso de que se hayan combinado varios ámbitos de importación mediante `IMapToken` Merge para cada ámbito.</span><span class="sxs-lookup"><span data-stu-id="b8214-110">If the callback method is not provided through `SetHandler`, no optimization will be performed on save except where several import scopes have been merged using `IMapToken` on merge for each scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8214-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b8214-111">Requirements</span></span>  

 <span data-ttu-id="b8214-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8214-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8214-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b8214-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b8214-114">**Biblioteca:** Se usa como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b8214-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b8214-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8214-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8214-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8214-116">See also</span></span>

- [<span data-ttu-id="b8214-117">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b8214-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="b8214-118">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b8214-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
