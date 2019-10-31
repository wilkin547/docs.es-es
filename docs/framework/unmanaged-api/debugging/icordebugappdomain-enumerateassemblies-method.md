---
title: ICorDebugAppDomain::EnumerateAssemblies (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.EnumerateAssemblies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::EnumerateAssemblies
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateAssemblies method [.NET Framework debugging]
- EnumerateAssemblies method [.NET Framework debugging]
ms.assetid: 7add64f9-19a8-46a9-be62-905d5e7d1bd8
topic_type:
- apiref
ms.openlocfilehash: 573b08fcf2ce0fa5ce3187df6ae6a1c2cc385f52
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134007"
---
# <a name="icordebugappdomainenumerateassemblies-method"></a><span data-ttu-id="45576-102">ICorDebugAppDomain::EnumerateAssemblies (Método)</span><span class="sxs-lookup"><span data-stu-id="45576-102">ICorDebugAppDomain::EnumerateAssemblies Method</span></span>
<span data-ttu-id="45576-103">Obtiene un enumerador para los ensamblados en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="45576-103">Gets an enumerator for the assemblies in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45576-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="45576-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateAssemblies (  
    [out] ICorDebugAssemblyEnum  **ppAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45576-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="45576-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="45576-106">enuncia Un puntero a la dirección de un objeto ICorDebugAssemblyEnum que es el enumerador para los ensamblados en el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="45576-106">[out] A pointer to the address of an ICorDebugAssemblyEnum object that is the enumerator for the assemblies in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45576-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="45576-107">Requirements</span></span>  
 <span data-ttu-id="45576-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45576-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45576-109">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="45576-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="45576-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45576-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45576-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45576-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
