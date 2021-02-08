---
description: 'Más información sobre: ITypeName:: GetAssemblyName ((método)'
title: ITypeName::GetAssemblyName (Método)
ms.date: 03/30/2017
api_name:
- ITypeName.GetAssemblyName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetAssemblyName
helpviewer_keywords:
- ITypeName::GetAssemblyName method [.NET Framework hosting]
- GetAssemblyName method [.NET Framework hosting]
ms.assetid: 97801d99-f5f1-4a30-882f-959827093fac
topic_type:
- apiref
ms.openlocfilehash: c2e84ec2fc7c6a300611643783d61b46c14997ce
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789351"
---
# <a name="itypenamegetassemblyname-method"></a><span data-ttu-id="dc47e-103">ITypeName::GetAssemblyName (Método)</span><span class="sxs-lookup"><span data-stu-id="dc47e-103">ITypeName::GetAssemblyName Method</span></span>

<span data-ttu-id="dc47e-104">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="dc47e-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc47e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dc47e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyName (  
    [out, retval] BSTR* rgbszAssemblyNames  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="dc47e-106">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dc47e-106">Requirements</span></span>  

 <span data-ttu-id="dc47e-107">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc47e-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc47e-108">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="dc47e-108">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dc47e-109">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dc47e-109">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dc47e-110">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc47e-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc47e-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc47e-111">See also</span></span>

- [<span data-ttu-id="dc47e-112">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="dc47e-112">Hosting Interfaces</span></span>](hosting-interfaces.md)
