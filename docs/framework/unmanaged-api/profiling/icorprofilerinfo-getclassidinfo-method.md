---
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
ms.openlocfilehash: 7d19a43048da742e702636faaa46ecf1458556f5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722598"
---
# <a name="icorprofilerinfogetclassidinfo-method"></a><span data-ttu-id="a6fe1-102">ICorProfilerInfo::GetClassIDInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="a6fe1-102">ICorProfilerInfo::GetClassIDInfo Method</span></span>

<span data-ttu-id="a6fe1-103">Obtiene el módulo primario y el token de metadatos para la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="a6fe1-103">Gets the parent module and the metadata token for the specified class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6fe1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a6fe1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassIDInfo(  
    [in]  ClassID   classId,  
    [out] ModuleID  *pModuleId,  
    [out] mdTypeDef *pTypeDefToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6fe1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a6fe1-105">Parameters</span></span>  

 `classId`  
 <span data-ttu-id="a6fe1-106">de IDENTIFICADOR de la clase para la que se va a obtener la información.</span><span class="sxs-lookup"><span data-stu-id="a6fe1-106">[in] The ID of the class for which to get the information.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="a6fe1-107">enuncia Puntero al identificador del módulo primario de la clase.</span><span class="sxs-lookup"><span data-stu-id="a6fe1-107">[out] A pointer to the ID of the parent module of the class.</span></span>  
  
 `pTypeDefToken`  
 <span data-ttu-id="a6fe1-108">enuncia Puntero al símbolo (token) de metadatos para la clase.</span><span class="sxs-lookup"><span data-stu-id="a6fe1-108">[out] A pointer to the metadata token for the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6fe1-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a6fe1-109">Remarks</span></span>  

 <span data-ttu-id="a6fe1-110">El código del generador de perfiles puede llamar a [ICorProfilerInfo:: GetModuleMetaData (](icorprofilerinfo-getmodulemetadata-method.md) para obtener una interfaz de metadatos para un módulo determinado.</span><span class="sxs-lookup"><span data-stu-id="a6fe1-110">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) to obtain a metadata interface for a given module.</span></span> <span data-ttu-id="a6fe1-111">Después, el token de metadatos que se devuelve a la ubicación a la que `pTypeDefToken` hace referencia puede usarse para acceder a los metadatos de la clase.</span><span class="sxs-lookup"><span data-stu-id="a6fe1-111">The metadata token that is returned to the location referenced by `pTypeDefToken` can then be used to access the metadata for the class.</span></span>  
  
 <span data-ttu-id="a6fe1-112">Para obtener más información sobre los tipos genéricos, use [ICorProfilerInfo2:: GetClassIDInfo2 (](icorprofilerinfo2-getclassidinfo2-method.md).</span><span class="sxs-lookup"><span data-stu-id="a6fe1-112">To get more information for generic types, use [ICorProfilerInfo2::GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6fe1-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a6fe1-113">Requirements</span></span>  

 <span data-ttu-id="a6fe1-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6fe1-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6fe1-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a6fe1-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a6fe1-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6fe1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6fe1-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6fe1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6fe1-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a6fe1-118">See also</span></span>

- [<span data-ttu-id="a6fe1-119">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a6fe1-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
