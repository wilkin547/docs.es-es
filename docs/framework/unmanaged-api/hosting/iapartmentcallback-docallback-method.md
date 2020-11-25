---
title: IApartmentCallback::DoCallback (Método)
ms.date: 03/30/2017
api_name:
- IApartmentCallback.DoCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- DoCallback
helpviewer_keywords:
- IApartmentCallback::DoCallback method [.NET Framework hosting]
- DoCallback method [.NET Framework hosting]
ms.assetid: 8edad30c-30ff-4bee-813c-75525a82fc93
topic_type:
- apiref
ms.openlocfilehash: e3031bf123ff9107b4cebc0723f1be0d423bdaec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721756"
---
# <a name="iapartmentcallbackdocallback-method"></a><span data-ttu-id="445a8-102">IApartmentCallback::DoCallback (Método)</span><span class="sxs-lookup"><span data-stu-id="445a8-102">IApartmentCallback::DoCallback Method</span></span>

<span data-ttu-id="445a8-103">Ejecuta la función especificada dentro de un contenedor.</span><span class="sxs-lookup"><span data-stu-id="445a8-103">Executes the specified function within an apartment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="445a8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="445a8-104">Syntax</span></span>  
  
```cpp  
HRESULT _stdcall DoCallback(  
    [in] SIZE_T pFunc,  
    [in] SIZE_T pData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="445a8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="445a8-105">Parameters</span></span>  

 `pFunc`  
 <span data-ttu-id="445a8-106">de Puntero a la función que se va a ejecutar dentro del apartamento.</span><span class="sxs-lookup"><span data-stu-id="445a8-106">[in] A pointer to the function to be executed within the apartment.</span></span>  
  
 `pData`  
 <span data-ttu-id="445a8-107">de Puntero al argumento de la función.</span><span class="sxs-lookup"><span data-stu-id="445a8-107">[in] A pointer to the function's argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="445a8-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="445a8-108">Requirements</span></span>  

 <span data-ttu-id="445a8-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="445a8-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="445a8-110">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="445a8-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="445a8-111">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="445a8-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="445a8-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="445a8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="445a8-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="445a8-113">See also</span></span>

- [<span data-ttu-id="445a8-114">IApartmentCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="445a8-114">IApartmentCallback Interface</span></span>](iapartmentcallback-interface.md)
