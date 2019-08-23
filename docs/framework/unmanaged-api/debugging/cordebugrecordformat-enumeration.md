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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e6ed7d25593f9dd5d5d01f8c06024dcf8acfcfea
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916474"
---
# <a name="cordebugrecordformat-enumeration"></a><span data-ttu-id="c0eb3-102">Enumeración CorDebugRecordFormat</span><span class="sxs-lookup"><span data-stu-id="c0eb3-102">CorDebugRecordFormat Enumeration</span></span>
<span data-ttu-id="c0eb3-103">Describe el formato de los datos de una matriz de bytes que contiene información sobre un evento de depuración de excepción nativo.</span><span class="sxs-lookup"><span data-stu-id="c0eb3-103">Describes the format of the data in a byte array that contains information about a native exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0eb3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c0eb3-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugRecordFormat {  
    FORMAT_WINDOWS_EXCEPTIONRECORD32 = 1,  
    FORMAT_WINDOWS_EXCEPTIONRECORD64 = 2,  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a><span data-ttu-id="c0eb3-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="c0eb3-105">Members</span></span>  
  
|<span data-ttu-id="c0eb3-106">Member</span><span class="sxs-lookup"><span data-stu-id="c0eb3-106">Member</span></span>|<span data-ttu-id="c0eb3-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c0eb3-107">Description</span></span>|  
|------------|-----------------|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD32`|<span data-ttu-id="c0eb3-108">Los datos son un registro de excepciones de Windows de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="c0eb3-108">The data is a 32-bit Windows exception record.</span></span>|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD64`|<span data-ttu-id="c0eb3-109">Los datos son un registro de excepciones de Windows de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="c0eb3-109">The data is a 64-bit Windows exception record.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0eb3-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c0eb3-110">Remarks</span></span>  
 <span data-ttu-id="c0eb3-111">Un miembro de la `CorDebugRecordFormat` enumeración se pasa al método [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) para indicar el formato de la matriz de bytes `pRecord` en su argumento.</span><span class="sxs-lookup"><span data-stu-id="c0eb3-111">A member of the `CorDebugRecordFormat` enumeration is passed to the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method to indicate the format of the byte array in its `pRecord` argument.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c0eb3-112">Esta enumeración está pensada solo para su uso en escenarios de depuración .NET Native.</span><span class="sxs-lookup"><span data-stu-id="c0eb3-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0eb3-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c0eb3-113">Requirements</span></span>  
 <span data-ttu-id="c0eb3-114">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0eb3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0eb3-115">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="c0eb3-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c0eb3-116">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0eb3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0eb3-117">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0eb3-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0eb3-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0eb3-118">See also</span></span>

- [<span data-ttu-id="c0eb3-119">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="c0eb3-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
