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
ms.openlocfilehash: e6616392eaa23f8ba40247c5aabd12e4d530cea1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687852"
---
# <a name="couninitializeee-function"></a><span data-ttu-id="36493-102">CoUninitializeEE (Función)</span><span class="sxs-lookup"><span data-stu-id="36493-102">CoUninitializeEE Function</span></span>

<span data-ttu-id="36493-103">`CoUninitializeEE` está obsoleto y no proporciona ninguna funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="36493-103">`CoUninitializeEE` is obsolete and provides no functionality.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36493-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="36493-104">Syntax</span></span>  
  
```cpp  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="36493-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="36493-105">Remarks</span></span>  

 <span data-ttu-id="36493-106">El motor de ejecución de Common Language Runtime no se puede descargar de un proceso.</span><span class="sxs-lookup"><span data-stu-id="36493-106">The common language runtime execution engine cannot be unloaded from a process.</span></span> <span data-ttu-id="36493-107">Para cerrar el motor de ejecución, llame a [CorExitProcess (](corexitprocess-function.md).</span><span class="sxs-lookup"><span data-stu-id="36493-107">To shut down the execution engine call [CorExitProcess](corexitprocess-function.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36493-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="36493-108">See also</span></span>

- [<span data-ttu-id="36493-109">CoInitializeEE (Función)</span><span class="sxs-lookup"><span data-stu-id="36493-109">CoInitializeEE Function</span></span>](coinitializeee-function.md)
- [<span data-ttu-id="36493-110">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="36493-110">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
