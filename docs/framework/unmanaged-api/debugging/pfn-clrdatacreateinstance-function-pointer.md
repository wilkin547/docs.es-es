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
ms.openlocfilehash: 34aae3cd913465bc3167d6c5eee9873d212fa4ac
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420700"
---
# <a name="pfn_clrdatacreateinstance-function-pointer"></a><span data-ttu-id="66871-102">puntero a la función PFN_CLRDataCreateInstance</span><span class="sxs-lookup"><span data-stu-id="66871-102">PFN_CLRDataCreateInstance Function Pointer</span></span>
<span data-ttu-id="66871-103">Apunta a una función que crea un objeto de interfaz para el elemento de destino especificado.</span><span class="sxs-lookup"><span data-stu-id="66871-103">Points to a function that creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66871-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="66871-104">Syntax</span></span>  
  
```cpp  
typedef HRESULT (STDAPICALLTYPE* PFN_CLRDataCreateInstance) (  
    [in]  REFIID           iid,  
    [in]  ICLRDataTarget  *target,  
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66871-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="66871-105">Parameters</span></span>  
 `iid`  
 <span data-ttu-id="66871-106">de Identificador de la interfaz de la que se va a crear una instancia.</span><span class="sxs-lookup"><span data-stu-id="66871-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="66871-107">de Un puntero a un objeto [ICLRDataTarget](iclrdatatarget-interface.md) implementado por el usuario que representa el elemento de destino para el que se va a crear el objeto de interfaz.</span><span class="sxs-lookup"><span data-stu-id="66871-107">[in] A pointer to a user-implemented [ICLRDataTarget](iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="66871-108">enuncia Puntero a la dirección del objeto de interfaz devuelto.</span><span class="sxs-lookup"><span data-stu-id="66871-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66871-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="66871-109">Remarks</span></span>  
 <span data-ttu-id="66871-110">El `ICLRDataTarget` escritor de la aplicación de depuración implementa el objeto.</span><span class="sxs-lookup"><span data-stu-id="66871-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="66871-111">La implementación depende del tipo de elemento de destino que se está representando.</span><span class="sxs-lookup"><span data-stu-id="66871-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="66871-112">El elemento de destino puede ser un proceso, un volcado de memoria, una máquina remota, etc.</span><span class="sxs-lookup"><span data-stu-id="66871-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66871-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="66871-113">Requirements</span></span>  
 <span data-ttu-id="66871-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66871-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66871-115">**Encabezado:** ClrData. idl</span><span class="sxs-lookup"><span data-stu-id="66871-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="66871-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66871-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66871-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66871-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66871-118">Consulta también</span><span class="sxs-lookup"><span data-stu-id="66871-118">See also</span></span>

- [<span data-ttu-id="66871-119">Funciones estáticas globales para la depuración</span><span class="sxs-lookup"><span data-stu-id="66871-119">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
