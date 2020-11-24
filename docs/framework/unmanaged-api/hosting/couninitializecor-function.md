---
title: CoUninitializeCor (Función)
ms.date: 03/30/2017
api_name:
- CoUninitializeCor
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoUninitializeCor
helpviewer_keywords:
- CoUninitializeCor function [.NET Framework hosting]
ms.assetid: 50a95b8b-9766-470e-bb29-2c7ecddfd4a1
topic_type:
- apiref
ms.openlocfilehash: 7d39c6fda6f159bfc937f62dc45d0d7ce37657f3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687886"
---
# <a name="couninitializecor-function"></a><span data-ttu-id="80f3e-102">CoUninitializeCor (Función)</span><span class="sxs-lookup"><span data-stu-id="80f3e-102">CoUninitializeCor Function</span></span>

<span data-ttu-id="80f3e-103">`CoUninitializeCor` está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="80f3e-103">`CoUninitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80f3e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="80f3e-104">Syntax</span></span>  
  
```cpp  
STDAPI_(void) CoUninitializeCor(void);  
```  
  
## <a name="remarks"></a><span data-ttu-id="80f3e-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="80f3e-105">Remarks</span></span>  

 <span data-ttu-id="80f3e-106">No se puede descargar el Common Language Runtime de un proceso.</span><span class="sxs-lookup"><span data-stu-id="80f3e-106">The common language runtime cannot be unloaded from a process.</span></span> <span data-ttu-id="80f3e-107">Para quitar completamente el Runtime de un proceso en ejecución, debe cerrar ese proceso.</span><span class="sxs-lookup"><span data-stu-id="80f3e-107">To completely remove the runtime from a running process, you must shut down that process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80f3e-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="80f3e-108">See also</span></span>

- [<span data-ttu-id="80f3e-109">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="80f3e-109">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
