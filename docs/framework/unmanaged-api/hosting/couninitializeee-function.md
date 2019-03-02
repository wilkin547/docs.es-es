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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c4e22c2e80af37177294d86c2e5775a5c296fe7
ms.sourcegitcommit: 79066169e93d9d65203028b21983574ad9dcf6b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/01/2019
ms.locfileid: "57211863"
---
# <a name="couninitializeee-function"></a><span data-ttu-id="d92f8-102">CoUninitializeEE (Función)</span><span class="sxs-lookup"><span data-stu-id="d92f8-102">CoUninitializeEE Function</span></span>
<span data-ttu-id="d92f8-103">`CoUninitializeEE` está obsoleto y no proporciona ninguna funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="d92f8-103">`CoUninitializeEE` is obsolete and provides no functionality.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d92f8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d92f8-104">Syntax</span></span>  
  
```  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="d92f8-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d92f8-105">Remarks</span></span>  
 <span data-ttu-id="d92f8-106">El motor de ejecución de common language runtime no se puede descargar desde un proceso.</span><span class="sxs-lookup"><span data-stu-id="d92f8-106">The common language runtime execution engine cannot be unloaded from a process.</span></span> <span data-ttu-id="d92f8-107">Para apagar la llamada del motor de ejecución [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).</span><span class="sxs-lookup"><span data-stu-id="d92f8-107">To shut down the execution engine call [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d92f8-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="d92f8-108">See also</span></span>
- [<span data-ttu-id="d92f8-109">CoInitializeEE (función)</span><span class="sxs-lookup"><span data-stu-id="d92f8-109">CoInitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)
- [<span data-ttu-id="d92f8-110">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="d92f8-110">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
