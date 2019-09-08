---
title: IInstallReferenceEnum (Interfaz)
ms.date: 03/30/2017
api_name:
- IInstallReferenceEnum
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceEnum
helpviewer_keywords:
- IInstallReferenceEnum interface [.NET Framework fusion]
ms.assetid: 2863b33b-a541-462c-bbe8-702a2832898e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d29b9e2a9b9022f682065816a62734d6c5b2d62
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796410"
---
# <a name="iinstallreferenceenum-interface"></a><span data-ttu-id="14537-102">IInstallReferenceEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="14537-102">IInstallReferenceEnum Interface</span></span>
<span data-ttu-id="14537-103">Representa un enumerador para los ensamblados a los que se hace referencia instalados en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="14537-103">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14537-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="14537-104">Syntax</span></span>  
  
```cpp  
interface IInstallReferenceEnum : IUnknown {  
    HRESULT GetNextInstallReferenceItem (  
        [out] IInstallReferenceItem **ppRefItem,  
        [in]  DWORD dwFlags,  
        [in]  LPVOID pvReserved  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="14537-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="14537-105">Methods</span></span>  
  
|<span data-ttu-id="14537-106">Método</span><span class="sxs-lookup"><span data-stu-id="14537-106">Method</span></span>|<span data-ttu-id="14537-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="14537-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="14537-108">GetNextInstallReferenceItem (método)</span><span class="sxs-lookup"><span data-stu-id="14537-108">GetNextInstallReferenceItem Method</span></span>](iinstallreferenceenum-getnextinstallreferenceitem-method.md)|<span data-ttu-id="14537-109">Obtiene un puntero al siguiente `IInstallReferenceItem` contenido en este. `IInstallReferenceEnum`</span><span class="sxs-lookup"><span data-stu-id="14537-109">Gets a pointer to the next `IInstallReferenceItem` contained in this `IInstallReferenceEnum`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="14537-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="14537-110">Requirements</span></span>  
 <span data-ttu-id="14537-111">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14537-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14537-112">**Encabezado**: Fusion. h</span><span class="sxs-lookup"><span data-stu-id="14537-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="14537-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14537-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14537-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="14537-114">See also</span></span>

- [<span data-ttu-id="14537-115">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="14537-115">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="14537-116">IInstallReferenceItem (interfaz)</span><span class="sxs-lookup"><span data-stu-id="14537-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
