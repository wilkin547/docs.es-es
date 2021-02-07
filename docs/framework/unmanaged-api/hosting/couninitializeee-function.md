---
description: 'Más información acerca de: CoUninitializeEE ((función)'
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
ms.openlocfilehash: e356135ea027bd52520eff9084ad2f7f09e1fe0b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746170"
---
# <a name="couninitializeee-function"></a><span data-ttu-id="ff11f-103">CoUninitializeEE (Función)</span><span class="sxs-lookup"><span data-stu-id="ff11f-103">CoUninitializeEE Function</span></span>

<span data-ttu-id="ff11f-104">`CoUninitializeEE` está obsoleto y no proporciona ninguna funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="ff11f-104">`CoUninitializeEE` is obsolete and provides no functionality.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff11f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ff11f-105">Syntax</span></span>  
  
```cpp  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="ff11f-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ff11f-106">Remarks</span></span>  

 <span data-ttu-id="ff11f-107">El motor de ejecución de Common Language Runtime no se puede descargar de un proceso.</span><span class="sxs-lookup"><span data-stu-id="ff11f-107">The common language runtime execution engine cannot be unloaded from a process.</span></span> <span data-ttu-id="ff11f-108">Para cerrar el motor de ejecución, llame a [CorExitProcess (](corexitprocess-function.md).</span><span class="sxs-lookup"><span data-stu-id="ff11f-108">To shut down the execution engine call [CorExitProcess](corexitprocess-function.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff11f-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff11f-109">See also</span></span>

- [<span data-ttu-id="ff11f-110">CoInitializeEE (Función)</span><span class="sxs-lookup"><span data-stu-id="ff11f-110">CoInitializeEE Function</span></span>](coinitializeee-function.md)
- [<span data-ttu-id="ff11f-111">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="ff11f-111">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
