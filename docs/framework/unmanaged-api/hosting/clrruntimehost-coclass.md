---
title: CLRRuntimeHost (Coclase)
ms.date: 03/30/2017
api_name:
- CLRRuntimeHost Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CLRRuntimeHost
helpviewer_keywords:
- CLRRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 2ac9cbf5-8a2d-4e4f-8831-0dad8ef0a897
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8bae2d134c412023d0f126453b5285662d994c78
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789602"
---
# <a name="clrruntimehost-coclass"></a><span data-ttu-id="199e6-102">CLRRuntimeHost (Coclase)</span><span class="sxs-lookup"><span data-stu-id="199e6-102">CLRRuntimeHost Coclass</span></span>
<span data-ttu-id="199e6-103">Proporciona interfaces para administrar la ejecución de código por el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="199e6-103">Provides interfaces for managing code execution by the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="199e6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="199e6-104">Syntax</span></span>  
  
```  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="199e6-105">Interfaces</span><span class="sxs-lookup"><span data-stu-id="199e6-105">Interfaces</span></span>  
  
|<span data-ttu-id="199e6-106">Interfaz</span><span class="sxs-lookup"><span data-stu-id="199e6-106">Interface</span></span>|<span data-ttu-id="199e6-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="199e6-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="199e6-108">ICLRRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="199e6-108">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)|<span data-ttu-id="199e6-109">Proporciona métodos para controlar la ejecución de aplicaciones por el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="199e6-109">Provides methods for controlling the execution of applications by the runtime.</span></span>|  
|[<span data-ttu-id="199e6-110">ICLRValidator (interfaz)</span><span class="sxs-lookup"><span data-stu-id="199e6-110">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)|<span data-ttu-id="199e6-111">Proporciona métodos para la validación de imágenes ejecutables portables y para generar informes detallados de errores de validación.</span><span class="sxs-lookup"><span data-stu-id="199e6-111">Provides methods for validation of portable executable images and for detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="199e6-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="199e6-112">Requirements</span></span>  
 <span data-ttu-id="199e6-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="199e6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="199e6-114">**Encabezado**: MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="199e6-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="199e6-115">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="199e6-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="199e6-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="199e6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="199e6-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="199e6-117">See also</span></span>

- [<span data-ttu-id="199e6-118">Coclases para el hospedaje</span><span class="sxs-lookup"><span data-stu-id="199e6-118">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
