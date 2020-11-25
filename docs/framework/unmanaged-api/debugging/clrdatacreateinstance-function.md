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
ms.openlocfilehash: 2ffc575cfcef1089a70ef3b6d38787a5b4c50443
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729829"
---
# <a name="clrdatacreateinstance-function"></a><span data-ttu-id="f4be7-102">CLRDataCreateInstance (Función)</span><span class="sxs-lookup"><span data-stu-id="f4be7-102">CLRDataCreateInstance Function</span></span>

<span data-ttu-id="f4be7-103">Crea un objeto de interfaz para el elemento de destino especificado.</span><span class="sxs-lookup"><span data-stu-id="f4be7-103">Creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4be7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f4be7-104">Syntax</span></span>  
  
```cpp  
HRESULT CLRDataCreateInstance (  
    [in]  REFIID           iid,
    [in]  ICLRDataTarget  *target,
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4be7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f4be7-105">Parameters</span></span>  

 `iid`  
 <span data-ttu-id="f4be7-106">de Identificador de la interfaz de la que se va a crear una instancia.</span><span class="sxs-lookup"><span data-stu-id="f4be7-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="f4be7-107">de Un puntero a un objeto [ICLRDataTarget](iclrdatatarget-interface.md) implementado por el usuario que representa el elemento de destino para el que se va a crear el objeto de interfaz.</span><span class="sxs-lookup"><span data-stu-id="f4be7-107">[in] A pointer to a user-implemented [ICLRDataTarget](iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="f4be7-108">enuncia Puntero a la dirección del objeto de interfaz devuelto.</span><span class="sxs-lookup"><span data-stu-id="f4be7-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4be7-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f4be7-109">Remarks</span></span>  

 <span data-ttu-id="f4be7-110">El `ICLRDataTarget` escritor de la aplicación de depuración implementa el objeto.</span><span class="sxs-lookup"><span data-stu-id="f4be7-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="f4be7-111">La implementación depende del tipo de elemento de destino que se está representando.</span><span class="sxs-lookup"><span data-stu-id="f4be7-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="f4be7-112">El elemento de destino puede ser un proceso, un volcado de memoria, una máquina remota, etc.</span><span class="sxs-lookup"><span data-stu-id="f4be7-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4be7-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f4be7-113">Requirements</span></span>  

 <span data-ttu-id="f4be7-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4be7-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4be7-115">**Encabezado:** ClrData. idl</span><span class="sxs-lookup"><span data-stu-id="f4be7-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="f4be7-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4be7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4be7-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4be7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4be7-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f4be7-118">See also</span></span>

- [<span data-ttu-id="f4be7-119">Funciones estáticas globales para la depuración</span><span class="sxs-lookup"><span data-stu-id="f4be7-119">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
