---
title: ICorDebugFunction::GetILCode (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetILCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetILCode
helpviewer_keywords:
- ICorDebugFunction::GetILCode method [.NET Framework debugging]
- GetILCode method [.NET Framework debugging]
ms.assetid: f794dd47-a7cd-47f6-96e9-a41a4dae8e72
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e32ce10b708afa5741d83cbd05f14accb4b2014f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754671"
---
# <a name="icordebugfunctiongetilcode-method"></a><span data-ttu-id="f4c55-102">ICorDebugFunction::GetILCode (Método)</span><span class="sxs-lookup"><span data-stu-id="f4c55-102">ICorDebugFunction::GetILCode Method</span></span>
<span data-ttu-id="f4c55-103">Obtiene la instancia de ICorDebugCode que representa el código de lenguaje intermedio (MSIL) de Microsoft asociado a este objeto ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="f4c55-103">Gets the ICorDebugCode instance that represents the Microsoft intermediate language (MSIL) code associated with this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4c55-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f4c55-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4c55-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f4c55-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="f4c55-106">[out] Un puntero a la `ICorDebugCode` de instancia o null si la función no se compila en MSIL.</span><span class="sxs-lookup"><span data-stu-id="f4c55-106">[out] A pointer to the `ICorDebugCode` instance, or null, if the function was not compiled into MSIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4c55-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f4c55-107">Remarks</span></span>  
 <span data-ttu-id="f4c55-108">Si ha permitido en esta función, editar y continuar la `GetILCode` método obtendrá el código MSIL correspondiente a versión editada esta función del código de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="f4c55-108">If Edit and Continue has been allowed on this function, the `GetILCode` method will get the MSIL code corresponding to this function's edited version of the code in the common language runtime (CLR).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4c55-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f4c55-109">Requirements</span></span>  
 <span data-ttu-id="f4c55-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4c55-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4c55-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f4c55-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f4c55-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4c55-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4c55-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4c55-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
