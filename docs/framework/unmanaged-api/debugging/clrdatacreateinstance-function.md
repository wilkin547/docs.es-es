---
title: CLRDataCreateInstance (Función)
ms.date: 03/30/2017
api_name:
- CLRDataCreateInstance
api_location:
- mscordbi.dll
- mscordacwks.dll
api_type:
- COM
f1_keywords:
- CLRDataCreateInstance
helpviewer_keywords:
- CLRDataCreateInstance function [.NET Framework debugging]
ms.assetid: 440bad90-5a88-45e7-9157-4596801d8d19
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5a839eb2edd36dc726c819a819fd4d427fbaea40
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740994"
---
# <a name="clrdatacreateinstance-function"></a><span data-ttu-id="de203-102">CLRDataCreateInstance (Función)</span><span class="sxs-lookup"><span data-stu-id="de203-102">CLRDataCreateInstance Function</span></span>
<span data-ttu-id="de203-103">Crea un objeto de interfaz para el elemento de destino especificado.</span><span class="sxs-lookup"><span data-stu-id="de203-103">Creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de203-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="de203-104">Syntax</span></span>  
  
```cpp  
HRESULT CLRDataCreateInstance (  
    [in]  REFIID           iid,   
    [in]  ICLRDataTarget  *target,   
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de203-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="de203-105">Parameters</span></span>  
 `iid`  
 <span data-ttu-id="de203-106">[in] El identificador de la interfaz de creación de instancias.</span><span class="sxs-lookup"><span data-stu-id="de203-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="de203-107">[in] Un puntero a un usuario implementa [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) objeto que representa el elemento de destino para el que se va a crear el objeto de interfaz.</span><span class="sxs-lookup"><span data-stu-id="de203-107">[in] A pointer to a user-implemented [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="de203-108">[out] Un puntero a la dirección del objeto de interfaz devuelto.</span><span class="sxs-lookup"><span data-stu-id="de203-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de203-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="de203-109">Remarks</span></span>  
 <span data-ttu-id="de203-110">La `ICLRDataTarget` objeto es implementado por el sistema de escritura de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="de203-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="de203-111">La implementación depende del tipo de elemento de destino que se va a representar.</span><span class="sxs-lookup"><span data-stu-id="de203-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="de203-112">El elemento de destino puede ser un proceso, volcado de memoria, equipo remoto y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="de203-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de203-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="de203-113">Requirements</span></span>  
 <span data-ttu-id="de203-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de203-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de203-115">**Encabezado**: ClrData.idl</span><span class="sxs-lookup"><span data-stu-id="de203-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="de203-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de203-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de203-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de203-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de203-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="de203-118">See also</span></span>

- [<span data-ttu-id="de203-119">Funciones estáticas globales de depuración</span><span class="sxs-lookup"><span data-stu-id="de203-119">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
