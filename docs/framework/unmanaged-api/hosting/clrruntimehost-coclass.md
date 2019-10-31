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
ms.openlocfilehash: b1e595e1a4f1b462437f47207b998829a8bd774d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129462"
---
# <a name="clrruntimehost-coclass"></a><span data-ttu-id="adc21-102">CLRRuntimeHost (Coclase)</span><span class="sxs-lookup"><span data-stu-id="adc21-102">CLRRuntimeHost Coclass</span></span>
<span data-ttu-id="adc21-103">Proporciona interfaces para administrar la ejecución del código en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="adc21-103">Provides interfaces for managing code execution by the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adc21-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="adc21-104">Syntax</span></span>  
  
```cpp  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="adc21-105">Interfaces</span><span class="sxs-lookup"><span data-stu-id="adc21-105">Interfaces</span></span>  
  
|<span data-ttu-id="adc21-106">Interfaz</span><span class="sxs-lookup"><span data-stu-id="adc21-106">Interface</span></span>|<span data-ttu-id="adc21-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="adc21-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="adc21-108">ICLRRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="adc21-108">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)|<span data-ttu-id="adc21-109">Proporciona métodos para controlar la ejecución de aplicaciones por parte del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="adc21-109">Provides methods for controlling the execution of applications by the runtime.</span></span>|  
|[<span data-ttu-id="adc21-110">ICLRValidator (interfaz)</span><span class="sxs-lookup"><span data-stu-id="adc21-110">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)|<span data-ttu-id="adc21-111">Proporciona métodos para la validación de imágenes ejecutables portables e informes detallados de errores de validación.</span><span class="sxs-lookup"><span data-stu-id="adc21-111">Provides methods for validation of portable executable images and for detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="adc21-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="adc21-112">Requirements</span></span>  
 <span data-ttu-id="adc21-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="adc21-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="adc21-114">**Encabezado:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="adc21-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="adc21-115">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="adc21-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="adc21-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="adc21-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adc21-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="adc21-117">See also</span></span>

- [<span data-ttu-id="adc21-118">Coclases para el hospedaje</span><span class="sxs-lookup"><span data-stu-id="adc21-118">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
