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
ms.openlocfilehash: 99fc89d1aee6c9f0fbffc193e12ce563e820f268
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789281"
---
# <a name="cordebugrecordformat-enumeration"></a><span data-ttu-id="eae55-102">Enumeración CorDebugRecordFormat</span><span class="sxs-lookup"><span data-stu-id="eae55-102">CorDebugRecordFormat Enumeration</span></span>
<span data-ttu-id="eae55-103">Describe el formato de los datos de una matriz de bytes que contiene información sobre un evento de depuración de excepción nativo.</span><span class="sxs-lookup"><span data-stu-id="eae55-103">Describes the format of the data in a byte array that contains information about a native exception debug event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eae55-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eae55-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugRecordFormat {  
    FORMAT_WINDOWS_EXCEPTIONRECORD32 = 1,  
    FORMAT_WINDOWS_EXCEPTIONRECORD64 = 2,  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a><span data-ttu-id="eae55-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="eae55-105">Members</span></span>  
  
|<span data-ttu-id="eae55-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="eae55-106">Member</span></span>|<span data-ttu-id="eae55-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="eae55-107">Description</span></span>|  
|------------|-----------------|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD32`|<span data-ttu-id="eae55-108">Los datos son un registro de excepciones de Windows de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="eae55-108">The data is a 32-bit Windows exception record.</span></span>|  
|`FORMAT_WINDOWS_EXCEPTIONRECORD64`|<span data-ttu-id="eae55-109">Los datos son un registro de excepciones de Windows de 64 bits.</span><span class="sxs-lookup"><span data-stu-id="eae55-109">The data is a 64-bit Windows exception record.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eae55-110">Notas</span><span class="sxs-lookup"><span data-stu-id="eae55-110">Remarks</span></span>  
 <span data-ttu-id="eae55-111">Un miembro de la enumeración `CorDebugRecordFormat` se pasa al método [DecodeEvent](icordebugprocess6-decodeevent-method.md) para indicar el formato de la matriz de bytes en su argumento `pRecord`.</span><span class="sxs-lookup"><span data-stu-id="eae55-111">A member of the `CorDebugRecordFormat` enumeration is passed to the [DecodeEvent](icordebugprocess6-decodeevent-method.md) method to indicate the format of the byte array in its `pRecord` argument.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eae55-112">Esta enumeración está pensada solo para su uso en escenarios de depuración .NET Native.</span><span class="sxs-lookup"><span data-stu-id="eae55-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eae55-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="eae55-113">Requirements</span></span>  
 <span data-ttu-id="eae55-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eae55-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eae55-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eae55-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eae55-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eae55-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eae55-117">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eae55-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eae55-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="eae55-118">See also</span></span>

- [<span data-ttu-id="eae55-119">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="eae55-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
