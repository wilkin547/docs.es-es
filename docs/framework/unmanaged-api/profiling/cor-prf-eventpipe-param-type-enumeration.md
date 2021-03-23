---
description: 'Más información acerca de: enumeración COR_PRF_EVENTPIPE_PARAM_TYPE'
title: Enumeración COR_PRF_EVENTPIPE_PARAM_TYPE
ms.date: 03/19/2021
api_name:
- COR_PRF_EVENTPIPE_PARAM_TYPE
api_location:
- coreclr.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 29aed86e4a991598d038a60ae086e77e25df24bb
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805784"
---
# <a name="cor_prf_eventpipe_param_type-enumeration"></a><span data-ttu-id="7cc7b-103">Enumeración COR_PRF_EVENTPIPE_PARAM_TYPE</span><span class="sxs-lookup"><span data-stu-id="7cc7b-103">COR_PRF_EVENTPIPE_PARAM_TYPE Enumeration</span></span>

<span data-ttu-id="7cc7b-104">Describe el tipo de un parámetro para un evento EventPipe.</span><span class="sxs-lookup"><span data-stu-id="7cc7b-104">Describes the type of a parameter for an EventPipe event.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="7cc7b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7cc7b-105">Syntax</span></span>  
  
```cpp  
typedef enum
{
    COR_PRF_EVENTPIPE_OBJECT = 1,
    COR_PRF_EVENTPIPE_BOOLEAN = 3,
    COR_PRF_EVENTPIPE_CHAR = 4,
    COR_PRF_EVENTPIPE_SBYTE = 5,
    COR_PRF_EVENTPIPE_BYTE = 6,
    COR_PRF_EVENTPIPE_INT16 = 7,
    COR_PRF_EVENTPIPE_UINT16 = 8,
    COR_PRF_EVENTPIPE_INT32 = 9,
    COR_PRF_EVENTPIPE_UINT32 = 10,
    COR_PRF_EVENTPIPE_INT64 = 11,
    COR_PRF_EVENTPIPE_UINT64 = 12,
    COR_PRF_EVENTPIPE_SINGLE = 13,
    COR_PRF_EVENTPIPE_DOUBLE = 14,
    COR_PRF_EVENTPIPE_DECIMAL = 15,
    COR_PRF_EVENTPIPE_DATETIME = 16,
    COR_PRF_EVENTPIPE_GUID = 17,
    COR_PRF_EVENTPIPE_STRING = 18,
    COR_PRF_EVENTPIPE_ARRAY = 19,
} COR_PRF_EVENTPIPE_PARAM_TYPE;
```  
  
## <a name="members"></a><span data-ttu-id="7cc7b-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="7cc7b-106">Members</span></span>  
  
