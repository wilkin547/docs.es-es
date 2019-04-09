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
ms.openlocfilehash: 7b3712b4cb66facc105a03d7bfad235f09339056
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59193010"
---
# <a name="couninitializeee-function"></a><span data-ttu-id="a6270-102">CoUninitializeEE (Función)</span><span class="sxs-lookup"><span data-stu-id="a6270-102">CoUninitializeEE Function</span></span>
`CoUninitializeEE` <span data-ttu-id="a6270-103">está obsoleto y no proporciona ninguna funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="a6270-103">is obsolete and provides no functionality.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6270-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a6270-104">Syntax</span></span>  
  
```  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="a6270-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a6270-105">Remarks</span></span>  
 <span data-ttu-id="a6270-106">El motor de ejecución de common language runtime no se puede descargar desde un proceso.</span><span class="sxs-lookup"><span data-stu-id="a6270-106">The common language runtime execution engine cannot be unloaded from a process.</span></span> <span data-ttu-id="a6270-107">Para apagar la llamada del motor de ejecución [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).</span><span class="sxs-lookup"><span data-stu-id="a6270-107">To shut down the execution engine call [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6270-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6270-108">See also</span></span>

- [<span data-ttu-id="a6270-109">CoInitializeEE (Función)</span><span class="sxs-lookup"><span data-stu-id="a6270-109">CoInitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)
- [<span data-ttu-id="a6270-110">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="a6270-110">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
