---
title: ComCallUnmarshal (Coclase)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ComCallUnmarshal Coclass
api_location: mscoree.dll
api_type: COM
f1_keywords: ComCallUnmarshal
helpviewer_keywords: ComCallUnmarshal coclass [.NET Framework hosting]
ms.assetid: 2adb5827-2268-4914-a1c6-f62b61880a45
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2760fc84466c85e022421bcc17dcee6444ec859a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="f70ba-102">ComCallUnmarshal (Coclase)</span><span class="sxs-lookup"><span data-stu-id="f70ba-102">ComCallUnmarshal Coclass</span></span>
<span data-ttu-id="f70ba-103">Proporciona interfaces para administrar la serialización de punteros de interfaz.</span><span class="sxs-lookup"><span data-stu-id="f70ba-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f70ba-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f70ba-104">Syntax</span></span>  
  
```  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="f70ba-105">Interfaces</span><span class="sxs-lookup"><span data-stu-id="f70ba-105">Interfaces</span></span>  
  
|<span data-ttu-id="f70ba-106">Interfaz</span><span class="sxs-lookup"><span data-stu-id="f70ba-106">Interface</span></span>|<span data-ttu-id="f70ba-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f70ba-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="f70ba-108">Proporciona métodos para crear, inicializar y administrar a un servidor proxy en un proceso de cliente.</span><span class="sxs-lookup"><span data-stu-id="f70ba-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f70ba-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f70ba-109">Requirements</span></span>  
 <span data-ttu-id="f70ba-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f70ba-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f70ba-111">**Encabezado:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="f70ba-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="f70ba-112">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f70ba-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f70ba-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f70ba-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f70ba-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f70ba-114">See Also</span></span>  
 [<span data-ttu-id="f70ba-115">Coclases para el hospedaje</span><span class="sxs-lookup"><span data-stu-id="f70ba-115">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
