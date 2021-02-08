---
description: 'Más información acerca de: interfaz IInstallReferenceEnum ('
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
ms.openlocfilehash: 496bd508b95b51cb23949f32f8390c7cb733b37e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800113"
---
# <a name="iinstallreferenceenum-interface"></a><span data-ttu-id="e6f96-103">IInstallReferenceEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e6f96-103">IInstallReferenceEnum Interface</span></span>

<span data-ttu-id="e6f96-104">Representa un enumerador para los ensamblados a los que se hace referencia instalados en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="e6f96-104">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6f96-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e6f96-105">Syntax</span></span>  
  
```cpp  
interface IInstallReferenceEnum : IUnknown {  
    HRESULT GetNextInstallReferenceItem (  
        [out] IInstallReferenceItem **ppRefItem,  
        [in]  DWORD dwFlags,  
        [in]  LPVOID pvReserved  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e6f96-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="e6f96-106">Methods</span></span>  
  
|<span data-ttu-id="e6f96-107">Método</span><span class="sxs-lookup"><span data-stu-id="e6f96-107">Method</span></span>|<span data-ttu-id="e6f96-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="e6f96-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e6f96-109">Método GetNextInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="e6f96-109">GetNextInstallReferenceItem Method</span></span>](iinstallreferenceenum-getnextinstallreferenceitem-method.md)|<span data-ttu-id="e6f96-110">Obtiene un puntero al siguiente `IInstallReferenceItem` contenido en este `IInstallReferenceEnum` .</span><span class="sxs-lookup"><span data-stu-id="e6f96-110">Gets a pointer to the next `IInstallReferenceItem` contained in this `IInstallReferenceEnum`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e6f96-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e6f96-111">Requirements</span></span>  

 <span data-ttu-id="e6f96-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6f96-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6f96-113">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="e6f96-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e6f96-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6f96-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6f96-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6f96-115">See also</span></span>

- [<span data-ttu-id="e6f96-116">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="e6f96-116">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="e6f96-117">IInstallReferenceItem (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e6f96-117">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
