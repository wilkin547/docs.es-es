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
ms.openlocfilehash: 1412231b53763ce8e6c2400497396d2f178d8e7a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54666298"
---
# <a name="createassemblynameobject-function"></a><span data-ttu-id="fef37-102">CreateAssemblyNameObject (Función)</span><span class="sxs-lookup"><span data-stu-id="fef37-102">CreateAssemblyNameObject Function</span></span>
<span data-ttu-id="fef37-103">Obtiene un puntero de interfaz a un [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) instancia que representa la identidad única del ensamblado con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="fef37-103">Gets an interface pointer to an [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) instance that represents the unique identity of the assembly with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fef37-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fef37-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyNameObject (  
    [out] LPASSEMBLYNAME  *ppAssemblyNameObj,  
    [in]  LPCWSTR         szAssemblyName,  
    [in]  DWORD           dwFlags,  
    [in]  LPVOID          pvReserved  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fef37-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fef37-105">Parameters</span></span>  
 `ppAssemblyNameObj`  
 <span data-ttu-id="fef37-106">[out] El valor devuelto `IAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="fef37-106">[out] The returned `IAssemblyName`.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="fef37-107">[in] El nombre del ensamblado para el que se va a crear el nuevo `IAssemblyName` instancia.</span><span class="sxs-lookup"><span data-stu-id="fef37-107">[in] The name of the assembly for which to create the new `IAssemblyName` instance.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="fef37-108">[in] Indicadores para pasar al constructor de objetos.</span><span class="sxs-lookup"><span data-stu-id="fef37-108">[in] Flags to pass to the object constructor.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="fef37-109">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="fef37-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="fef37-110">`pvReserved` debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="fef37-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fef37-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fef37-111">Requirements</span></span>  
 <span data-ttu-id="fef37-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fef37-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fef37-113">**Encabezado**: Fusion.h</span><span class="sxs-lookup"><span data-stu-id="fef37-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="fef37-114">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fef37-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fef37-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fef37-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fef37-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="fef37-116">See also</span></span>
- [<span data-ttu-id="fef37-117">IAssemblyName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fef37-117">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="fef37-118">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="fef37-118">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
