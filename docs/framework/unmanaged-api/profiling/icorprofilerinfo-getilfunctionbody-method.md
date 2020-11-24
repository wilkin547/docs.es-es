---
title: ICorProfilerInfo::GetILFunctionBody (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBody
helpviewer_keywords:
- GetILFunctionBody method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBody method [.NET Framework profiling]
ms.assetid: e29b46bc-5fdc-4894-b0c2-619df4b65ded
topic_type:
- apiref
ms.openlocfilehash: 337c4fd091ebf7c39f7eee2358ca4f4df239cce3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687533"
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a><span data-ttu-id="4ed83-102">ICorProfilerInfo::GetILFunctionBody (Método)</span><span class="sxs-lookup"><span data-stu-id="4ed83-102">ICorProfilerInfo::GetILFunctionBody Method</span></span>

<span data-ttu-id="4ed83-103">Obtiene un puntero al cuerpo de un método en el código del lenguaje intermedio de Microsoft (MSIL), comenzando en su encabezado.</span><span class="sxs-lookup"><span data-stu-id="4ed83-103">Gets a pointer to the body of a method in Microsoft intermediate language (MSIL) code, starting at its header.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ed83-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4ed83-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILFunctionBody(  
    [in]  ModuleID    moduleId,  
    [in]  mdMethodDef methodId,  
    [out] LPCBYTE     *ppMethodHeader,  
    [out] ULONG       *pcbMethodSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ed83-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4ed83-105">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="4ed83-106">de IDENTIFICADOR del módulo en el que reside la función.</span><span class="sxs-lookup"><span data-stu-id="4ed83-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodId`  
 <span data-ttu-id="4ed83-107">de Símbolo (token) de metadatos para el método.</span><span class="sxs-lookup"><span data-stu-id="4ed83-107">[in] The metadata token for the method.</span></span>  
  
 `ppMethodHeader`  
 <span data-ttu-id="4ed83-108">enuncia Puntero al encabezado del método.</span><span class="sxs-lookup"><span data-stu-id="4ed83-108">[out] A pointer to the method's header.</span></span>  
  
 `pcbMethodSize`  
 <span data-ttu-id="4ed83-109">enuncia Entero que especifica el tamaño del método.</span><span class="sxs-lookup"><span data-stu-id="4ed83-109">[out] An integer that specifies the size of the method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ed83-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4ed83-110">Remarks</span></span>  

 <span data-ttu-id="4ed83-111">Un método está en el ámbito del módulo en el que reside.</span><span class="sxs-lookup"><span data-stu-id="4ed83-111">A method is scoped by the module in which it lives.</span></span> <span data-ttu-id="4ed83-112">Dado que el `GetILFunctionBody` método está diseñado para proporcionar a una herramienta acceso al código MSIL antes de que lo haya cargado el Common Language Runtime (CLR), usa el token de metadatos del método para buscar la instancia deseada.</span><span class="sxs-lookup"><span data-stu-id="4ed83-112">Because the `GetILFunctionBody` method is designed to give a tool access to the MSIL code before it has been loaded by the common language runtime (CLR), it uses the metadata token of the method to find the desired instance.</span></span>  
  
 <span data-ttu-id="4ed83-113">`GetILFunctionBody` puede devolver un CORPROF_E_FUNCTION_NOT_IL HRESULT si `methodId` apunta a un método sin código MSIL (como un método abstracto o un método de invocación de plataforma (PInvoke)).</span><span class="sxs-lookup"><span data-stu-id="4ed83-113">`GetILFunctionBody` can return a CORPROF_E_FUNCTION_NOT_IL HRESULT if the `methodId` points to a method without any MSIL code (such as an abstract method, or a platform invoke (PInvoke) method).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ed83-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4ed83-114">Requirements</span></span>  

 <span data-ttu-id="4ed83-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ed83-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ed83-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4ed83-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4ed83-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ed83-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ed83-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ed83-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ed83-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4ed83-119">See also</span></span>

- [<span data-ttu-id="4ed83-120">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4ed83-120">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
