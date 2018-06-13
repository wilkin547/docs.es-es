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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b96c6ab8fb9065e1a08ad45a7f4482ef0b32788b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418890"
---
# <a name="icordebugtypegetbase-method"></a><span data-ttu-id="33dc7-102">ICorDebugType::GetBase (Método)</span><span class="sxs-lookup"><span data-stu-id="33dc7-102">ICorDebugType::GetBase Method</span></span>
<span data-ttu-id="33dc7-103">Obtiene un puntero de interfaz a una instancia de ICorDebugType que representa el tipo base, si existe, del tipo representado por este `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="33dc7-103">Gets an interface pointer to an ICorDebugType that represents the base type, if one exists, of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33dc7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33dc7-104">Syntax</span></span>  
  
```  
HRESULT GetBase (  
    [out] ICorDebugType   **pBase  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="33dc7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="33dc7-105">Parameters</span></span>  
 `pBase`  
 <span data-ttu-id="33dc7-106">[out] Un puntero a la dirección de un `ICorDebugType` objeto que representa el tipo base.</span><span class="sxs-lookup"><span data-stu-id="33dc7-106">[out] A pointer to the address of an `ICorDebugType` object that represents the base type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33dc7-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="33dc7-107">Remarks</span></span>  
 <span data-ttu-id="33dc7-108">Buscar el tipo base para un tipo es útil para implementar funciones de depuración comunes, como imprimir todos los campos de un objeto o sus clases primarias.</span><span class="sxs-lookup"><span data-stu-id="33dc7-108">Looking up the base type for a type is useful to implement common debugger functionality, such as printing out all the fields of an object or its parent classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33dc7-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="33dc7-109">Requirements</span></span>  
 <span data-ttu-id="33dc7-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33dc7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33dc7-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="33dc7-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="33dc7-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33dc7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33dc7-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33dc7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
