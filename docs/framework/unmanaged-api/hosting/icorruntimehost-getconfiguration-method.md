---
description: 'Más información acerca de: ICorRuntimeHost:: GetConfiguration (método)'
title: ICorRuntimeHost::GetConfiguration (Método)
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.GetConfiguration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::GetConfiguration
helpviewer_keywords:
- ICorRuntimeHost::GetConfiguration method [.NET Framework hosting]
- GetConfiguration method [.NET Framework hosting]
ms.assetid: c431617a-b055-44a0-8730-48b7a86d9610
topic_type:
- apiref
ms.openlocfilehash: d3e3f065c3957fb29daa11ed7c46858a53865c91
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784839"
---
# <a name="icorruntimehostgetconfiguration-method"></a><span data-ttu-id="57740-103">ICorRuntimeHost::GetConfiguration (Método)</span><span class="sxs-lookup"><span data-stu-id="57740-103">ICorRuntimeHost::GetConfiguration Method</span></span>

<span data-ttu-id="57740-104">Obtiene un objeto que permite al host especificar la configuración de devolución de llamada del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="57740-104">Gets an object that allows the host to specify the callback configuration of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57740-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="57740-105">Syntax</span></span>  
  
```cpp  
HRESULT GetConfiguration(  
    [out] ICorConfiguration** pConfiguration  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57740-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="57740-106">Parameters</span></span>  

 `pConfiguration`  
 <span data-ttu-id="57740-107">enuncia Puntero a la dirección de un objeto [ICorConfiguration](icorconfiguration-interface.md) que se puede usar para configurar el CLR.</span><span class="sxs-lookup"><span data-stu-id="57740-107">[out] A pointer to the address of an [ICorConfiguration](icorconfiguration-interface.md) object that can be used to configure the CLR.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57740-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="57740-108">Remarks</span></span>  

 <span data-ttu-id="57740-109">CLR se debe configurar antes de su inicialización; de lo contrario, el `GetConfiguration` método devuelve un valor HRESULT que indica un error.</span><span class="sxs-lookup"><span data-stu-id="57740-109">The CLR must be configured prior to its initialization; otherwise, the `GetConfiguration` method returns an HRESULT indicating an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57740-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="57740-110">Requirements</span></span>  

 <span data-ttu-id="57740-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57740-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57740-112">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="57740-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="57740-113">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="57740-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="57740-114">**.NET Framework versiones:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="57740-114">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57740-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="57740-115">See also</span></span>

- [<span data-ttu-id="57740-116">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="57740-116">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
