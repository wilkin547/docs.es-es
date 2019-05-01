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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0845c4d493cb3c750931a0ae2ad92b628a255c0c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985756"
---
# <a name="couninitializecor-function"></a><span data-ttu-id="63bdd-102">CoUninitializeCor (Función)</span><span class="sxs-lookup"><span data-stu-id="63bdd-102">CoUninitializeCor Function</span></span>
<span data-ttu-id="63bdd-103">`CoUninitializeCor` está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="63bdd-103">`CoUninitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63bdd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="63bdd-104">Syntax</span></span>  
  
```  
STDAPI_(void) CoUninitializeCor(void);  
```  
  
## <a name="remarks"></a><span data-ttu-id="63bdd-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="63bdd-105">Remarks</span></span>  
 <span data-ttu-id="63bdd-106">Common language runtime no se puede descargar desde un proceso.</span><span class="sxs-lookup"><span data-stu-id="63bdd-106">The common language runtime cannot be unloaded from a process.</span></span> <span data-ttu-id="63bdd-107">Para quitar completamente el tiempo de ejecución de un proceso en ejecución, debe cerrar el proceso.</span><span class="sxs-lookup"><span data-stu-id="63bdd-107">To completely remove the runtime from a running process, you must shut down that process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63bdd-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="63bdd-108">See also</span></span>

- [<span data-ttu-id="63bdd-109">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="63bdd-109">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
