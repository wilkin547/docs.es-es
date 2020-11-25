---
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
ms.openlocfilehash: b3a22d7b32eb258263d373ae91b3fb7fbc9aae99
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696393"
---
# <a name="cordebugrecordformat-enumeration"></a><span data-ttu-id="51137-102">Enumeración CorDebugRecordFormat</span><span class="sxs-lookup"><span data-stu-id="51137-102">CorDebugRecordFormat Enumeration</span></span>

<span data-ttu-id="51137-103">Describe el formato de los datos de una matriz de bytes que contiene información sobre un evento de depuración de excepción nativo.</span><span class="sxs-lookup"><span data-stu-id="51137-103">Describes the format of the data in a byte array that contains information about a native exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51137-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="51137-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugRecordFormat {  
    FORMAT_WINDOWS_EXCEPTIONRECORD32 = 1,  
    FORMAT_WINDOWS_EXCEPTIONRECORD64 = 2,  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a><span data-ttu-id="51137-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="51137-105">Members</span></span>  
  
|<span data-ttu-id="51137-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="51137-106">Member</span></span>|<span data-ttu-id="51137-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="51137-107">Description</span></span>|  
|------------|-----------------|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD32`|<span data-ttu-id="51137-108">Los datos son un registro de excepciones de Windows de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="51137-108">The data is a 32-bit Windows exception record.</span></span>|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD64`|<span data-ttu-id="51137-109">Los datos son un registro de excepciones de Windows de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="51137-109">The data is a 64-bit Windows exception record.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51137-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="51137-110">Remarks</span></span>  

 <span data-ttu-id="51137-111">Un miembro de la `CorDebugRecordFormat` enumeración se pasa al método [DecodeEvent](icordebugprocess6-decodeevent-method.md) para indicar el formato de la matriz de bytes en su `pRecord` argumento.</span><span class="sxs-lookup"><span data-stu-id="51137-111">A member of the `CorDebugRecordFormat` enumeration is passed to the [DecodeEvent](icordebugprocess6-decodeevent-method.md) method to indicate the format of the byte array in its `pRecord` argument.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="51137-112">Esta enumeración está pensada solo para su uso en escenarios de depuración .NET Native.</span><span class="sxs-lookup"><span data-stu-id="51137-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51137-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="51137-113">Requirements</span></span>  

 <span data-ttu-id="51137-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51137-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51137-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="51137-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="51137-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51137-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51137-117">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51137-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51137-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="51137-118">See also</span></span>

- [<span data-ttu-id="51137-119">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="51137-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
