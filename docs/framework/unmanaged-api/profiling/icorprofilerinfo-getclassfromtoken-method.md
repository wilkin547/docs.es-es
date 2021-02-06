---
description: 'Más información acerca de: ICorProfilerInfo:: GetClassFromToken ((método)'
title: ICorProfilerInfo::GetClassFromToken (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromToken
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetClassFromToken method [.NET Framework profiling]
- GetClassFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0afc1197-2a5b-424f-8b82-9cb59a7e00db
topic_type:
- apiref
ms.openlocfilehash: 0460a9b767f29f108a2b290b848f4cc6b6394ecb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647757"
---
# <a name="icorprofilerinfogetclassfromtoken-method"></a><span data-ttu-id="772f6-103">ICorProfilerInfo::GetClassFromToken (Método)</span><span class="sxs-lookup"><span data-stu-id="772f6-103">ICorProfilerInfo::GetClassFromToken Method</span></span>

<span data-ttu-id="772f6-104">Obtiene el identificador de la clase, dado el token de metadatos.</span><span class="sxs-lookup"><span data-stu-id="772f6-104">Gets the ID of the class, given the metadata token.</span></span> <span data-ttu-id="772f6-105">Este método está obsoleto en la .NET Framework versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="772f6-105">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="772f6-106">Use [ICorProfilerInfo2:: GetClassFromTokenAndTypeArgs (](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="772f6-106">Use [ICorProfilerInfo2::GetClassFromTokenAndTypeArgs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="772f6-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="772f6-107">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  ModuleID  moduleId,  
    [in]  mdTypeDef typeDef,  
    [out] ClassID   *pClassId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="772f6-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="772f6-108">Parameters</span></span>  

 `moduleID`  
 <span data-ttu-id="772f6-109">de IDENTIFICADOR del módulo que contiene la clase.</span><span class="sxs-lookup"><span data-stu-id="772f6-109">[in] The ID of the module that contains the class.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="772f6-110">de `mdTypeDef` Token de metadatos que hace referencia a la clase.</span><span class="sxs-lookup"><span data-stu-id="772f6-110">[in] An `mdTypeDef` metadata token that references the class.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="772f6-111">enuncia Puntero al identificador de clase.</span><span class="sxs-lookup"><span data-stu-id="772f6-111">[out] A pointer to the class ID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="772f6-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="772f6-112">Remarks</span></span>  

 <span data-ttu-id="772f6-113">Este método está obsoleto; en su lugar, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` para todos los tipos.</span><span class="sxs-lookup"><span data-stu-id="772f6-113">This method is obsolete; instead, use `ICorProfilerInfo2::GetClassFromTokenAndTypeArgs` for all types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="772f6-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="772f6-114">Requirements</span></span>  

 <span data-ttu-id="772f6-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="772f6-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="772f6-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="772f6-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="772f6-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="772f6-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="772f6-118">**.NET Framework versiones:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="772f6-118">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="772f6-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="772f6-119">See also</span></span>

- [<span data-ttu-id="772f6-120">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="772f6-120">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
