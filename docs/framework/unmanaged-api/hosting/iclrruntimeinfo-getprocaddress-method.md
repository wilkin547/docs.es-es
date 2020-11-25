---
title: ICLRRuntimeInfo::GetProcAddress (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetProcAddress
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetProcAddress
helpviewer_keywords:
- GetProcAddress method [.NET Framework hosting]
- ICLRRuntimeInfo::GetProcAddress method [.NET Framework hosting]
ms.assetid: a7732bfc-689a-4926-88fd-4f81e6f9ed78
topic_type:
- apiref
ms.openlocfilehash: 028cfd51a713d8598598566a5b1edcf3fc70ecfc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732065"
---
# <a name="iclrruntimeinfogetprocaddress-method"></a><span data-ttu-id="d47e0-102">ICLRRuntimeInfo::GetProcAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="d47e0-102">ICLRRuntimeInfo::GetProcAddress Method</span></span>

<span data-ttu-id="d47e0-103">Obtiene la dirección de una función especificada que se exportó desde el Common Language Runtime (CLR) asociado a esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="d47e0-103">Gets the address of a specified function that was exported from the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="d47e0-104">Este método reemplaza a la función [GetRealProcAddress (](getrealprocaddress-function.md) .</span><span class="sxs-lookup"><span data-stu-id="d47e0-104">This method supersedes the [GetRealProcAddress](getrealprocaddress-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d47e0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d47e0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetProcAddress(  
     [in]  LPCSTR pszProcName,  
     [out, retval] LPVOID *ppProc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d47e0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d47e0-106">Parameters</span></span>  

 `pszProcName`  
 <span data-ttu-id="d47e0-107">de Nombre de la función exportada.</span><span class="sxs-lookup"><span data-stu-id="d47e0-107">[in] The name of the exported function.</span></span>  
  
 `ppProc`  
 <span data-ttu-id="d47e0-108">enuncia Dirección de la función exportada.</span><span class="sxs-lookup"><span data-stu-id="d47e0-108">[out] The address of the exported function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d47e0-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d47e0-109">Return Value</span></span>  

 <span data-ttu-id="d47e0-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="d47e0-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="d47e0-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d47e0-111">HRESULT</span></span>|<span data-ttu-id="d47e0-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="d47e0-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d47e0-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="d47e0-113">S_OK</span></span>|<span data-ttu-id="d47e0-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="d47e0-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="d47e0-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="d47e0-115">E_POINTER</span></span>|<span data-ttu-id="d47e0-116">`pszProcName` o `ppProc` es null.</span><span class="sxs-lookup"><span data-stu-id="d47e0-116">`pszProcName` or `ppProc` is null.</span></span>|  
|<span data-ttu-id="d47e0-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="d47e0-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="d47e0-118">La función especificada no es una función exportada.</span><span class="sxs-lookup"><span data-stu-id="d47e0-118">The specified function is not an exported function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d47e0-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d47e0-119">Remarks</span></span>  

 <span data-ttu-id="d47e0-120">Este método hace que el CLR se cargue pero no se inicialice.</span><span class="sxs-lookup"><span data-stu-id="d47e0-120">This method causes the CLR to be loaded but not initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d47e0-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d47e0-121">Requirements</span></span>  

 <span data-ttu-id="d47e0-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d47e0-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d47e0-123">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="d47e0-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d47e0-124">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d47e0-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d47e0-125">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d47e0-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d47e0-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d47e0-126">See also</span></span>

- [<span data-ttu-id="d47e0-127">ICLRRuntimeInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d47e0-127">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="d47e0-128">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="d47e0-128">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="d47e0-129">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="d47e0-129">Hosting</span></span>](index.md)
