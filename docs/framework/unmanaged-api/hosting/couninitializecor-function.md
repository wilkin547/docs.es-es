---
description: 'Más información acerca de: Couninitializecor ((función)'
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
ms.openlocfilehash: 1aa3482b6891779b4c85c29079ccd26d7170934e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746209"
---
# <a name="couninitializecor-function"></a><span data-ttu-id="a49b2-103">CoUninitializeCor (Función)</span><span class="sxs-lookup"><span data-stu-id="a49b2-103">CoUninitializeCor Function</span></span>

<span data-ttu-id="a49b2-104">`CoUninitializeCor` está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="a49b2-104">`CoUninitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a49b2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a49b2-105">Syntax</span></span>  
  
```cpp  
STDAPI_(void) CoUninitializeCor(void);  
```  
  
## <a name="remarks"></a><span data-ttu-id="a49b2-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a49b2-106">Remarks</span></span>  

 <span data-ttu-id="a49b2-107">No se puede descargar el Common Language Runtime de un proceso.</span><span class="sxs-lookup"><span data-stu-id="a49b2-107">The common language runtime cannot be unloaded from a process.</span></span> <span data-ttu-id="a49b2-108">Para quitar completamente el Runtime de un proceso en ejecución, debe cerrar ese proceso.</span><span class="sxs-lookup"><span data-stu-id="a49b2-108">To completely remove the runtime from a running process, you must shut down that process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a49b2-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="a49b2-109">See also</span></span>

- [<span data-ttu-id="a49b2-110">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="a49b2-110">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
