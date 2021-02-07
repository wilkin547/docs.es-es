---
description: 'Más información acerca de: Createassemblynameobject ((función)'
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
ms.openlocfilehash: 0eaa74bdb37a098ad58b81658229f8c04259b730
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761192"
---
# <a name="createassemblynameobject-function"></a><span data-ttu-id="cb1bd-103">CreateAssemblyNameObject (Función)</span><span class="sxs-lookup"><span data-stu-id="cb1bd-103">CreateAssemblyNameObject Function</span></span>

<span data-ttu-id="cb1bd-104">Obtiene un puntero de interfaz a una instancia de [IAssemblyName](iassemblyname-interface.md) que representa la identidad única del ensamblado con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="cb1bd-104">Gets an interface pointer to an [IAssemblyName](iassemblyname-interface.md) instance that represents the unique identity of the assembly with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb1bd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cb1bd-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyNameObject (  
    [out] LPASSEMBLYNAME  *ppAssemblyNameObj,  
    [in]  LPCWSTR         szAssemblyName,  
    [in]  DWORD           dwFlags,  
    [in]  LPVOID          pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb1bd-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cb1bd-106">Parameters</span></span>  

 `ppAssemblyNameObj`  
 <span data-ttu-id="cb1bd-107">enuncia Devuelto `IAssemblyName` .</span><span class="sxs-lookup"><span data-stu-id="cb1bd-107">[out] The returned `IAssemblyName`.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="cb1bd-108">de Nombre del ensamblado para el que se va a crear la nueva `IAssemblyName` instancia.</span><span class="sxs-lookup"><span data-stu-id="cb1bd-108">[in] The name of the assembly for which to create the new `IAssemblyName` instance.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="cb1bd-109">de Marcas que se van a pasar al constructor de objetos.</span><span class="sxs-lookup"><span data-stu-id="cb1bd-109">[in] Flags to pass to the object constructor.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="cb1bd-110">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="cb1bd-110">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="cb1bd-111">`pvReserved` debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="cb1bd-111">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb1bd-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cb1bd-112">Requirements</span></span>  

 <span data-ttu-id="cb1bd-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb1bd-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb1bd-114">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="cb1bd-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="cb1bd-115">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cb1bd-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cb1bd-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb1bd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb1bd-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb1bd-117">See also</span></span>

- [<span data-ttu-id="cb1bd-118">IAssemblyName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cb1bd-118">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="cb1bd-119">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="cb1bd-119">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
