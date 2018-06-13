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
ms.openlocfilehash: a27c96a7be9b5d868e07da11f1a239b9dd5fe2f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402857"
---
# <a name="cordebugrecordformat-enumeration"></a><span data-ttu-id="fec27-102">Enumeración CorDebugRecordFormat</span><span class="sxs-lookup"><span data-stu-id="fec27-102">CorDebugRecordFormat Enumeration</span></span>
<span data-ttu-id="fec27-103">Describe el formato de los datos de una matriz de bytes que contiene información sobre un evento de depuración de excepción nativo.</span><span class="sxs-lookup"><span data-stu-id="fec27-103">Describes the format of the data in a byte array that contains information about a native exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fec27-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fec27-104">Syntax</span></span>  
  
```  
typedef enum CorDebugRecordFormat {  
    FORMAT_WINDOWS_EXCEPTIONRECORD32 = 1,  
    FORMAT_WINDOWS_EXCEPTIONRECORD64 = 2,  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a><span data-ttu-id="fec27-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="fec27-105">Members</span></span>  
  
|<span data-ttu-id="fec27-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="fec27-106">Member</span></span>|<span data-ttu-id="fec27-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="fec27-107">Description</span></span>|  
|------------|-----------------|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD32`|<span data-ttu-id="fec27-108">Los datos son un registro de excepciones de Windows de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="fec27-108">The data is a 32-bit Windows exception record.</span></span>|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD64`|<span data-ttu-id="fec27-109">Los datos son un registro de excepciones de Windows de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="fec27-109">The data is a 64-bit Windows exception record.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fec27-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fec27-110">Remarks</span></span>  
 <span data-ttu-id="fec27-111">Un miembro de la `CorDebugRecordFormat` enumeración se pasa a la [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) método para indicar el formato de la matriz de bytes en su `pRecord` argumento.</span><span class="sxs-lookup"><span data-stu-id="fec27-111">A member of the `CorDebugRecordFormat` enumeration is passed to the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method to indicate the format of the byte array in its `pRecord` argument.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fec27-112">Esta enumeración está pensada solo para su uso en escenarios de depuración .NET Native.</span><span class="sxs-lookup"><span data-stu-id="fec27-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fec27-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fec27-113">Requirements</span></span>  
 <span data-ttu-id="fec27-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fec27-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fec27-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fec27-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fec27-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fec27-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fec27-117">**Versiones de .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fec27-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fec27-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="fec27-118">See Also</span></span>  
 [<span data-ttu-id="fec27-119">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="fec27-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
