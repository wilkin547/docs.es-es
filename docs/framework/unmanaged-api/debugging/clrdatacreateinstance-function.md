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
ms.openlocfilehash: 73a4a8a2fc737bbf4b49ca859f0549ca7efd54a2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701286"
---
# <a name="clrdatacreateinstance-function"></a><span data-ttu-id="f559a-102">CLRDataCreateInstance (Función)</span><span class="sxs-lookup"><span data-stu-id="f559a-102">CLRDataCreateInstance Function</span></span>
<span data-ttu-id="f559a-103">Crea un objeto de interfaz para el elemento de destino especificado.</span><span class="sxs-lookup"><span data-stu-id="f559a-103">Creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f559a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f559a-104">Syntax</span></span>  
  
```  
HRESULT CLRDataCreateInstance (  
    [in]  REFIID           iid,   
    [in]  ICLRDataTarget  *target,   
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f559a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f559a-105">Parameters</span></span>  
 `iid`  
 <span data-ttu-id="f559a-106">[in] El identificador de la interfaz de creación de instancias.</span><span class="sxs-lookup"><span data-stu-id="f559a-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="f559a-107">[in] Un puntero a un usuario implementa [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) objeto que representa el elemento de destino para el que se va a crear el objeto de interfaz.</span><span class="sxs-lookup"><span data-stu-id="f559a-107">[in] A pointer to a user-implemented [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="f559a-108">[out] Un puntero a la dirección del objeto de interfaz devuelto.</span><span class="sxs-lookup"><span data-stu-id="f559a-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f559a-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f559a-109">Remarks</span></span>  
 <span data-ttu-id="f559a-110">La `ICLRDataTarget` objeto es implementado por el sistema de escritura de la aplicación de depuración.</span><span class="sxs-lookup"><span data-stu-id="f559a-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="f559a-111">La implementación depende del tipo de elemento de destino que se va a representar.</span><span class="sxs-lookup"><span data-stu-id="f559a-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="f559a-112">El elemento de destino puede ser un proceso, volcado de memoria, equipo remoto y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="f559a-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f559a-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f559a-113">Requirements</span></span>  
 <span data-ttu-id="f559a-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f559a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f559a-115">**Encabezado**: ClrData.idl</span><span class="sxs-lookup"><span data-stu-id="f559a-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="f559a-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f559a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f559a-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f559a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f559a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f559a-118">See also</span></span>

- [<span data-ttu-id="f559a-119">Funciones estáticas globales de depuración</span><span class="sxs-lookup"><span data-stu-id="f559a-119">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
