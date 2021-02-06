---
description: 'Más información acerca de: ICorProfilerInfo:: GetModuleMetaData ((método)'
title: ICorProfilerInfo::GetModuleMetaData (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetModuleMetaData
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetModuleMetaData
helpviewer_keywords:
- GetModuleMetaData method [.NET Framework profiling]
- ICorProfilerInfo::GetModuleMetaData method [.NET Framework profiling]
ms.assetid: 7a439d92-348a-44dd-b60f-cad7cba56379
topic_type:
- apiref
ms.openlocfilehash: ff0fb0563b041fcb3cf63438874724c8236d6081
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647185"
---
# <a name="icorprofilerinfogetmodulemetadata-method"></a><span data-ttu-id="d5886-103">ICorProfilerInfo::GetModuleMetaData (Método)</span><span class="sxs-lookup"><span data-stu-id="d5886-103">ICorProfilerInfo::GetModuleMetaData Method</span></span>

<span data-ttu-id="d5886-104">Obtiene una instancia de la interfaz de metadatos que se asigna al módulo especificado.</span><span class="sxs-lookup"><span data-stu-id="d5886-104">Gets a metadata interface instance that maps to the specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5886-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d5886-105">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleMetaData(  
    [in]  ModuleID moduleId,  
    [in]  DWORD    dwOpenFlags,  
    [in]  REFIID   riid,  
    [out] IUnknown **ppOut);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5886-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d5886-106">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="d5886-107">de IDENTIFICADOR del módulo al que se asignará la instancia de interfaz.</span><span class="sxs-lookup"><span data-stu-id="d5886-107">[in] The ID of the module to which the interface instance will be mapped.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="d5886-108">de Un valor de la enumeración [CorOpenFlags (](../metadata/coropenflags-enumeration.md) que especifica el modo para abrir los archivos de manifiesto.</span><span class="sxs-lookup"><span data-stu-id="d5886-108">[in] A value of the [CorOpenFlags](../metadata/coropenflags-enumeration.md) enumeration that specifies the mode for opening manifest files.</span></span> <span data-ttu-id="d5886-109">Solo los `ofRead` `ofWrite` bits, y `ofNoTransform` son válidos.</span><span class="sxs-lookup"><span data-stu-id="d5886-109">Only the `ofRead`, `ofWrite` and `ofNoTransform` bits are valid.</span></span>  
  
 `riid`  
 <span data-ttu-id="d5886-110">de IDENTIFICADOR de referencia (GUID) de la interfaz de metadatos cuya instancia se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="d5886-110">[in] The reference ID (GUID) of the metadata interface whose instance will be retrieved.</span></span> <span data-ttu-id="d5886-111">Vea [interfaces de metadatos](../metadata/metadata-interfaces.md) para obtener una lista de las interfaces.</span><span class="sxs-lookup"><span data-stu-id="d5886-111">See [Metadata Interfaces](../metadata/metadata-interfaces.md) for a list of the interfaces.</span></span>  
  
 `ppOut`  
 <span data-ttu-id="d5886-112">enuncia Puntero a la dirección de la instancia de la interfaz de metadatos.</span><span class="sxs-lookup"><span data-stu-id="d5886-112">[out] A pointer to the address of the metadata interface instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5886-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d5886-113">Remarks</span></span>  

 <span data-ttu-id="d5886-114">Puede solicitar que los metadatos se abran en modo de lectura/escritura, pero esto hará que la ejecución del programa sea más lenta, ya que los cambios realizados en los metadatos no se pueden optimizar tal como estaban del compilador.</span><span class="sxs-lookup"><span data-stu-id="d5886-114">You may ask for the metadata to be opened in read/write mode, but this will result in slower metadata execution of the program, because changes made to the metadata cannot be optimized as they were from the compiler.</span></span>  
  
 <span data-ttu-id="d5886-115">Algunos módulos (como los módulos de recursos) no tienen metadatos.</span><span class="sxs-lookup"><span data-stu-id="d5886-115">Some modules (such as resource modules) have no metadata.</span></span> <span data-ttu-id="d5886-116">En esos casos, `GetModuleMetaData` devolverá un valor HRESULT de S_FALSE y un valor null en \* `ppOut` .</span><span class="sxs-lookup"><span data-stu-id="d5886-116">In those cases, `GetModuleMetaData` will return an HRESULT value of S_FALSE, and a null in \*`ppOut`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5886-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d5886-117">Requirements</span></span>  

 <span data-ttu-id="d5886-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5886-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5886-119">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d5886-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d5886-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5886-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5886-121">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5886-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5886-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5886-122">See also</span></span>

- [<span data-ttu-id="d5886-123">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d5886-123">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
