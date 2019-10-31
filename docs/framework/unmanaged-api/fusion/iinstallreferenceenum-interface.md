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
ms.openlocfilehash: d3f7c24b4bd373924c44dbc0490c890e7f1322bd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131732"
---
# <a name="iinstallreferenceenum-interface"></a><span data-ttu-id="f3e5c-102">IInstallReferenceEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f3e5c-102">IInstallReferenceEnum Interface</span></span>
<span data-ttu-id="f3e5c-103">Representa un enumerador para los ensamblados a los que se hace referencia instalados en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="f3e5c-103">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3e5c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f3e5c-104">Syntax</span></span>  
  
```cpp  
interface IInstallReferenceEnum : IUnknown {  
    HRESULT GetNextInstallReferenceItem (  
        [out] IInstallReferenceItem **ppRefItem,  
        [in]  DWORD dwFlags,  
        [in]  LPVOID pvReserved  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f3e5c-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="f3e5c-105">Methods</span></span>  
  
|<span data-ttu-id="f3e5c-106">Método</span><span class="sxs-lookup"><span data-stu-id="f3e5c-106">Method</span></span>|<span data-ttu-id="f3e5c-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3e5c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f3e5c-108">GetNextInstallReferenceItem (método)</span><span class="sxs-lookup"><span data-stu-id="f3e5c-108">GetNextInstallReferenceItem Method</span></span>](iinstallreferenceenum-getnextinstallreferenceitem-method.md)|<span data-ttu-id="f3e5c-109">Obtiene un puntero al `IInstallReferenceItem` siguiente contenido en esta `IInstallReferenceEnum`.</span><span class="sxs-lookup"><span data-stu-id="f3e5c-109">Gets a pointer to the next `IInstallReferenceItem` contained in this `IInstallReferenceEnum`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f3e5c-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f3e5c-110">Requirements</span></span>  
 <span data-ttu-id="f3e5c-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3e5c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3e5c-112">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="f3e5c-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="f3e5c-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3e5c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3e5c-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3e5c-114">See also</span></span>

- [<span data-ttu-id="f3e5c-115">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="f3e5c-115">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="f3e5c-116">IInstallReferenceItem (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f3e5c-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
