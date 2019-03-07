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
ms.openlocfilehash: f34a2fe2bb1f92e75f77c086b03776ec59495600
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57482111"
---
# <a name="icordebugfunctiongetilcode-method"></a><span data-ttu-id="04123-102">ICorDebugFunction::GetILCode (Método)</span><span class="sxs-lookup"><span data-stu-id="04123-102">ICorDebugFunction::GetILCode Method</span></span>
<span data-ttu-id="04123-103">Obtiene la instancia de ICorDebugCode que representa el código de lenguaje intermedio (MSIL) de Microsoft asociado a este objeto ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="04123-103">Gets the ICorDebugCode instance that represents the Microsoft intermediate language (MSIL) code associated with this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04123-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="04123-104">Syntax</span></span>  
  
```  
HRESULT GetILCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04123-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="04123-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="04123-106">[out] Un puntero a la `ICorDebugCode` de instancia o null si la función no se compila en MSIL.</span><span class="sxs-lookup"><span data-stu-id="04123-106">[out] A pointer to the `ICorDebugCode` instance, or null, if the function was not compiled into MSIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04123-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="04123-107">Remarks</span></span>  
 <span data-ttu-id="04123-108">Si ha permitido en esta función, editar y continuar la `GetILCode` método obtendrá el código MSIL correspondiente a versión editada esta función del código de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="04123-108">If Edit and Continue has been allowed on this function, the `GetILCode` method will get the MSIL code corresponding to this function's edited version of the code in the common language runtime (CLR).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04123-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="04123-109">Requirements</span></span>  
 <span data-ttu-id="04123-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04123-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04123-111">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="04123-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="04123-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04123-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04123-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04123-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
