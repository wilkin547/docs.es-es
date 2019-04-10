---
title: CreateAssemblyNameObject (Función)
ms.date: 03/30/2017
api_name:
- CreateAssemblyNameObject
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyNameObject
helpviewer_keywords:
- CreateAssemblyNameObject function [.NET Framework fusion]
ms.assetid: 55c8b41e-fbe4-4ae0-aa29-68fbb2311691
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd8609bedcea28c1cb8559d378b5e171f3ad568e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225006"
---
# <a name="createassemblynameobject-function"></a><span data-ttu-id="e0ae6-102">CreateAssemblyNameObject (Función)</span><span class="sxs-lookup"><span data-stu-id="e0ae6-102">CreateAssemblyNameObject Function</span></span>
<span data-ttu-id="e0ae6-103">Obtiene un puntero de interfaz a un [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) instancia que representa la identidad única del ensamblado con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="e0ae6-103">Gets an interface pointer to an [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) instance that represents the unique identity of the assembly with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0ae6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e0ae6-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyNameObject (  
    [out] LPASSEMBLYNAME  *ppAssemblyNameObj,  
    [in]  LPCWSTR         szAssemblyName,  
    [in]  DWORD           dwFlags,  
    [in]  LPVOID          pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0ae6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e0ae6-105">Parameters</span></span>  
 `ppAssemblyNameObj`  
 <span data-ttu-id="e0ae6-106">[out] El valor devuelto `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="e0ae6-106">[out] The returned `IAssemblyName`.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="e0ae6-107">[in] El nombre del ensamblado para el que se va a crear el nuevo `IAssemblyName` instancia.</span><span class="sxs-lookup"><span data-stu-id="e0ae6-107">[in] The name of the assembly for which to create the new `IAssemblyName` instance.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="e0ae6-108">[in] Indicadores para pasar al constructor de objetos.</span><span class="sxs-lookup"><span data-stu-id="e0ae6-108">[in] Flags to pass to the object constructor.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="e0ae6-109">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="e0ae6-109">[in] Reserved for future extensibility.</span></span> `pvReserved` <span data-ttu-id="e0ae6-110">debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="e0ae6-110">must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0ae6-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e0ae6-111">Requirements</span></span>  
 <span data-ttu-id="e0ae6-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0ae6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0ae6-113">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="e0ae6-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e0ae6-114">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e0ae6-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="e0ae6-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e0ae6-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e0ae6-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0ae6-116">See also</span></span>

- [<span data-ttu-id="e0ae6-117">IAssemblyName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e0ae6-117">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="e0ae6-118">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="e0ae6-118">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
