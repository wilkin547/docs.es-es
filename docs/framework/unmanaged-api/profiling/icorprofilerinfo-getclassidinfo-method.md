---
description: 'Más información acerca de: ICorProfilerInfo:: GetClassIDInfo ((método)'
title: ICorProfilerInfo::GetClassIDInfo (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassIDInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassIDInfo
helpviewer_keywords:
- GetClassIDInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetClassIDInfo method [.NET Framework profiling]
ms.assetid: 9e93b99e-5aca-415c-8e37-7f33753b612d
topic_type:
- apiref
ms.openlocfilehash: 05937580bd8bd672da16875964548829d071f4bf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647718"
---
# <a name="icorprofilerinfogetclassidinfo-method"></a><span data-ttu-id="9986b-103">ICorProfilerInfo::GetClassIDInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="9986b-103">ICorProfilerInfo::GetClassIDInfo Method</span></span>

<span data-ttu-id="9986b-104">Obtiene el módulo primario y el token de metadatos para la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="9986b-104">Gets the parent module and the metadata token for the specified class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9986b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9986b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetClassIDInfo(  
    [in]  ClassID   classId,  
    [out] ModuleID  *pModuleId,  
    [out] mdTypeDef *pTypeDefToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9986b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9986b-106">Parameters</span></span>  

 `classId`  
 <span data-ttu-id="9986b-107">de IDENTIFICADOR de la clase para la que se va a obtener la información.</span><span class="sxs-lookup"><span data-stu-id="9986b-107">[in] The ID of the class for which to get the information.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="9986b-108">enuncia Puntero al identificador del módulo primario de la clase.</span><span class="sxs-lookup"><span data-stu-id="9986b-108">[out] A pointer to the ID of the parent module of the class.</span></span>  
  
 `pTypeDefToken`  
 <span data-ttu-id="9986b-109">enuncia Puntero al símbolo (token) de metadatos para la clase.</span><span class="sxs-lookup"><span data-stu-id="9986b-109">[out] A pointer to the metadata token for the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9986b-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9986b-110">Remarks</span></span>  

 <span data-ttu-id="9986b-111">El código del generador de perfiles puede llamar a [ICorProfilerInfo:: GetModuleMetaData (](icorprofilerinfo-getmodulemetadata-method.md) para obtener una interfaz de metadatos para un módulo determinado.</span><span class="sxs-lookup"><span data-stu-id="9986b-111">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) to obtain a metadata interface for a given module.</span></span> <span data-ttu-id="9986b-112">Después, el token de metadatos que se devuelve a la ubicación a la que `pTypeDefToken` hace referencia puede usarse para acceder a los metadatos de la clase.</span><span class="sxs-lookup"><span data-stu-id="9986b-112">The metadata token that is returned to the location referenced by `pTypeDefToken` can then be used to access the metadata for the class.</span></span>  
  
 <span data-ttu-id="9986b-113">Para obtener más información sobre los tipos genéricos, use [ICorProfilerInfo2:: GetClassIDInfo2 (](icorprofilerinfo2-getclassidinfo2-method.md).</span><span class="sxs-lookup"><span data-stu-id="9986b-113">To get more information for generic types, use [ICorProfilerInfo2::GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9986b-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9986b-114">Requirements</span></span>  

 <span data-ttu-id="9986b-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9986b-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9986b-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9986b-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9986b-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9986b-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9986b-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9986b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9986b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="9986b-119">See also</span></span>

- [<span data-ttu-id="9986b-120">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9986b-120">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
