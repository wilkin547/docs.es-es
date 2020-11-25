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
ms.openlocfilehash: 7c77cb2e89cb8fd87bf219780b9460649de19c9d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731776"
---
# <a name="clrruntimehost-coclass"></a><span data-ttu-id="abcf9-102">CLRRuntimeHost (Coclase)</span><span class="sxs-lookup"><span data-stu-id="abcf9-102">CLRRuntimeHost Coclass</span></span>

<span data-ttu-id="abcf9-103">Proporciona interfaces para administrar la ejecución del código en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="abcf9-103">Provides interfaces for managing code execution by the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abcf9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="abcf9-104">Syntax</span></span>  
  
```cpp  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="abcf9-105">Interfaces</span><span class="sxs-lookup"><span data-stu-id="abcf9-105">Interfaces</span></span>  
  
|<span data-ttu-id="abcf9-106">Interfaz</span><span class="sxs-lookup"><span data-stu-id="abcf9-106">Interface</span></span>|<span data-ttu-id="abcf9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="abcf9-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="abcf9-108">ICLRRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="abcf9-108">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)|<span data-ttu-id="abcf9-109">Proporciona métodos para controlar la ejecución de aplicaciones por parte del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="abcf9-109">Provides methods for controlling the execution of applications by the runtime.</span></span>|  
|[<span data-ttu-id="abcf9-110">ICLRValidator (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="abcf9-110">ICLRValidator Interface</span></span>](iclrvalidator-interface.md)|<span data-ttu-id="abcf9-111">Proporciona métodos para la validación de imágenes ejecutables portables e informes detallados de errores de validación.</span><span class="sxs-lookup"><span data-stu-id="abcf9-111">Provides methods for validation of portable executable images and for detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="abcf9-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="abcf9-112">Requirements</span></span>  

 <span data-ttu-id="abcf9-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="abcf9-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abcf9-114">**Encabezado:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="abcf9-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="abcf9-115">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="abcf9-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="abcf9-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="abcf9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abcf9-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="abcf9-117">See also</span></span>

- [<span data-ttu-id="abcf9-118">Coclases para el hospedaje</span><span class="sxs-lookup"><span data-stu-id="abcf9-118">Hosting Coclasses</span></span>](hosting-coclasses.md)
