---
title: "LoadLibraryShim (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- LoadLibraryShim
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- LoadLibraryShim
helpviewer_keywords:
- LoadLibraryShim function [.NET Framework hosting]
ms.assetid: 30931874-4d0e-4df1-b3d1-e425b50655d1
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5b8fe8413d0eff332e60508a083f03574e58d7bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="loadlibraryshim-function"></a><span data-ttu-id="d25ba-102">LoadLibraryShim (Función)</span><span class="sxs-lookup"><span data-stu-id="d25ba-102">LoadLibraryShim Function</span></span>
<span data-ttu-id="d25ba-103">Carga la versión especificada de un archivo DLL que se incluye en el paquete redistribuible de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d25ba-103">Loads a specified version of a DLL that is included in the .NET Framework redistributable package.</span></span>  
  
 <span data-ttu-id="d25ba-104">Esta función está desusada en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d25ba-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="d25ba-105">Use la [ICLRRuntimeInfo:: LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="d25ba-105">Use the [ICLRRuntimeInfo::LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d25ba-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d25ba-106">Syntax</span></span>  
  
```  
HRESULT LoadLibraryShim (  
    [in]  LPCWSTR  szDllName,  
    [in]  LPCWSTR  szVersion,  
          LPVOID   pvReserved,  
    [out] HMODULE *phModDll  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d25ba-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d25ba-107">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="d25ba-108">[in] Una cadena terminada en cero que representa el nombre de la DLL que se va a cargar desde la biblioteca de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d25ba-108">[in] A zero-terminated string that represents the name of the DLL to be loaded from the .NET Framework library.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="d25ba-109">[in] Una cadena terminada en cero que representa la versión de la DLL que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="d25ba-109">[in] A zero-terminated string that represents the version of the DLL to be loaded.</span></span> <span data-ttu-id="d25ba-110">Si `szVersion` es null, la versión seleccionada para la carga es la versión más reciente de la DLL especificada que es menor que la versión 4.</span><span class="sxs-lookup"><span data-stu-id="d25ba-110">If `szVersion` is null, the version selected for loading is the latest version of the specified DLL that is less than version 4.</span></span> <span data-ttu-id="d25ba-111">Es decir, todas las versiones iguales o mayores que la versión 4 se omiten si `szVersion` es null, y si no está instalada ninguna versión menor que la versión 4, no puede cargar el archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="d25ba-111">That is, all versions equal to or greater than version 4 are ignored if `szVersion` is null, and if no version less than version 4 is installed, the DLL fails to load.</span></span> <span data-ttu-id="d25ba-112">Esto sirve para asegurarse de esa instalación de la [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] no afecta a las aplicaciones existentes o componentes.</span><span class="sxs-lookup"><span data-stu-id="d25ba-112">This is to ensure that installation of the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] does not affect pre-existing applications or components.</span></span> <span data-ttu-id="d25ba-113">Vea la entrada [SxS en proceso y el inicio rápido de migración](http://go.microsoft.com/fwlink/?LinkId=200329) en el blog del equipo CLR.</span><span class="sxs-lookup"><span data-stu-id="d25ba-113">See the entry [In-Proc SxS and Migration Quick Start](http://go.microsoft.com/fwlink/?LinkId=200329) in the CLR team blog.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="d25ba-114">Reservado para un uso futuro.</span><span class="sxs-lookup"><span data-stu-id="d25ba-114">Reserved for future use.</span></span>  
  
 `phModDll`  
 <span data-ttu-id="d25ba-115">[out] Un puntero al identificador del módulo.</span><span class="sxs-lookup"><span data-stu-id="d25ba-115">[out] A pointer to the handle of the module.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d25ba-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d25ba-116">Return Value</span></span>  
 <span data-ttu-id="d25ba-117">Este método devuelve códigos de error estándar de modelo de objetos componentes (COM), como se define en WinError.h, además de los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="d25ba-117">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="d25ba-118">Código devuelto</span><span class="sxs-lookup"><span data-stu-id="d25ba-118">Return code</span></span>|<span data-ttu-id="d25ba-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="d25ba-119">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="d25ba-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="d25ba-120">S_OK</span></span>|<span data-ttu-id="d25ba-121">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="d25ba-121">The method completed successfully.</span></span>|  
|<span data-ttu-id="d25ba-122">CLR_E_SHIM_RUNTIMELOAD</span><span class="sxs-lookup"><span data-stu-id="d25ba-122">CLR_E_SHIM_RUNTIMELOAD</span></span>|<span data-ttu-id="d25ba-123">Cargar `szDllName` requiere cargar common language runtime (CLR) y la versión necesaria de CLR no se puede cargar.</span><span class="sxs-lookup"><span data-stu-id="d25ba-123">Loading `szDllName` requires loading the common language runtime (CLR), and the necessary version of the CLR cannot be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d25ba-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d25ba-124">Remarks</span></span>  
 <span data-ttu-id="d25ba-125">Esta función se usa para cargar archivos DLL que se incluyen en el paquete redistribuible de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d25ba-125">This function is used to load DLLs that are included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="d25ba-126">No carga las DLL generadas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="d25ba-126">It does not load user-generated DLLs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d25ba-127">A partir de la versión 2.0 de .NET Framework, carga Fusion.dll hace que el CLR que se va a cargar.</span><span class="sxs-lookup"><span data-stu-id="d25ba-127">Beginning with the .NET Framework version 2.0, loading Fusion.dll causes the CLR to be loaded.</span></span> <span data-ttu-id="d25ba-128">Esto es porque las funciones de Fusion.dll ahora son contenedores cuyas implementaciones se proporcionan con el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d25ba-128">This is because the functions in Fusion.dll are now wrappers whose implementations are provided by the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d25ba-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d25ba-129">Requirements</span></span>  
 <span data-ttu-id="d25ba-130">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d25ba-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d25ba-131">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d25ba-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d25ba-132">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d25ba-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d25ba-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="d25ba-133">See Also</span></span>  
 [<span data-ttu-id="d25ba-134">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="d25ba-134">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
