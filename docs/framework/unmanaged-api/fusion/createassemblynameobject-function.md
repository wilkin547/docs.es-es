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
ms.openlocfilehash: 995f1064c2f40005c4a19ef034d7edfd668b5d51
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704167"
---
# <a name="createassemblynameobject-function"></a><span data-ttu-id="fcf4e-102">CreateAssemblyNameObject (Función)</span><span class="sxs-lookup"><span data-stu-id="fcf4e-102">CreateAssemblyNameObject Function</span></span>

<span data-ttu-id="fcf4e-103">Obtiene un puntero de interfaz a una instancia de [IAssemblyName](iassemblyname-interface.md) que representa la identidad única del ensamblado con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="fcf4e-103">Gets an interface pointer to an [IAssemblyName](iassemblyname-interface.md) instance that represents the unique identity of the assembly with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcf4e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fcf4e-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyNameObject (  
    [out] LPASSEMBLYNAME  *ppAssemblyNameObj,  
    [in]  LPCWSTR         szAssemblyName,  
    [in]  DWORD           dwFlags,  
    [in]  LPVOID          pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="fcf4e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fcf4e-105">Parameters</span></span>  

 `ppAssemblyNameObj`  
 <span data-ttu-id="fcf4e-106">enuncia Devuelto `IAssemblyName` .</span><span class="sxs-lookup"><span data-stu-id="fcf4e-106">[out] The returned `IAssemblyName`.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="fcf4e-107">de Nombre del ensamblado para el que se va a crear la nueva `IAssemblyName` instancia.</span><span class="sxs-lookup"><span data-stu-id="fcf4e-107">[in] The name of the assembly for which to create the new `IAssemblyName` instance.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="fcf4e-108">de Marcas que se van a pasar al constructor de objetos.</span><span class="sxs-lookup"><span data-stu-id="fcf4e-108">[in] Flags to pass to the object constructor.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="fcf4e-109">[in] Reservado para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="fcf4e-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="fcf4e-110">`pvReserved` debe ser una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="fcf4e-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcf4e-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fcf4e-111">Requirements</span></span>  

 <span data-ttu-id="fcf4e-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fcf4e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcf4e-113">**Encabezado:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="fcf4e-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="fcf4e-114">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fcf4e-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fcf4e-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcf4e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcf4e-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fcf4e-116">See also</span></span>

- [<span data-ttu-id="fcf4e-117">IAssemblyName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fcf4e-117">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="fcf4e-118">Funciones estáticas globales de la fusión</span><span class="sxs-lookup"><span data-stu-id="fcf4e-118">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
