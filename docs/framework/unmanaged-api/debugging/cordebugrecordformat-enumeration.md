---
description: 'Más información sobre: enumeración CorDebugRecordFormat'
title: Enumeración CorDebugRecordFormat
ms.date: 03/30/2017
api_name:
- CorDebugRecordFormat
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: d680c1c0-16ab-4ccc-9444-39cf8e0e05ee
topic_type:
- apiref
ms.openlocfilehash: 856522497a8f858abdb39ac232fb3034d4d91dfc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801571"
---
# <a name="cordebugrecordformat-enumeration"></a><span data-ttu-id="80074-103">Enumeración CorDebugRecordFormat</span><span class="sxs-lookup"><span data-stu-id="80074-103">CorDebugRecordFormat Enumeration</span></span>

<span data-ttu-id="80074-104">Describe el formato de los datos de una matriz de bytes que contiene información sobre un evento de depuración de excepción nativo.</span><span class="sxs-lookup"><span data-stu-id="80074-104">Describes the format of the data in a byte array that contains information about a native exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80074-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="80074-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugRecordFormat {  
    FORMAT_WINDOWS_EXCEPTIONRECORD32 = 1,  
    FORMAT_WINDOWS_EXCEPTIONRECORD64 = 2,  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a><span data-ttu-id="80074-106">Members</span><span class="sxs-lookup"><span data-stu-id="80074-106">Members</span></span>  
  
|<span data-ttu-id="80074-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="80074-107">Member</span></span>|<span data-ttu-id="80074-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="80074-108">Description</span></span>|  
|------------|-----------------|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD32`|<span data-ttu-id="80074-109">Los datos son un registro de excepciones de Windows de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="80074-109">The data is a 32-bit Windows exception record.</span></span>|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD64`|<span data-ttu-id="80074-110">Los datos son un registro de excepciones de Windows de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="80074-110">The data is a 64-bit Windows exception record.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80074-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="80074-111">Remarks</span></span>  

 <span data-ttu-id="80074-112">Un miembro de la `CorDebugRecordFormat` enumeración se pasa al método [DecodeEvent](icordebugprocess6-decodeevent-method.md) para indicar el formato de la matriz de bytes en su `pRecord` argumento.</span><span class="sxs-lookup"><span data-stu-id="80074-112">A member of the `CorDebugRecordFormat` enumeration is passed to the [DecodeEvent](icordebugprocess6-decodeevent-method.md) method to indicate the format of the byte array in its `pRecord` argument.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="80074-113">Esta enumeración está pensada solo para su uso en escenarios de depuración .NET Native.</span><span class="sxs-lookup"><span data-stu-id="80074-113">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80074-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="80074-114">Requirements</span></span>  

 <span data-ttu-id="80074-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80074-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80074-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="80074-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="80074-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="80074-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="80074-118">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80074-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80074-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="80074-119">See also</span></span>

- [<span data-ttu-id="80074-120">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="80074-120">Debugging Enumerations</span></span>](debugging-enumerations.md)
