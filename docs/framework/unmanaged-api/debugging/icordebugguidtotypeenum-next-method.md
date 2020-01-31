---
title: ICorDebugGuidToTypeEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum::Next
helpviewer_keywords:
- ICorDebugGuidToTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: c9937666-8e18-484d-9fe0-b9ac95199530
topic_type:
- apiref
ms.openlocfilehash: 76cab0b8b5f16f24c62e31be2707c95c7e557034
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777640"
---
# <a name="icordebugguidtotypeenumnext-method"></a><span data-ttu-id="1d9a2-102">ICorDebugGuidToTypeEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="1d9a2-102">ICorDebugGuidToTypeEnum::Next Method</span></span>
<span data-ttu-id="1d9a2-103">Obtiene el número especificado de instancias de [cordebugguidtotypemapping (](cordebugguidtotypemapping-structure.md) que asignan los GUID a la información de tipo.</span><span class="sxs-lookup"><span data-stu-id="1d9a2-103">Gets the specified number of [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d9a2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1d9a2-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched] CorDebugGuidToTypeMapping values[  ],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d9a2-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="1d9a2-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="1d9a2-106">de El número de objetos de asignación de GUID a tipo que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="1d9a2-106">[in] The number of GUID-to-type mapping objects to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="1d9a2-107">enuncia Una matriz de punteros, cada uno de los cuales apunta a un objeto [cordebugguidtotypemapping (](cordebugguidtotypemapping-structure.md) que asigna un GUID Windows Runtime a su objeto ICorDebugType correspondiente.</span><span class="sxs-lookup"><span data-stu-id="1d9a2-107">[out] An array of pointers, each of which points to a [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) object that maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="1d9a2-108">enuncia Puntero al número de objetos [cordebugguidtotypemapping (](cordebugguidtotypemapping-structure.md) realmente devueltos en `values`.</span><span class="sxs-lookup"><span data-stu-id="1d9a2-108">[out] A pointer to the number of [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) objects actually returned in `values`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d9a2-109">Notas</span><span class="sxs-lookup"><span data-stu-id="1d9a2-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d9a2-110">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="1d9a2-110">Requirements</span></span>  
 <span data-ttu-id="1d9a2-111">**Plataformas:** Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="1d9a2-111">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="1d9a2-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1d9a2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1d9a2-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d9a2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d9a2-114">**.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d9a2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d9a2-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d9a2-115">See also</span></span>

- [<span data-ttu-id="1d9a2-116">ICorDebugGuidToTypeEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1d9a2-116">ICorDebugGuidToTypeEnum Interface</span></span>](icordebugguidtotypeenum-interface.md)
- [<span data-ttu-id="1d9a2-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="1d9a2-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
