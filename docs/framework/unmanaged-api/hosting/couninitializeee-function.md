---
title: CoUninitializeEE (Función)
ms.date: 03/30/2017
api_name:
- CoUninitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoUninitializeEE
helpviewer_keywords:
- CoUninitializeEE function [.NET Framework hosting]
ms.assetid: 5f5a311a-839a-465f-89d9-ff1c74da9736
topic_type:
- apiref
ms.openlocfilehash: 3531cfc0815c3f8a9479e35b2df60b2825801b39
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136848"
---
# <a name="couninitializeee-function"></a><span data-ttu-id="7ce8c-102">CoUninitializeEE (Función)</span><span class="sxs-lookup"><span data-stu-id="7ce8c-102">CoUninitializeEE Function</span></span>
<span data-ttu-id="7ce8c-103">`CoUninitializeEE` está obsoleto y no proporciona ninguna funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="7ce8c-103">`CoUninitializeEE` is obsolete and provides no functionality.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ce8c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7ce8c-104">Syntax</span></span>  
  
```cpp  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="7ce8c-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7ce8c-105">Remarks</span></span>  
 <span data-ttu-id="7ce8c-106">El motor de ejecución de Common Language Runtime no se puede descargar de un proceso.</span><span class="sxs-lookup"><span data-stu-id="7ce8c-106">The common language runtime execution engine cannot be unloaded from a process.</span></span> <span data-ttu-id="7ce8c-107">Para cerrar el motor de ejecución, llame a [CorExitProcess (](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).</span><span class="sxs-lookup"><span data-stu-id="7ce8c-107">To shut down the execution engine call [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ce8c-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ce8c-108">See also</span></span>

- [<span data-ttu-id="7ce8c-109">CoInitializeEE (función)</span><span class="sxs-lookup"><span data-stu-id="7ce8c-109">CoInitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)
- [<span data-ttu-id="7ce8c-110">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="7ce8c-110">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
