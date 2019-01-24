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
ms.openlocfilehash: 2aed89008dd2fa86b38f243c8e7cca1bdda901e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54497779"
---
# <a name="iinstallreferenceenum-interface"></a><span data-ttu-id="4325c-102">IInstallReferenceEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4325c-102">IInstallReferenceEnum Interface</span></span>
<span data-ttu-id="4325c-103">Representa un enumerador para los ensamblados instalados en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="4325c-103">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4325c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4325c-104">Syntax</span></span>  
  
```  
interface IInstallReferenceEnum : IUnknown {  
    HRESULT GetNextInstallReferenceItem (  
        [out] IInstallReferenceItem **ppRefItem,  
        [in]  DWORD dwFlags,  
        [in]  LPVOID pvReserved  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4325c-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="4325c-105">Methods</span></span>  
  
|<span data-ttu-id="4325c-106">Método</span><span class="sxs-lookup"><span data-stu-id="4325c-106">Method</span></span>|<span data-ttu-id="4325c-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="4325c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4325c-108">GetNextInstallReferenceItem (método)</span><span class="sxs-lookup"><span data-stu-id="4325c-108">GetNextInstallReferenceItem Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-getnextinstallreferenceitem-method.md)|<span data-ttu-id="4325c-109">Obtiene un puntero a la siguiente `IInstallReferenceItem` incluidos en este `IInstallReferenceEnum`.</span><span class="sxs-lookup"><span data-stu-id="4325c-109">Gets a pointer to the next `IInstallReferenceItem` contained in this `IInstallReferenceEnum`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4325c-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4325c-110">Requirements</span></span>  
 <span data-ttu-id="4325c-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4325c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4325c-112">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="4325c-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="4325c-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4325c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4325c-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="4325c-114">See also</span></span>
- [<span data-ttu-id="4325c-115">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="4325c-115">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="4325c-116">IInstallReferenceItem (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4325c-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
