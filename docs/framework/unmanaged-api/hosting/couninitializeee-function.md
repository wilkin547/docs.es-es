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
ms.openlocfilehash: fa6297e926d53c02bb0d1af7b59b45b8ee152399
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616468"
---
# <a name="couninitializeee-function"></a><span data-ttu-id="200ac-102">CoUninitializeEE (Función)</span><span class="sxs-lookup"><span data-stu-id="200ac-102">CoUninitializeEE Function</span></span>
<span data-ttu-id="200ac-103">`CoUninitializeEE`está obsoleto y no proporciona ninguna funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="200ac-103">`CoUninitializeEE` is obsolete and provides no functionality.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="200ac-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="200ac-104">Syntax</span></span>  
  
```cpp  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="200ac-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="200ac-105">Remarks</span></span>  
 <span data-ttu-id="200ac-106">El motor de ejecución de Common Language Runtime no se puede descargar de un proceso.</span><span class="sxs-lookup"><span data-stu-id="200ac-106">The common language runtime execution engine cannot be unloaded from a process.</span></span> <span data-ttu-id="200ac-107">Para cerrar el motor de ejecución, llame a [CorExitProcess (](corexitprocess-function.md).</span><span class="sxs-lookup"><span data-stu-id="200ac-107">To shut down the execution engine call [CorExitProcess](corexitprocess-function.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="200ac-108">Consulta también</span><span class="sxs-lookup"><span data-stu-id="200ac-108">See also</span></span>

- [<span data-ttu-id="200ac-109">CoInitializeEE (Función)</span><span class="sxs-lookup"><span data-stu-id="200ac-109">CoInitializeEE Function</span></span>](coinitializeee-function.md)
- [<span data-ttu-id="200ac-110">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="200ac-110">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
