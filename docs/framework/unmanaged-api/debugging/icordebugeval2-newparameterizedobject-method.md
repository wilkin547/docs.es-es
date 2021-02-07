---
description: 'Más información sobre: ICorDebugEval2:: NewParameterizedObject ((método)'
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
ms.openlocfilehash: 2dc746fdada0e79044a1387bd4cb1c11b81d7777
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693686"
---
# <a name="icordebugeval2newparameterizedobject-method"></a><span data-ttu-id="6be6e-103">ICorDebugEval2::NewParameterizedObject (Método)</span><span class="sxs-lookup"><span data-stu-id="6be6e-103">ICorDebugEval2::NewParameterizedObject Method</span></span>

<span data-ttu-id="6be6e-104">Crea una instancia de un nuevo objeto de tipo parametrizado y llama al método de constructor del objeto.</span><span class="sxs-lookup"><span data-stu-id="6be6e-104">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6be6e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6be6e-105">Syntax</span></span>  
  
```cpp  
HRESULT NewParameterizedObject (  
    [in] ICorDebugFunction     *pConstructor,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6be6e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6be6e-106">Parameters</span></span>  

 `pConstructor`  
 <span data-ttu-id="6be6e-107">de Un puntero a un objeto ICorDebugFunction que representa el constructor del objeto del que se va a crear una instancia.</span><span class="sxs-lookup"><span data-stu-id="6be6e-107">[in] A pointer to an ICorDebugFunction object that represents the constructor of the object to be instantiated.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="6be6e-108">de El número de argumentos de tipo pasados.</span><span class="sxs-lookup"><span data-stu-id="6be6e-108">[in] The number of type arguments passed.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="6be6e-109">de Matriz de punteros, cada uno de los cuales señala a un objeto ICorDebugType que representa un argumento de tipo para el objeto del que se crea una instancia.</span><span class="sxs-lookup"><span data-stu-id="6be6e-109">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument for the object that is being instantiated.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="6be6e-110">de El número de argumentos pasados al constructor.</span><span class="sxs-lookup"><span data-stu-id="6be6e-110">[in] The number of arguments passed to the constructor.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="6be6e-111">de Matriz de punteros, cada uno de los cuales señala a un objeto ICorDebugValue que representa un valor de argumento que se pasa al constructor.</span><span class="sxs-lookup"><span data-stu-id="6be6e-111">[in] An array of pointers, each of which points to an ICorDebugValue object that represents an argument value that is passed to the constructor.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6be6e-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6be6e-112">Remarks</span></span>  

 <span data-ttu-id="6be6e-113">El constructor del objeto puede tomar <xref:System.Type> parámetros.</span><span class="sxs-lookup"><span data-stu-id="6be6e-113">The object's constructor may take <xref:System.Type> parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6be6e-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6be6e-114">Requirements</span></span>  

 <span data-ttu-id="6be6e-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6be6e-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6be6e-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6be6e-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6be6e-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6be6e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6be6e-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6be6e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
