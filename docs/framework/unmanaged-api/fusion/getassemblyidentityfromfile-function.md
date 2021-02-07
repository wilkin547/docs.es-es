---
description: 'Más información acerca de: Getassemblyidentityfromfile ((función)'
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
ms.openlocfilehash: 8832e03182a5652c938404c99115fa8059439d1d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761045"
---
# <a name="getassemblyidentityfromfile-function"></a><span data-ttu-id="66c59-103">GetAssemblyIdentityFromFile (Función)</span><span class="sxs-lookup"><span data-stu-id="66c59-103">GetAssemblyIdentityFromFile Function</span></span>

<span data-ttu-id="66c59-104">Obtiene un puntero a un `IUnknown` objeto con el especificado `IID` en el ensamblado en la ruta de acceso de archivo especificada.</span><span class="sxs-lookup"><span data-stu-id="66c59-104">Gets a pointer to an `IUnknown` object with the specified `IID` in the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66c59-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="66c59-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="66c59-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="66c59-106">Parameters</span></span>  

 `pwzFilePath`  
 <span data-ttu-id="66c59-107">de Ruta de acceso válida al ensamblado solicitado.</span><span class="sxs-lookup"><span data-stu-id="66c59-107">[in] A valid path to the requested assembly.</span></span>  
  
 `riid`  
 <span data-ttu-id="66c59-108">de `IID` De la interfaz que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="66c59-108">[in] The `IID` of the interface to return.</span></span>  
  
 `ppIdentity`  
 <span data-ttu-id="66c59-109">enuncia Puntero de interfaz devuelto.</span><span class="sxs-lookup"><span data-stu-id="66c59-109">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66c59-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="66c59-110">Requirements</span></span>  

 <span data-ttu-id="66c59-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66c59-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66c59-112">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="66c59-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="66c59-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66c59-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66c59-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="66c59-114">See also</span></span>

- [<span data-ttu-id="66c59-115">IUnknown</span><span class="sxs-lookup"><span data-stu-id="66c59-115">IUnknown</span></span>](/cpp/atl/iunknown)
- [<span data-ttu-id="66c59-116">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="66c59-116">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
