---
description: 'Más información acerca de: coclase Corruntimehost ('
title: CorRuntimeHost (Coclase)
ms.date: 03/30/2017
api_name:
- CorRuntimeHost Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRuntimeHost
helpviewer_keywords:
- CoRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 5833740b-7d67-44b4-865c-b5bf45e291e3
topic_type:
- apiref
ms.openlocfilehash: cd2d01075e5c8264337e1e989b3d9fdc6bf68962
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760647"
---
# <a name="corruntimehost-coclass"></a><span data-ttu-id="09555-103">CorRuntimeHost (Coclase)</span><span class="sxs-lookup"><span data-stu-id="09555-103">CorRuntimeHost Coclass</span></span>

<span data-ttu-id="09555-104">Proporciona interfaces para administrar las aplicaciones que se ejecutan en el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="09555-104">Provides interfaces for managing applications that are being executed by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09555-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="09555-105">Syntax</span></span>  
  
```cpp  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="09555-106">Interfaces</span><span class="sxs-lookup"><span data-stu-id="09555-106">Interfaces</span></span>  
  
|<span data-ttu-id="09555-107">Interfaz</span><span class="sxs-lookup"><span data-stu-id="09555-107">Interface</span></span>|<span data-ttu-id="09555-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="09555-108">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="09555-109">ICorConfiguration (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="09555-109">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)|<span data-ttu-id="09555-110">Proporciona métodos para configurar el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="09555-110">Provides methods for configuring the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="09555-111">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="09555-111">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)|<span data-ttu-id="09555-112">Proporciona métodos que permiten al host iniciar y detener el Common Language Runtime explícitamente, para crear y configurar dominios de aplicación, para tener acceso al dominio predeterminado y para enumerar todos los dominios que se ejecutan en el proceso.</span><span class="sxs-lookup"><span data-stu-id="09555-112">Provides methods that enable the host to start and stop the common language runtime explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>|  
|[<span data-ttu-id="09555-113">IDebuggerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="09555-113">IDebuggerInfo Interface</span></span>](idebuggerinfo-interface.md)|<span data-ttu-id="09555-114">Proporciona métodos para obtener información sobre el estado de los servicios de depuración.</span><span class="sxs-lookup"><span data-stu-id="09555-114">Provides methods for obtaining information about the state of the debugging services.</span></span>|  
|[<span data-ttu-id="09555-115">IGCHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="09555-115">IGCHost Interface</span></span>](igchost-interface.md)|<span data-ttu-id="09555-116">Proporciona métodos para obtener información sobre el sistema de recolección de elementos no utilizados y para controlar algunos aspectos de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="09555-116">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>|  
|<span data-ttu-id="09555-117">IValidator</span><span class="sxs-lookup"><span data-stu-id="09555-117">"IValidator"</span></span>|<span data-ttu-id="09555-118">Proporciona métodos para la validación de imágenes ejecutables portables e informes detallados de errores de validación.</span><span class="sxs-lookup"><span data-stu-id="09555-118">Provides methods for validation of portable executable images and detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="09555-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="09555-119">Requirements</span></span>  

 <span data-ttu-id="09555-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09555-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09555-121">**Encabezado:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="09555-121">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="09555-122">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="09555-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="09555-123">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09555-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09555-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="09555-124">See also</span></span>

- [<span data-ttu-id="09555-125">Coclases para el hospedaje</span><span class="sxs-lookup"><span data-stu-id="09555-125">Hosting Coclasses</span></span>](hosting-coclasses.md)
