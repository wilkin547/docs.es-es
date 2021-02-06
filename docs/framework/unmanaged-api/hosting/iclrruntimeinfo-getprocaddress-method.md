---
description: 'Más información acerca de: ICLRRuntimeInfo:: GetProcAddress (método)'
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
ms.openlocfilehash: 1e5d08ed118930418106b28541b4081d6acad927
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637149"
---
# <a name="iclrruntimeinfogetprocaddress-method"></a><span data-ttu-id="a36c3-103">ICLRRuntimeInfo::GetProcAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="a36c3-103">ICLRRuntimeInfo::GetProcAddress Method</span></span>

<span data-ttu-id="a36c3-104">Obtiene la dirección de una función especificada que se exportó desde el Common Language Runtime (CLR) asociado a esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="a36c3-104">Gets the address of a specified function that was exported from the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="a36c3-105">Este método reemplaza a la función [GetRealProcAddress (](getrealprocaddress-function.md) .</span><span class="sxs-lookup"><span data-stu-id="a36c3-105">This method supersedes the [GetRealProcAddress](getrealprocaddress-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a36c3-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a36c3-106">Syntax</span></span>  
  
```cpp  
HRESULT GetProcAddress(  
     [in]  LPCSTR pszProcName,  
     [out, retval] LPVOID *ppProc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a36c3-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a36c3-107">Parameters</span></span>  

 `pszProcName`  
 <span data-ttu-id="a36c3-108">de Nombre de la función exportada.</span><span class="sxs-lookup"><span data-stu-id="a36c3-108">[in] The name of the exported function.</span></span>  
  
 `ppProc`  
 <span data-ttu-id="a36c3-109">enuncia Dirección de la función exportada.</span><span class="sxs-lookup"><span data-stu-id="a36c3-109">[out] The address of the exported function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a36c3-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a36c3-110">Return Value</span></span>  

 <span data-ttu-id="a36c3-111">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="a36c3-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a36c3-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a36c3-112">HRESULT</span></span>|<span data-ttu-id="a36c3-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="a36c3-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a36c3-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="a36c3-114">S_OK</span></span>|<span data-ttu-id="a36c3-115">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="a36c3-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="a36c3-116">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="a36c3-116">E_POINTER</span></span>|<span data-ttu-id="a36c3-117">`pszProcName` o `ppProc` es null.</span><span class="sxs-lookup"><span data-stu-id="a36c3-117">`pszProcName` or `ppProc` is null.</span></span>|  
|<span data-ttu-id="a36c3-118">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="a36c3-118">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="a36c3-119">La función especificada no es una función exportada.</span><span class="sxs-lookup"><span data-stu-id="a36c3-119">The specified function is not an exported function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a36c3-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a36c3-120">Remarks</span></span>  

 <span data-ttu-id="a36c3-121">Este método hace que el CLR se cargue pero no se inicialice.</span><span class="sxs-lookup"><span data-stu-id="a36c3-121">This method causes the CLR to be loaded but not initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a36c3-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a36c3-122">Requirements</span></span>  

 <span data-ttu-id="a36c3-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a36c3-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a36c3-124">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="a36c3-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a36c3-125">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a36c3-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a36c3-126">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a36c3-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a36c3-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="a36c3-127">See also</span></span>

- [<span data-ttu-id="a36c3-128">ICLRRuntimeInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a36c3-128">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="a36c3-129">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="a36c3-129">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="a36c3-130">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="a36c3-130">Hosting</span></span>](index.md)
