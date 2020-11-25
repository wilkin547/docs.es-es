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
ms.openlocfilehash: 9580dd3bc5a7279549e8deadac95d35a33da74f8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724486"
---
# <a name="getassemblyidentityfromfile-function"></a><span data-ttu-id="95aef-102">GetAssemblyIdentityFromFile (Función)</span><span class="sxs-lookup"><span data-stu-id="95aef-102">GetAssemblyIdentityFromFile Function</span></span>

<span data-ttu-id="95aef-103">Obtiene un puntero a un `IUnknown` objeto con el especificado `IID` en el ensamblado en la ruta de acceso de archivo especificada.</span><span class="sxs-lookup"><span data-stu-id="95aef-103">Gets a pointer to an `IUnknown` object with the specified `IID` in the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95aef-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="95aef-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="95aef-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="95aef-105">Parameters</span></span>  

 `pwzFilePath`  
 <span data-ttu-id="95aef-106">de Ruta de acceso válida al ensamblado solicitado.</span><span class="sxs-lookup"><span data-stu-id="95aef-106">[in] A valid path to the requested assembly.</span></span>  
  
 `riid`  
 <span data-ttu-id="95aef-107">de `IID` De la interfaz que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="95aef-107">[in] The `IID` of the interface to return.</span></span>  
  
 `ppIdentity`  
 <span data-ttu-id="95aef-108">enuncia Puntero de interfaz devuelto.</span><span class="sxs-lookup"><span data-stu-id="95aef-108">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95aef-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="95aef-109">Requirements</span></span>  

 <span data-ttu-id="95aef-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95aef-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95aef-111">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="95aef-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="95aef-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95aef-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95aef-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="95aef-113">See also</span></span>

- [<span data-ttu-id="95aef-114">IUnknown</span><span class="sxs-lookup"><span data-stu-id="95aef-114">IUnknown</span></span>](/cpp/atl/iunknown)
- [<span data-ttu-id="95aef-115">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="95aef-115">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
