---
title: CoUninitializeEE (Función)
ms.date: 03/30/2017
api_name:
- CoUninitializeEE
api_location:
- mscoree.dll
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
ms.openlocfilehash: 73fa281d28e9b5362ff386b55b07dd431f1915f4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429187"
---
# <a name="couninitializeee-function"></a><span data-ttu-id="a4271-102">CoUninitializeEE (Función)</span><span class="sxs-lookup"><span data-stu-id="a4271-102">CoUninitializeEE Function</span></span>
<span data-ttu-id="a4271-103">`CoUninitializeEE` está obsoleto y no proporciona ninguna funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="a4271-103">`CoUninitializeEE` is obsolete and provides no functionality.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4271-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a4271-104">Syntax</span></span>  
  
```  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="a4271-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a4271-105">Remarks</span></span>  
 <span data-ttu-id="a4271-106">El motor de ejecución de common language runtime no se puede descargar desde un proceso.</span><span class="sxs-lookup"><span data-stu-id="a4271-106">The common language runtime execution engine cannot be unloaded from a process.</span></span> <span data-ttu-id="a4271-107">Para cerrar la llamada del motor de ejecución [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).</span><span class="sxs-lookup"><span data-stu-id="a4271-107">To shut down the execution engine call [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4271-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4271-108">See Also</span></span>  
 [<span data-ttu-id="a4271-109">CoInitializeEE (función)</span><span class="sxs-lookup"><span data-stu-id="a4271-109">CoInitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)  
 [<span data-ttu-id="a4271-110">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="a4271-110">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
