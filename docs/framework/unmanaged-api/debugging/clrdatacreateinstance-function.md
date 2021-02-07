---
description: 'Más información acerca de: Clrdatacreateinstance ((función)'
title: CLRDataCreateInstance (Función)
ms.date: 03/30/2017
api_name:
- CLRDataCreateInstance
api_location:
- mscordbi.dll
- mscordacwks.dll
api_type:
- DLLExport
f1_keywords:
- CLRDataCreateInstance
helpviewer_keywords:
- CLRDataCreateInstance function [.NET Framework debugging]
ms.assetid: 440bad90-5a88-45e7-9157-4596801d8d19
topic_type:
- apiref
ms.openlocfilehash: 923b0c687d2b337eacb475973927452e3b47ad0d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747262"
---
# <a name="clrdatacreateinstance-function"></a><span data-ttu-id="3f5d7-103">CLRDataCreateInstance (Función)</span><span class="sxs-lookup"><span data-stu-id="3f5d7-103">CLRDataCreateInstance Function</span></span>

<span data-ttu-id="3f5d7-104">Crea un objeto de interfaz para el elemento de destino especificado.</span><span class="sxs-lookup"><span data-stu-id="3f5d7-104">Creates an interface object for the specified target item.</span></span>

## <a name="syntax"></a><span data-ttu-id="3f5d7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3f5d7-105">Syntax</span></span>

```cpp
HRESULT CLRDataCreateInstance (
    [in]  REFIID           iid,
    [in]  ICLRDataTarget  *target,
    [out] void           **iface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f5d7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3f5d7-106">Parameters</span></span>  

 `iid`  
 <span data-ttu-id="3f5d7-107">de Identificador de la interfaz de la que se va a crear una instancia.</span><span class="sxs-lookup"><span data-stu-id="3f5d7-107">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="3f5d7-108">de Un puntero a un objeto [ICLRDataTarget](iclrdatatarget-interface.md) implementado por el usuario que representa el elemento de destino para el que se va a crear el objeto de interfaz.</span><span class="sxs-lookup"><span data-stu-id="3f5d7-108">[in] A pointer to a user-implemented [ICLRDataTarget](iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="3f5d7-109">enuncia Puntero a la dirección del objeto de interfaz devuelto.</span><span class="sxs-lookup"><span data-stu-id="3f5d7-109">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3f5d7-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3f5d7-110">Remarks</span></span>  

 <span data-ttu-id="3f5d7-111">El `ICLRDataTarget` escritor de la aplicación de depuración implementa el objeto.</span><span class="sxs-lookup"><span data-stu-id="3f5d7-111">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="3f5d7-112">La implementación depende del tipo de elemento de destino que se está representando.</span><span class="sxs-lookup"><span data-stu-id="3f5d7-112">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="3f5d7-113">El elemento de destino puede ser un proceso, un volcado de memoria, una máquina remota, etc.</span><span class="sxs-lookup"><span data-stu-id="3f5d7-113">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f5d7-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3f5d7-114">Requirements</span></span>  

 <span data-ttu-id="3f5d7-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f5d7-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f5d7-116">**Encabezado:** ClrData. idl</span><span class="sxs-lookup"><span data-stu-id="3f5d7-116">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="3f5d7-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f5d7-117">**Library:** CorGuids.lib</span></span>  

 <span data-ttu-id="3f5d7-118">**Ensamblado**: mscordacwks.dll, mscordbi.dll</span><span class="sxs-lookup"><span data-stu-id="3f5d7-118">**Assembly**: mscordacwks.dll, mscordbi.dll</span></span>
  
 <span data-ttu-id="3f5d7-119">**.NET Framework versiones:** Disponible desde .NET Framework 2,0</span><span class="sxs-lookup"><span data-stu-id="3f5d7-119">**.NET Framework Versions:** Available since .NET Framework 2.0</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3f5d7-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f5d7-120">See also</span></span>

- [<span data-ttu-id="3f5d7-121">Funciones estáticas globales para la depuración</span><span class="sxs-lookup"><span data-stu-id="3f5d7-121">Debugging Global Static Functions</span></span>](debugging-global-static-functions.md)
