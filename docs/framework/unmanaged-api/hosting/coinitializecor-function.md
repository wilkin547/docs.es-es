---
description: 'Más información acerca de: CoInitializeCor ((función)'
title: CoInitializeCor (Función)
ms.date: 03/30/2017
api_name:
- CoInitializeCor
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeCor
helpviewer_keywords:
- CoInitializeCor function [.NET Framework hosting]
ms.assetid: 9b9079fb-579e-4141-b3f0-791072dd40dc
topic_type:
- apiref
ms.openlocfilehash: e1db9914cce8a92cecf78123a2e247d75ec74acf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799855"
---
# <a name="coinitializecor-function"></a><span data-ttu-id="74d24-103">CoInitializeCor (Función)</span><span class="sxs-lookup"><span data-stu-id="74d24-103">CoInitializeCor Function</span></span>

<span data-ttu-id="74d24-104">`CoInitializeCor` está obsoleto.</span><span class="sxs-lookup"><span data-stu-id="74d24-104">`CoInitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74d24-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74d24-105">Syntax</span></span>  
  
```cpp  
STDAPI CoInitializeCor (  
    DWORD fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="74d24-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="74d24-106">Remarks</span></span>  

 <span data-ttu-id="74d24-107">Para inicializar el Common Language Runtime, use [CorBindToRuntimeEx](corbindtoruntimeex-function.md) o [CorBindToCurrentRuntime (](corbindtocurrentruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="74d24-107">To initialize the common language runtime, use either [CorBindToRuntimeEx](corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74d24-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="74d24-108">Requirements</span></span>  

 <span data-ttu-id="74d24-109">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="74d24-109">**Header:** Cor.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74d24-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="74d24-110">See also</span></span>

- [<span data-ttu-id="74d24-111">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="74d24-111">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
