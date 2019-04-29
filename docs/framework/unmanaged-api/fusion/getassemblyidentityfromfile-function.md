---
title: GetAssemblyIdentityFromFile (Función)
ms.date: 03/30/2017
api_name:
- GetAssemblyIdentityFromFile
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- COM
f1_keywords:
- GetAssemblyIdentityFromFile
helpviewer_keywords:
- GetAssemblyIdentityFromFile function [.NET Framework fusion]
ms.assetid: 2c32da53-76c7-4048-84d0-d05207333004
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4f5dd25ec2a6a1b0b5d6266c3d8e728bd128a9ed
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697763"
---
# <a name="getassemblyidentityfromfile-function"></a><span data-ttu-id="3e510-102">GetAssemblyIdentityFromFile (Función)</span><span class="sxs-lookup"><span data-stu-id="3e510-102">GetAssemblyIdentityFromFile Function</span></span>
<span data-ttu-id="3e510-103">Obtiene un puntero a un `IUnknown` objeto con los valores especificados `IID` en el ensamblado en la ruta de acceso de archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="3e510-103">Gets a pointer to an `IUnknown` object with the specified `IID` in the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e510-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3e510-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e510-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3e510-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="3e510-106">[in] Una ruta de acceso válida para el ensamblado solicitado.</span><span class="sxs-lookup"><span data-stu-id="3e510-106">[in] A valid path to the requested assembly.</span></span>  
  
 `riid`  
 <span data-ttu-id="3e510-107">[in] El `IID` de la interfaz para devolver.</span><span class="sxs-lookup"><span data-stu-id="3e510-107">[in] The `IID` of the interface to return.</span></span>  
  
 `ppIdentity`  
 <span data-ttu-id="3e510-108">[out] El puntero de interfaz devuelto.</span><span class="sxs-lookup"><span data-stu-id="3e510-108">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e510-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3e510-109">Requirements</span></span>  
 <span data-ttu-id="3e510-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e510-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e510-111">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="3e510-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="3e510-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e510-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e510-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e510-113">See also</span></span>

- [<span data-ttu-id="3e510-114">IUnknown</span><span class="sxs-lookup"><span data-stu-id="3e510-114">IUnknown</span></span>](/cpp/atl/iunknown)
- [<span data-ttu-id="3e510-115">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="3e510-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
