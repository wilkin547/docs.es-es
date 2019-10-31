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
ms.openlocfilehash: c2ce4b95de75bef3928e144656b565676568caa0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137910"
---
# <a name="icordebugfunctiongetilcode-method"></a><span data-ttu-id="d88f0-102">ICorDebugFunction::GetILCode (Método)</span><span class="sxs-lookup"><span data-stu-id="d88f0-102">ICorDebugFunction::GetILCode Method</span></span>
<span data-ttu-id="d88f0-103">Obtiene la instancia de ICorDebugCode que representa el código de lenguaje intermedio de Microsoft (MSIL) asociado a este objeto ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="d88f0-103">Gets the ICorDebugCode instance that represents the Microsoft intermediate language (MSIL) code associated with this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d88f0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d88f0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d88f0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d88f0-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="d88f0-106">enuncia Puntero a la instancia de `ICorDebugCode`, o null, si la función no se compiló en MSIL.</span><span class="sxs-lookup"><span data-stu-id="d88f0-106">[out] A pointer to the `ICorDebugCode` instance, or null, if the function was not compiled into MSIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d88f0-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d88f0-107">Remarks</span></span>  
 <span data-ttu-id="d88f0-108">Si se permite editar y continuar en esta función, el método `GetILCode` obtendrá el código MSIL correspondiente a la versión editada de esta función del código en el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="d88f0-108">If Edit and Continue has been allowed on this function, the `GetILCode` method will get the MSIL code corresponding to this function's edited version of the code in the common language runtime (CLR).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d88f0-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d88f0-109">Requirements</span></span>  
 <span data-ttu-id="d88f0-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d88f0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d88f0-111">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d88f0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d88f0-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d88f0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d88f0-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d88f0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
