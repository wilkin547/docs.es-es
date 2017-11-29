---
title: IInstallReferenceEnum (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IInstallReferenceEnum
api_location: fusion.dll
api_type: COM
f1_keywords: IInstallReferenceEnum
helpviewer_keywords: IInstallReferenceEnum interface [.NET Framework fusion]
ms.assetid: 2863b33b-a541-462c-bbe8-702a2832898e
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d3847d06c77a92eb6e63542f03405ca0cb9c9560
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iinstallreferenceenum-interface"></a><span data-ttu-id="dadd4-102">IInstallReferenceEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dadd4-102">IInstallReferenceEnum Interface</span></span>
<span data-ttu-id="dadd4-103">Representa un enumerador para los ensamblados instalados en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="dadd4-103">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dadd4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dadd4-104">Syntax</span></span>  
  
```  
interface IInstallReferenceEnum : IUnknown {  
    HRESULT GetNextInstallReferenceItem (  
        [out] IInstallReferenceItem **ppRefItem,  
        [in]  DWORD dwFlags,  
        [in]  LPVOID pvReserved  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="dadd4-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="dadd4-105">Methods</span></span>  
  
|<span data-ttu-id="dadd4-106">Método</span><span class="sxs-lookup"><span data-stu-id="dadd4-106">Method</span></span>|<span data-ttu-id="dadd4-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="dadd4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dadd4-108">GetNextInstallReferenceItem (método)</span><span class="sxs-lookup"><span data-stu-id="dadd4-108">GetNextInstallReferenceItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-getnextinstallreferenceitem-method.md)|<span data-ttu-id="dadd4-109">Obtiene un puntero a la siguiente `IInstallReferenceItem` contenida en esta instancia `IInstallReferenceEnum`.</span><span class="sxs-lookup"><span data-stu-id="dadd4-109">Gets a pointer to the next `IInstallReferenceItem` contained in this `IInstallReferenceEnum`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dadd4-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dadd4-110">Requirements</span></span>  
 <span data-ttu-id="dadd4-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dadd4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dadd4-112">**Encabezado:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="dadd4-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="dadd4-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dadd4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dadd4-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="dadd4-114">See Also</span></span>  
 [<span data-ttu-id="dadd4-115">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="dadd4-115">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="dadd4-116">IInstallReferenceItem (interfaz)</span><span class="sxs-lookup"><span data-stu-id="dadd4-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
