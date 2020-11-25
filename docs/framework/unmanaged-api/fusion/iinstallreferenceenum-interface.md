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
ms.openlocfilehash: f56a9049cd4b503124abe9dd4866dc91779e268e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721070"
---
# <a name="iinstallreferenceenum-interface"></a><span data-ttu-id="66278-102">IInstallReferenceEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="66278-102">IInstallReferenceEnum Interface</span></span>

<span data-ttu-id="66278-103">Representa un enumerador para los ensamblados a los que se hace referencia instalados en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="66278-103">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66278-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="66278-104">Syntax</span></span>  
  
```cpp  
interface IInstallReferenceEnum : IUnknown {  
    HRESULT GetNextInstallReferenceItem (  
        [out] IInstallReferenceItem **ppRefItem,  
        [in]  DWORD dwFlags,  
        [in]  LPVOID pvReserved  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="66278-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="66278-105">Methods</span></span>  
  
|<span data-ttu-id="66278-106">Método</span><span class="sxs-lookup"><span data-stu-id="66278-106">Method</span></span>|<span data-ttu-id="66278-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="66278-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="66278-108">Método GetNextInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="66278-108">GetNextInstallReferenceItem Method</span></span>](iinstallreferenceenum-getnextinstallreferenceitem-method.md)|<span data-ttu-id="66278-109">Obtiene un puntero al siguiente `IInstallReferenceItem` contenido en este `IInstallReferenceEnum` .</span><span class="sxs-lookup"><span data-stu-id="66278-109">Gets a pointer to the next `IInstallReferenceItem` contained in this `IInstallReferenceEnum`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="66278-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="66278-110">Requirements</span></span>  

 <span data-ttu-id="66278-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66278-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66278-112">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="66278-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="66278-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66278-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66278-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="66278-114">See also</span></span>

- [<span data-ttu-id="66278-115">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="66278-115">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="66278-116">IInstallReferenceItem (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="66278-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
