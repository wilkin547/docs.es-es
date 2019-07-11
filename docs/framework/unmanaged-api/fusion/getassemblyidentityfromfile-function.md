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
ms.openlocfilehash: 581c675cfb69503e6366471a469ffed1a2d13b1a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745232"
---
# <a name="getassemblyidentityfromfile-function"></a><span data-ttu-id="d53f5-102">GetAssemblyIdentityFromFile (Función)</span><span class="sxs-lookup"><span data-stu-id="d53f5-102">GetAssemblyIdentityFromFile Function</span></span>
<span data-ttu-id="d53f5-103">Obtiene un puntero a un `IUnknown` objeto con los valores especificados `IID` en el ensamblado en la ruta de acceso de archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="d53f5-103">Gets a pointer to an `IUnknown` object with the specified `IID` in the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d53f5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d53f5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="d53f5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d53f5-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="d53f5-106">[in] Una ruta de acceso válida para el ensamblado solicitado.</span><span class="sxs-lookup"><span data-stu-id="d53f5-106">[in] A valid path to the requested assembly.</span></span>  
  
 `riid`  
 <span data-ttu-id="d53f5-107">[in] El `IID` de la interfaz para devolver.</span><span class="sxs-lookup"><span data-stu-id="d53f5-107">[in] The `IID` of the interface to return.</span></span>  
  
 `ppIdentity`  
 <span data-ttu-id="d53f5-108">[out] El puntero de interfaz devuelto.</span><span class="sxs-lookup"><span data-stu-id="d53f5-108">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d53f5-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d53f5-109">Requirements</span></span>  
 <span data-ttu-id="d53f5-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d53f5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d53f5-111">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="d53f5-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="d53f5-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d53f5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d53f5-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="d53f5-113">See also</span></span>

- [<span data-ttu-id="d53f5-114">IUnknown</span><span class="sxs-lookup"><span data-stu-id="d53f5-114">IUnknown</span></span>](/cpp/atl/iunknown)
- [<span data-ttu-id="d53f5-115">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="d53f5-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
