---
description: 'Más información acerca de: coclase Clrruntimehost ('
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
ms.openlocfilehash: a371b9b7263f8bb58b5c513de6647320f000beed
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799894"
---
# <a name="clrruntimehost-coclass"></a><span data-ttu-id="6e984-103">CLRRuntimeHost (Coclase)</span><span class="sxs-lookup"><span data-stu-id="6e984-103">CLRRuntimeHost Coclass</span></span>

<span data-ttu-id="6e984-104">Proporciona interfaces para administrar la ejecución del código en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6e984-104">Provides interfaces for managing code execution by the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e984-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6e984-105">Syntax</span></span>  
  
```cpp  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="6e984-106">Interfaces</span><span class="sxs-lookup"><span data-stu-id="6e984-106">Interfaces</span></span>  
  
|<span data-ttu-id="6e984-107">Interfaz</span><span class="sxs-lookup"><span data-stu-id="6e984-107">Interface</span></span>|<span data-ttu-id="6e984-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="6e984-108">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="6e984-109">ICLRRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6e984-109">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)|<span data-ttu-id="6e984-110">Proporciona métodos para controlar la ejecución de aplicaciones por parte del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6e984-110">Provides methods for controlling the execution of applications by the runtime.</span></span>|  
|[<span data-ttu-id="6e984-111">ICLRValidator (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6e984-111">ICLRValidator Interface</span></span>](iclrvalidator-interface.md)|<span data-ttu-id="6e984-112">Proporciona métodos para la validación de imágenes ejecutables portables e informes detallados de errores de validación.</span><span class="sxs-lookup"><span data-stu-id="6e984-112">Provides methods for validation of portable executable images and for detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6e984-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6e984-113">Requirements</span></span>  

 <span data-ttu-id="6e984-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e984-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e984-115">**Encabezado:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="6e984-115">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="6e984-116">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6e984-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6e984-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e984-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e984-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="6e984-118">See also</span></span>

- [<span data-ttu-id="6e984-119">Coclases para el hospedaje</span><span class="sxs-lookup"><span data-stu-id="6e984-119">Hosting Coclasses</span></span>](hosting-coclasses.md)
