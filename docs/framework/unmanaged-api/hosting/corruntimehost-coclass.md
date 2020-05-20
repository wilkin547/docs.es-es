---
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
ms.openlocfilehash: fe378307ce2bda6e1a267e46433ead70a0e2299e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616531"
---
# <a name="corruntimehost-coclass"></a><span data-ttu-id="d97f5-102">CorRuntimeHost (Coclase)</span><span class="sxs-lookup"><span data-stu-id="d97f5-102">CorRuntimeHost Coclass</span></span>
<span data-ttu-id="d97f5-103">Proporciona interfaces para administrar las aplicaciones que se ejecutan en el Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="d97f5-103">Provides interfaces for managing applications that are being executed by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d97f5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d97f5-104">Syntax</span></span>  
  
```cpp  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="d97f5-105">Interfaces</span><span class="sxs-lookup"><span data-stu-id="d97f5-105">Interfaces</span></span>  
  
|<span data-ttu-id="d97f5-106">Interfaz</span><span class="sxs-lookup"><span data-stu-id="d97f5-106">Interface</span></span>|<span data-ttu-id="d97f5-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d97f5-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="d97f5-108">ICorConfiguration (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d97f5-108">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)|<span data-ttu-id="d97f5-109">Proporciona métodos para configurar el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="d97f5-109">Provides methods for configuring the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="d97f5-110">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d97f5-110">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)|<span data-ttu-id="d97f5-111">Proporciona métodos que permiten al host iniciar y detener el Common Language Runtime explícitamente, para crear y configurar dominios de aplicación, para tener acceso al dominio predeterminado y para enumerar todos los dominios que se ejecutan en el proceso.</span><span class="sxs-lookup"><span data-stu-id="d97f5-111">Provides methods that enable the host to start and stop the common language runtime explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>|  
|[<span data-ttu-id="d97f5-112">IDebuggerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d97f5-112">IDebuggerInfo Interface</span></span>](idebuggerinfo-interface.md)|<span data-ttu-id="d97f5-113">Proporciona métodos para obtener información sobre el estado de los servicios de depuración.</span><span class="sxs-lookup"><span data-stu-id="d97f5-113">Provides methods for obtaining information about the state of the debugging services.</span></span>|  
|[<span data-ttu-id="d97f5-114">IGCHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d97f5-114">IGCHost Interface</span></span>](igchost-interface.md)|<span data-ttu-id="d97f5-115">Proporciona métodos para obtener información sobre el sistema de recolección de elementos no utilizados y para controlar algunos aspectos de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="d97f5-115">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>|  
|<span data-ttu-id="d97f5-116">IValidator</span><span class="sxs-lookup"><span data-stu-id="d97f5-116">"IValidator"</span></span>|<span data-ttu-id="d97f5-117">Proporciona métodos para la validación de imágenes ejecutables portables e informes detallados de errores de validación.</span><span class="sxs-lookup"><span data-stu-id="d97f5-117">Provides methods for validation of portable executable images and detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d97f5-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d97f5-118">Requirements</span></span>  
 <span data-ttu-id="d97f5-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d97f5-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d97f5-120">**Encabezado:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="d97f5-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="d97f5-121">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d97f5-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d97f5-122">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d97f5-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d97f5-123">Consulta también</span><span class="sxs-lookup"><span data-stu-id="d97f5-123">See also</span></span>

- [<span data-ttu-id="d97f5-124">Coclases para el hospedaje</span><span class="sxs-lookup"><span data-stu-id="d97f5-124">Hosting Coclasses</span></span>](hosting-coclasses.md)
