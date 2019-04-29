---
title: puntero a la función PFN_CLRDataCreateInstance
ms.date: 03/30/2017
api_name:
- PFN_CLRDataCreateInstance
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- PFN_CLRDataCreateInstance
helpviewer_keywords:
- PFN_CLRDataCreateInstance function pointer [.NET Framework debugging]
ms.assetid: 5c66ac57-d751-4de5-af9f-26ceb949af8b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ff2ddb1e98f3455c6915acf8149f528176228425
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765471"
---
# <a name="pfnclrdatacreateinstance-function-pointer"></a><span data-ttu-id="5c5c2-102">puntero a la función PFN_CLRDataCreateInstance</span><span class="sxs-lookup"><span data-stu-id="5c5c2-102">PFN_CLRDataCreateInstance Function Pointer</span></span>
<span data-ttu-id="5c5c2-103">Señala una función que crea un objeto de interfaz para el elemento de destino especificado.</span><span class="sxs-lookup"><span data-stu-id="5c5c2-103">Points to a function that creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c5c2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5c5c2-104">Syntax</span></span>  
  
```  
typedef HRESULT (STDAPICALLTYPE* PFN_CLRDataCreateInstance) (  
    [in]  REFIID           iid,  
    [in]  ICLRDataTarget  *target,  
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c5c2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5c5c2-105">Parameters</span></span>  
 `iid`  
 <span data-ttu-id="5c5c2-106">[in] El identificador de la interfaz de creación de instancias.</span><span class="sxs-lookup"><span data-stu-id="5c5c2-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="5c5c2-107">[in] Un puntero a un usuario implementa [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) objeto que representa el elemento de destino para el que se va a crear el objeto de interfaz.</span><span class="sxs-lookup"><span data-stu-id="5c5c2-107">[in] A pointer to a user-implemented [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="5c5c2-108">[out] Un puntero a la dirección del objeto de interfaz devuelto.</span><span class="sxs-lookup"><span data-stu-id="5c5c2-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c5c2-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5c5c2-109">Remarks</span></span>  
 <span data-ttu-id="5c5c2-110">La `ICLRDataTarget` objeto es implementado por el sistema de escritura de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="5c5c2-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="5c5c2-111">La implementación depende del tipo de elemento de destino que se va a representar.</span><span class="sxs-lookup"><span data-stu-id="5c5c2-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="5c5c2-112">El elemento de destino puede ser un proceso, volcado de memoria, equipo remoto y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="5c5c2-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c5c2-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5c5c2-113">Requirements</span></span>  
 <span data-ttu-id="5c5c2-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c5c2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c5c2-115">**Encabezado**: ClrData.idl</span><span class="sxs-lookup"><span data-stu-id="5c5c2-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="5c5c2-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c5c2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c5c2-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c5c2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c5c2-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c5c2-118">See also</span></span>

- [<span data-ttu-id="5c5c2-119">Funciones estáticas globales de depuración</span><span class="sxs-lookup"><span data-stu-id="5c5c2-119">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
