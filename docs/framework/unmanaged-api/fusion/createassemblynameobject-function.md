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
ms.openlocfilehash: 5433c49db8e507c6026ab0e87040dd5634ad0808
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430443"
---
# <a name="createassemblynameobject-function"></a><span data-ttu-id="c6745-102">CreateAssemblyNameObject (Función)</span><span class="sxs-lookup"><span data-stu-id="c6745-102">CreateAssemblyNameObject Function</span></span>
<span data-ttu-id="c6745-103">Obtiene un puntero de interfaz a una [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) instancia que representa la identidad única del ensamblado con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="c6745-103">Gets an interface pointer to an [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) instance that represents the unique identity of the assembly with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6745-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c6745-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyNameObject (  
    [out] LPASSEMBLYNAME  *ppAssemblyNameObj,  
    [in]  LPCWSTR         szAssemblyName,  
    [in]  DWORD           dwFlags,  
    [in]  LPVOID          pvReserved  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c6745-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c6745-105">Parameters</span></span>  
 `ppAssemblyNameObj`  
 <span data-ttu-id="c6745-106">[out] El valor devuelto `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="c6745-106">[out] The returned `IAssemblyName`.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="c6745-107">[in] El nombre del ensamblado para el que se va a crear el nuevo `IAssemblyName` instancia.</span><span class="sxs-lookup"><span data-stu-id="c6745-107">[in] The name of the assembly for which to create the new `IAssemblyName` instance.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="c6745-108">[in] Indicadores para pasar al constructor de objetos.</span><span class="sxs-lookup"><span data-stu-id="c6745-108">[in] Flags to pass to the object constructor.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="c6745-109">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="c6745-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="c6745-110">`pvReserved` debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="c6745-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6745-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c6745-111">Requirements</span></span>  
 <span data-ttu-id="c6745-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6745-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6745-113">**Encabezado:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="c6745-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="c6745-114">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c6745-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c6745-115">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6745-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6745-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6745-116">See Also</span></span>  
 [<span data-ttu-id="c6745-117">IAssemblyName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c6745-117">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [<span data-ttu-id="c6745-118">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="c6745-118">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
