---
description: 'Más información acerca de: ICorDebugType:: GetBase (método)'
title: ICorDebugType::GetBase (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetBase
helpviewer_keywords:
- ICorDebugType::GetBase method [.NET Framework debugging]
- GetBase method [.NET Framework debugging]
ms.assetid: f24e1af9-c220-4f79-ae62-4153ec17ea81
topic_type:
- apiref
ms.openlocfilehash: 78cd540974b540b704e946f6c723214d72e89ab4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658391"
---
# <a name="icordebugtypegetbase-method"></a><span data-ttu-id="4d50b-103">ICorDebugType::GetBase (Método)</span><span class="sxs-lookup"><span data-stu-id="4d50b-103">ICorDebugType::GetBase Method</span></span>

<span data-ttu-id="4d50b-104">Obtiene un puntero de interfaz a una ICorDebugType que representa el tipo base, si existe, del tipo representado por este `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="4d50b-104">Gets an interface pointer to an ICorDebugType that represents the base type, if one exists, of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d50b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d50b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetBase (  
    [out] ICorDebugType   **pBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d50b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4d50b-106">Parameters</span></span>  

 `pBase`  
 <span data-ttu-id="4d50b-107">enuncia Puntero a la dirección de un `ICorDebugType` objeto que representa el tipo base.</span><span class="sxs-lookup"><span data-stu-id="4d50b-107">[out] A pointer to the address of an `ICorDebugType` object that represents the base type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d50b-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4d50b-108">Remarks</span></span>  

 <span data-ttu-id="4d50b-109">Buscar el tipo base de un tipo es útil para implementar la funcionalidad común del depurador, como la impresión de todos los campos de un objeto o de sus clases primarias.</span><span class="sxs-lookup"><span data-stu-id="4d50b-109">Looking up the base type for a type is useful to implement common debugger functionality, such as printing out all the fields of an object or its parent classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d50b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4d50b-110">Requirements</span></span>  

 <span data-ttu-id="4d50b-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d50b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d50b-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4d50b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4d50b-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d50b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d50b-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d50b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
