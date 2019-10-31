---
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
ms.openlocfilehash: 87549118742da797ef0dd1b08ae9e72c466f7841
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139566"
---
# <a name="icorruntimehostgetconfiguration-method"></a><span data-ttu-id="e7ce8-102">ICorRuntimeHost::GetConfiguration (Método)</span><span class="sxs-lookup"><span data-stu-id="e7ce8-102">ICorRuntimeHost::GetConfiguration Method</span></span>
<span data-ttu-id="e7ce8-103">Obtiene un objeto que permite al host especificar la configuración de devolución de llamada del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="e7ce8-103">Gets an object that allows the host to specify the callback configuration of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7ce8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e7ce8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConfiguration(  
    [out] ICorConfiguration** pConfiguration  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7ce8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e7ce8-105">Parameters</span></span>  
 `pConfiguration`  
 <span data-ttu-id="e7ce8-106">enuncia Puntero a la dirección de un objeto [ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md) que se puede usar para configurar el CLR.</span><span class="sxs-lookup"><span data-stu-id="e7ce8-106">[out] A pointer to the address of an [ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md) object that can be used to configure the CLR.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7ce8-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e7ce8-107">Remarks</span></span>  
 <span data-ttu-id="e7ce8-108">CLR se debe configurar antes de su inicialización; de lo contrario, el método `GetConfiguration` devuelve un valor HRESULT que indica un error.</span><span class="sxs-lookup"><span data-stu-id="e7ce8-108">The CLR must be configured prior to its initialization; otherwise, the `GetConfiguration` method returns an HRESULT indicating an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7ce8-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e7ce8-109">Requirements</span></span>  
 <span data-ttu-id="e7ce8-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7ce8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7ce8-111">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e7ce8-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e7ce8-112">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e7ce8-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e7ce8-113">**.NET Framework versiones:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="e7ce8-113">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7ce8-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7ce8-114">See also</span></span>

- [<span data-ttu-id="e7ce8-115">ICorRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e7ce8-115">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
