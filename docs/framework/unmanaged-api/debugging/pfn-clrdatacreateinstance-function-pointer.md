---
description: 'Más información acerca de: PFN_CLRDataCreateInstance puntero a función'
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
ms.openlocfilehash: fc048f840084eff0270944d3190ccbb153bf22d8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800635"
---
# <a name="pfn_clrdatacreateinstance-function-pointer"></a><span data-ttu-id="964f0-103">puntero a la función PFN_CLRDataCreateInstance</span><span class="sxs-lookup"><span data-stu-id="964f0-103">PFN_CLRDataCreateInstance Function Pointer</span></span>

<span data-ttu-id="964f0-104">Apunta a una función que crea un objeto de interfaz para el elemento de destino especificado.</span><span class="sxs-lookup"><span data-stu-id="964f0-104">Points to a function that creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="964f0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="964f0-105">Syntax</span></span>  
  
```cpp  
typedef HRESULT (STDAPICALLTYPE* PFN_CLRDataCreateInstance) (  
    [in]  REFIID           iid,  
    [in]  ICLRDataTarget  *target,  
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="964f0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="964f0-106">Parameters</span></span>  

 `iid`  
 <span data-ttu-id="964f0-107">de Identificador de la interfaz de la que se va a crear una instancia.</span><span class="sxs-lookup"><span data-stu-id="964f0-107">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="964f0-108">de Un puntero a un objeto [ICLRDataTarget](iclrdatatarget-interface.md) implementado por el usuario que representa el elemento de destino para el que se va a crear el objeto de interfaz.</span><span class="sxs-lookup"><span data-stu-id="964f0-108">[in] A pointer to a user-implemented [ICLRDataTarget](iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="964f0-109">enuncia Puntero a la dirección del objeto de interfaz devuelto.</span><span class="sxs-lookup"><span data-stu-id="964f0-109">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="964f0-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="964f0-110">Remarks</span></span>  

 <span data-ttu-id="964f0-111">El `ICLRDataTarget` escritor de la aplicación de depuración implementa el objeto.</span><span class="sxs-lookup"><span data-stu-id="964f0-111">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="964f0-112">La implementación depende del tipo de elemento de destino que se está representando.</span><span class="sxs-lookup"><span data-stu-id="964f0-112">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="964f0-113">El elemento de destino puede ser un proceso, un volcado de memoria, una máquina remota, etc.</span><span class="sxs-lookup"><span data-stu-id="964f0-113">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="964f0-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="964f0-114">Requirements</span></span>  

 <span data-ttu-id="964f0-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="964f0-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="964f0-116">**Encabezado:** ClrData. idl</span><span class="sxs-lookup"><span data-stu-id="964f0-116">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="964f0-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="964f0-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="964f0-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="964f0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="964f0-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="964f0-119">See also</span></span>

- [<span data-ttu-id="964f0-120">Funciones estáticas globales para la depuración</span><span class="sxs-lookup"><span data-stu-id="964f0-120">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
