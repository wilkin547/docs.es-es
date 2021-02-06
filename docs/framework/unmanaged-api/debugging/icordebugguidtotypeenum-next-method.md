---
description: 'Más información sobre: Icordebugguidtotypeenum (:: Next (método)'
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
ms.openlocfilehash: 0ab05cc0689c76c0bb185205ea00c5ccebfcbe03
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661004"
---
# <a name="icordebugguidtotypeenumnext-method"></a><span data-ttu-id="a23fc-103">ICorDebugGuidToTypeEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="a23fc-103">ICorDebugGuidToTypeEnum::Next Method</span></span>

<span data-ttu-id="a23fc-104">Obtiene el número especificado de instancias de [cordebugguidtotypemapping (](cordebugguidtotypemapping-structure.md) que asignan los GUID a la información de tipo.</span><span class="sxs-lookup"><span data-stu-id="a23fc-104">Gets the specified number of [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a23fc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a23fc-105">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched] CorDebugGuidToTypeMapping values[  ],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a23fc-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a23fc-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="a23fc-107">de El número de objetos de asignación de GUID a tipo que se van a recuperar.</span><span class="sxs-lookup"><span data-stu-id="a23fc-107">[in] The number of GUID-to-type mapping objects to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="a23fc-108">enuncia Una matriz de punteros, cada uno de los cuales apunta a un objeto [cordebugguidtotypemapping (](cordebugguidtotypemapping-structure.md) que asigna un GUID Windows Runtime a su objeto ICorDebugType correspondiente.</span><span class="sxs-lookup"><span data-stu-id="a23fc-108">[out] An array of pointers, each of which points to a [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) object that maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="a23fc-109">enuncia Un puntero al número de objetos [cordebugguidtotypemapping (](cordebugguidtotypemapping-structure.md) realmente devueltos en `values` .</span><span class="sxs-lookup"><span data-stu-id="a23fc-109">[out] A pointer to the number of [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) objects actually returned in `values`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a23fc-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a23fc-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a23fc-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a23fc-111">Requirements</span></span>  

 <span data-ttu-id="a23fc-112">**Plataformas:** Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="a23fc-112">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="a23fc-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a23fc-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a23fc-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a23fc-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a23fc-115">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a23fc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a23fc-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a23fc-116">See also</span></span>

- [<span data-ttu-id="a23fc-117">ICorDebugGuidToTypeEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a23fc-117">ICorDebugGuidToTypeEnum Interface</span></span>](icordebugguidtotypeenum-interface.md)
- [<span data-ttu-id="a23fc-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="a23fc-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
