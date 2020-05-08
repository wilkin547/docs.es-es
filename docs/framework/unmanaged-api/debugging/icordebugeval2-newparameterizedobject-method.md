---
title: ICorDebugEval2::NewParameterizedObject (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewParameterizedObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedObject
helpviewer_keywords:
- NewParameterizedObject method [.NET Framework debugging]
- ICorDebugEval2::NewParameterizedObject method [.NET Framework debugging]
ms.assetid: 3d705463-e640-4249-8036-4e8206d03cfe
topic_type:
- apiref
ms.openlocfilehash: f6ede42ac90f65f934e285f879bcef62d13b65cb
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976101"
---
# <a name="icordebugeval2newparameterizedobject-method"></a><span data-ttu-id="06396-102">ICorDebugEval2::NewParameterizedObject (Método)</span><span class="sxs-lookup"><span data-stu-id="06396-102">ICorDebugEval2::NewParameterizedObject Method</span></span>
<span data-ttu-id="06396-103">Crea una instancia de un nuevo objeto de tipo parametrizado y llama al método de constructor del objeto.</span><span class="sxs-lookup"><span data-stu-id="06396-103">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06396-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="06396-104">Syntax</span></span>  
  
```cpp  
HRESULT NewParameterizedObject (  
    [in] ICorDebugFunction     *pConstructor,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06396-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="06396-105">Parameters</span></span>  
 `pConstructor`  
 <span data-ttu-id="06396-106">de Un puntero a un objeto ICorDebugFunction que representa el constructor del objeto del que se va a crear una instancia.</span><span class="sxs-lookup"><span data-stu-id="06396-106">[in] A pointer to an ICorDebugFunction object that represents the constructor of the object to be instantiated.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="06396-107">de El número de argumentos de tipo pasados.</span><span class="sxs-lookup"><span data-stu-id="06396-107">[in] The number of type arguments passed.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="06396-108">de Matriz de punteros, cada uno de los cuales señala a un objeto ICorDebugType que representa un argumento de tipo para el objeto del que se crea una instancia.</span><span class="sxs-lookup"><span data-stu-id="06396-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument for the object that is being instantiated.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="06396-109">de El número de argumentos pasados al constructor.</span><span class="sxs-lookup"><span data-stu-id="06396-109">[in] The number of arguments passed to the constructor.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="06396-110">de Matriz de punteros, cada uno de los cuales señala a un objeto ICorDebugValue que representa un valor de argumento que se pasa al constructor.</span><span class="sxs-lookup"><span data-stu-id="06396-110">[in] An array of pointers, each of which points to an ICorDebugValue object that represents an argument value that is passed to the constructor.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06396-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="06396-111">Remarks</span></span>  
 <span data-ttu-id="06396-112">El constructor del objeto puede tomar <xref:System.Type> parámetros.</span><span class="sxs-lookup"><span data-stu-id="06396-112">The object's constructor may take <xref:System.Type> parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06396-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="06396-113">Requirements</span></span>  
 <span data-ttu-id="06396-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06396-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06396-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="06396-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="06396-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06396-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06396-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06396-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
