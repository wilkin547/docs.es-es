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
ms.openlocfilehash: 50ec5a23db4d2460480bcc3e463ecd88e7470bde
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134533"
---
# <a name="getassemblyidentityfromfile-function"></a><span data-ttu-id="59fa0-102">GetAssemblyIdentityFromFile (Función)</span><span class="sxs-lookup"><span data-stu-id="59fa0-102">GetAssemblyIdentityFromFile Function</span></span>
<span data-ttu-id="59fa0-103">Obtiene un puntero a un objeto `IUnknown` con el `IID` especificado en el ensamblado en la ruta de acceso de archivo especificada.</span><span class="sxs-lookup"><span data-stu-id="59fa0-103">Gets a pointer to an `IUnknown` object with the specified `IID` in the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59fa0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="59fa0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="59fa0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="59fa0-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="59fa0-106">de Ruta de acceso válida al ensamblado solicitado.</span><span class="sxs-lookup"><span data-stu-id="59fa0-106">[in] A valid path to the requested assembly.</span></span>  
  
 `riid`  
 <span data-ttu-id="59fa0-107">de `IID` de la interfaz que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="59fa0-107">[in] The `IID` of the interface to return.</span></span>  
  
 `ppIdentity`  
 <span data-ttu-id="59fa0-108">enuncia Puntero de interfaz devuelto.</span><span class="sxs-lookup"><span data-stu-id="59fa0-108">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59fa0-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="59fa0-109">Requirements</span></span>  
 <span data-ttu-id="59fa0-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59fa0-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59fa0-111">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="59fa0-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="59fa0-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59fa0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59fa0-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="59fa0-113">See also</span></span>

- [<span data-ttu-id="59fa0-114">IUnknown</span><span class="sxs-lookup"><span data-stu-id="59fa0-114">IUnknown</span></span>](/cpp/atl/iunknown)
- [<span data-ttu-id="59fa0-115">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="59fa0-115">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