|<span data-ttu-id="7cc7b-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="7cc7b-107">Member</span></span>|<span data-ttu-id="7cc7b-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="7cc7b-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_EVENTPIPE_OBJECT`|<span data-ttu-id="7cc7b-109">El tipo de parámetro es un objeto que se describe automáticamente.</span><span class="sxs-lookup"><span data-stu-id="7cc7b-109">The parameter type is a self describing object.</span></span>|
|`COR_PRF_EVENTPIPE_BOOLEAN`|<span data-ttu-id="7cc7b-110">El tipo de parámetro es un valor booleano.</span><span class="sxs-lookup"><span data-stu-id="7cc7b-110">The parameter type is a boolean.</span></span>|
|`COR_PRF_EVENTPIPE_CHAR`|<span data-ttu-id="7cc7b-111">El tipo de parámetro es un carácter ancho de 16 bits.</span><span class="sxs-lookup"><span data-stu-id="7cc7b-111">The parameter type is a 16 bit wide character.</span></span>|
|`COR_PRF_EVENTPIPE_SBYTE`|<span data-ttu-id="7cc7b-112">El tipo de parámetro es un entero de 8 bits con signo.</span><span class="sxs-lookup"><span data-stu-id="7cc7b-112">The parameter type is a signed 8 bit integer.</span></span>|
|`COR_PRF_EVENTPIPE_BYTE`|<span data-ttu-id="7cc7b-113">El tipo de parámetro es un entero de 8 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="7cc7b-113">The parameter type is an unsigned 8 bit integer.</span></span>|
|`COR_PRF_EVENTPIPE_INT16`|<span data-ttu-id="7cc7b-114">El tipo de parámetro es un entero de 16 bits con signo.</span><span class="sxs-lookup"><span data-stu-id="7cc7b-114">The parameter type is a signed 16 bit integer.</span></span>|
|`COR_PRF_EVENTPIPE_UINT16`|<span data-ttu-id="7cc7b-115">El tipo de parámetro es un entero de 16 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="7cc7b-115">The parameter type is an unsigned 16 bit integer.</span></span>|
|`COR_PRF_EVENTPIPE_INT32`|<span data-ttu-id="7cc7b-116">El tipo de parámetro es un entero de 32 bits con signo.</span><span class="sxs-lookup"><span data-stu-id="7cc7b-116">The parameter type is a signed 32 bit integer.</span></span>|
|`COR_PRF_EVENTPIPE_UINT32`|<span data-ttu-id="7cc7b-117">El tipo de parámetro es un entero de bit 32 sin signo.</span><span class="sxs-lookup"><span data-stu-id="7cc7b-117">The parameter type is an unsigned 32 bit integer.</span></span>|
|`COR_PRF_EVENTPIPE_INT64`|<span data-ttu-id="7cc7b-118">El tipo de parámetro es un entero de 64 bits con signo.</span><span class="sxs-lookup"><span data-stu-id="7cc7b-118">The parameter type is a signed 64 bit integer.</span></span>|
|`COR_PRF_EVENTPIPE_UINT64`|<span data-ttu-id="7cc7b-119">El tipo de parámetro es un entero de bit 64 sin signo.</span><span class="sxs-lookup"><span data-stu-id="7cc7b-119">The parameter type is an unsigned 64 bit integer.</span></span>|
|`COR_PRF_EVENTPIPE_SINGLE`|<span data-ttu-id="7cc7b-120">El tipo de parámetro es un número de punto flotante de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="7cc7b-120">The parameter type is a 32 bit floating point number.</span></span>|
|`COR_PRF_EVENTPIPE_DOUBLE`|<span data-ttu-id="7cc7b-121">El tipo de parámetro es un número de punto flotante de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="7cc7b-121">The parameter type is a 64 bit floating point number.</span></span>|
|`COR_PRF_EVENTPIPE_DECIMAL`|<span data-ttu-id="7cc7b-122">El tipo de parámetro es un número de punto flotante de 128 bits.</span><span class="sxs-lookup"><span data-stu-id="7cc7b-122">The parameter type is a 128 bit floating point number.</span></span>|
|`COR_PRF_EVENTPIPE_DATETIME`|<span data-ttu-id="7cc7b-123">El tipo de parámetro es una estructura de tiempo de fecha serializada.</span><span class="sxs-lookup"><span data-stu-id="7cc7b-123">The parameter type is a serialized DataTime structure.</span></span>|
|`COR_PRF_EVENTPIPE_GUID`|<span data-ttu-id="7cc7b-124">El tipo de parámetro es un GUID.</span><span class="sxs-lookup"><span data-stu-id="7cc7b-124">The parameter type is a GUID.</span></span>|
|`COR_PRF_EVENTPIPE_STRING`|<span data-ttu-id="7cc7b-125">El tipo de parámetro es una cadena de caracteres anchos terminada en NULL de 16 bits.</span><span class="sxs-lookup"><span data-stu-id="7cc7b-125">The parameter type is a 16 bit null terminated wide character string.</span></span>|
|`COR_PRF_EVENTPIPE_ARRAY`|<span data-ttu-id="7cc7b-126">El tipo de parámetro es una matriz de uno de los tipos anteriores.</span><span class="sxs-lookup"><span data-stu-id="7cc7b-126">The parameter type is an array of one of the preceding types.</span></span>|
  
## <a name="remarks"></a><span data-ttu-id="7cc7b-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7cc7b-127">Remarks</span></span>  

 <span data-ttu-id="7cc7b-128">La `COR_PRF_EVENTPIPE_PARAM_TYPE` estructura [COR_PRF_EVENTPIPE_PARAM_DESC](cor-prf-eventpipe-param-desc-structure.md) usa la enumeración para indicar el tipo del parámetro.</span><span class="sxs-lookup"><span data-stu-id="7cc7b-128">The `COR_PRF_EVENTPIPE_PARAM_TYPE` enumeration is used by the [COR_PRF_EVENTPIPE_PARAM_DESC](cor-prf-eventpipe-param-desc-structure.md) structure to indicate the type of the parameter.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="7cc7b-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7cc7b-129">Requirements</span></span>  

<span data-ttu-id="7cc7b-130">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="7cc7b-130">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>
<span data-ttu-id="7cc7b-131">**Encabezado:** **Versiones de .net** de Corprof. idl, Corprof. h: [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7cc7b-131">**Header:** CorProf.idl, CorProf.h **.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-50-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7cc7b-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7cc7b-132">See also</span></span>

- [<span data-ttu-id="7cc7b-133">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="7cc7b-133">Profiling Enumerations</span></span>](profiling-enumerations.md)
