---
title: "Enumeración CorDebugRecordFormat"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugRecordFormat
api_location: mscordbi.dll
api_type: COM
ms.assetid: d680c1c0-16ab-4ccc-9444-39cf8e0e05ee
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c2f8397382dde061078a0d96114420f1c5f48669
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugrecordformat-enumeration"></a><span data-ttu-id="cbe3a-102">Enumeración CorDebugRecordFormat</span><span class="sxs-lookup"><span data-stu-id="cbe3a-102">CorDebugRecordFormat Enumeration</span></span>
<span data-ttu-id="cbe3a-103">Describe el formato de los datos de una matriz de bytes que contiene información sobre un evento de depuración de excepción nativo.</span><span class="sxs-lookup"><span data-stu-id="cbe3a-103">Describes the format of the data in a byte array that contains information about a native exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbe3a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cbe3a-104">Syntax</span></span>  
  
```  
typedef enum CorDebugRecordFormat {  
    FORMAT_WINDOWS_EXCEPTIONRECORD32 = 1,  
    FORMAT_WINDOWS_EXCEPTIONRECORD64 = 2,  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a><span data-ttu-id="cbe3a-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="cbe3a-105">Members</span></span>  
  
|<span data-ttu-id="cbe3a-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="cbe3a-106">Member</span></span>|<span data-ttu-id="cbe3a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="cbe3a-107">Description</span></span>|  
|------------|-----------------|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD32`|<span data-ttu-id="cbe3a-108">Los datos son un registro de excepciones de Windows de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="cbe3a-108">The data is a 32-bit Windows exception record.</span></span>|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD64`|<span data-ttu-id="cbe3a-109">Los datos son un registro de excepciones de Windows de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="cbe3a-109">The data is a 64-bit Windows exception record.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cbe3a-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cbe3a-110">Remarks</span></span>  
 <span data-ttu-id="cbe3a-111">Un miembro de la `CorDebugRecordFormat` enumeración se pasa a la [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) método para indicar el formato de la matriz de bytes en su `pRecord` argumento.</span><span class="sxs-lookup"><span data-stu-id="cbe3a-111">A member of the `CorDebugRecordFormat` enumeration is passed to the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method to indicate the format of the byte array in its `pRecord` argument.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cbe3a-112">Esta enumeración está pensada solo para su uso en escenarios de depuración .NET Native.</span><span class="sxs-lookup"><span data-stu-id="cbe3a-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbe3a-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cbe3a-113">Requirements</span></span>  
 <span data-ttu-id="cbe3a-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbe3a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbe3a-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cbe3a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cbe3a-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cbe3a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cbe3a-117">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbe3a-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbe3a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="cbe3a-118">See Also</span></span>  
 [<span data-ttu-id="cbe3a-119">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="cbe3a-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
