---
title: CLRRuntimeHost (Coclase)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CLRRuntimeHost Coclass
api_location: mscoree.dll
api_type: COM
f1_keywords: CLRRuntimeHost
helpviewer_keywords: CLRRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 2ac9cbf5-8a2d-4e4f-8831-0dad8ef0a897
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 372b2466baaa76ba47a6710447d93f9fa6bb967f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="clrruntimehost-coclass"></a><span data-ttu-id="142a2-102">CLRRuntimeHost (Coclase)</span><span class="sxs-lookup"><span data-stu-id="142a2-102">CLRRuntimeHost Coclass</span></span>
<span data-ttu-id="142a2-103">Proporciona interfaces para administrar la ejecución de código en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="142a2-103">Provides interfaces for managing code execution by the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="142a2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="142a2-104">Syntax</span></span>  
  
```  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="142a2-105">Interfaces</span><span class="sxs-lookup"><span data-stu-id="142a2-105">Interfaces</span></span>  
  
|<span data-ttu-id="142a2-106">Interfaz</span><span class="sxs-lookup"><span data-stu-id="142a2-106">Interface</span></span>|<span data-ttu-id="142a2-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="142a2-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="142a2-108">ICLRRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="142a2-108">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)|<span data-ttu-id="142a2-109">Proporciona métodos para controlar la ejecución de aplicaciones en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="142a2-109">Provides methods for controlling the execution of applications by the runtime.</span></span>|  
|[<span data-ttu-id="142a2-110">ICLRValidator (interfaz)</span><span class="sxs-lookup"><span data-stu-id="142a2-110">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)|<span data-ttu-id="142a2-111">Proporciona métodos para la validación de imágenes ejecutables portables y para los informes detallados de errores de validación.</span><span class="sxs-lookup"><span data-stu-id="142a2-111">Provides methods for validation of portable executable images and for detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="142a2-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="142a2-112">Requirements</span></span>  
 <span data-ttu-id="142a2-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="142a2-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="142a2-114">**Encabezado:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="142a2-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="142a2-115">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="142a2-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="142a2-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="142a2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="142a2-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="142a2-117">See Also</span></span>  
 [<span data-ttu-id="142a2-118">Coclases para el hospedaje</span><span class="sxs-lookup"><span data-stu-id="142a2-118">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
