---
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
ms.openlocfilehash: cff527aa7cde6a13667d47d030a0ef7db96ad5ba
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122345"
---
# <a name="icordebugtypegetbase-method"></a><span data-ttu-id="4d491-102">ICorDebugType::GetBase (Método)</span><span class="sxs-lookup"><span data-stu-id="4d491-102">ICorDebugType::GetBase Method</span></span>
<span data-ttu-id="4d491-103">Obtiene un puntero de interfaz a una ICorDebugType que representa el tipo base, si existe, del tipo representado por este `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="4d491-103">Gets an interface pointer to an ICorDebugType that represents the base type, if one exists, of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d491-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d491-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBase (  
    [out] ICorDebugType   **pBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d491-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4d491-105">Parameters</span></span>  
 `pBase`  
 <span data-ttu-id="4d491-106">enuncia Puntero a la dirección de un objeto `ICorDebugType` que representa el tipo base.</span><span class="sxs-lookup"><span data-stu-id="4d491-106">[out] A pointer to the address of an `ICorDebugType` object that represents the base type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d491-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4d491-107">Remarks</span></span>  
 <span data-ttu-id="4d491-108">Buscar el tipo base de un tipo es útil para implementar la funcionalidad común del depurador, como la impresión de todos los campos de un objeto o de sus clases primarias.</span><span class="sxs-lookup"><span data-stu-id="4d491-108">Looking up the base type for a type is useful to implement common debugger functionality, such as printing out all the fields of an object or its parent classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d491-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4d491-109">Requirements</span></span>  
 <span data-ttu-id="4d491-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d491-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d491-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4d491-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4d491-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d491-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d491-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d491-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
