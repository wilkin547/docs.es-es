---
title: ICorPublishProcess::EnumAppDomains (Método)
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.EnumAppDomains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::EnumAppDomains
helpviewer_keywords:
- EnumAppDomains method [.NET Framework debugging]
- ICorPublishProcess::EnumAppDomains method [.NET Framework debugging]
ms.assetid: 7da621fc-e7d0-4c00-9439-5c93619d7414
topic_type:
- apiref
ms.openlocfilehash: 2acf8fb507ab617e066a31c9c2657b1ef0d18e47
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95693286"
---
# <a name="icorpublishprocessenumappdomains-method"></a><span data-ttu-id="811c8-102">ICorPublishProcess::EnumAppDomains (Método)</span><span class="sxs-lookup"><span data-stu-id="811c8-102">ICorPublishProcess::EnumAppDomains Method</span></span>

<span data-ttu-id="811c8-103">Obtiene un enumerador para los dominios de aplicación en el proceso al que hace referencia esta [ICorPublishProcess](icorpublishprocess-interface.md).</span><span class="sxs-lookup"><span data-stu-id="811c8-103">Gets an enumerator for the application domains in the process that is referenced by this [ICorPublishProcess](icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="811c8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="811c8-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumAppDomains (  
    [out] ICorPublishAppDomainEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="811c8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="811c8-105">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="811c8-106">enuncia Un puntero a la dirección de una instancia de [ICorPublishAppDomainEnum (](icorpublishappdomainenum-interface.md) que permite la iteración a través de la colección de dominios de aplicación en este proceso.</span><span class="sxs-lookup"><span data-stu-id="811c8-106">[out] A pointer to the address of an [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) instance that allows iteration through the collection of application domains in this process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="811c8-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="811c8-107">Remarks</span></span>  

 <span data-ttu-id="811c8-108">La lista de dominios de aplicación se basa en una instantánea de los dominios de aplicación que existen cuando `EnumAppDomains` se llama al método.</span><span class="sxs-lookup"><span data-stu-id="811c8-108">The list of application domains is based on a snapshot of the application domains that exist when the `EnumAppDomains` method is called.</span></span> <span data-ttu-id="811c8-109">Este método se puede llamar más de una vez para crear una nueva lista actualizada.</span><span class="sxs-lookup"><span data-stu-id="811c8-109">This method may be called more than once to create a new up-to-date list.</span></span> <span data-ttu-id="811c8-110">Las llamadas subsiguientes de este método no afectarán a las listas existentes.</span><span class="sxs-lookup"><span data-stu-id="811c8-110">Existing lists will not be affected by subsequent calls of this method.</span></span>  
  
 <span data-ttu-id="811c8-111">Si se ha finalizado el proceso, `EnumAppDomains` se producirá un error HRESULT con el valor CORDBG_E_PROCESS_TERMINATED.</span><span class="sxs-lookup"><span data-stu-id="811c8-111">If the process has been terminated, `EnumAppDomains` will fail with an HRESULT value of CORDBG_E_PROCESS_TERMINATED.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="811c8-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="811c8-112">Requirements</span></span>  

 <span data-ttu-id="811c8-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="811c8-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="811c8-114">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="811c8-114">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="811c8-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="811c8-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="811c8-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="811c8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="811c8-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="811c8-117">See also</span></span>

- [<span data-ttu-id="811c8-118">ICorPublishProcess (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="811c8-118">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
