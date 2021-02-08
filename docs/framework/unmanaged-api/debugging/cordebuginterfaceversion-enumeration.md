---
description: 'Más información sobre: enumeración CorDebugInterfaceVersion ('
title: CorDebugInterfaceVersion (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugInterfaceVersion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugInterfaceVersion
helpviewer_keywords:
- CorDebugInterfaceVersion enumeration [.NET Framework debugging]
ms.assetid: 7d1e6cd9-2a15-41c6-9b68-008705a4ed90
topic_type:
- apiref
ms.openlocfilehash: 35b8fd6eae2b7999d7669632506cfea43dffbd45
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801649"
---
# <a name="cordebuginterfaceversion-enumeration"></a><span data-ttu-id="3affc-103">CorDebugInterfaceVersion (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="3affc-103">CorDebugInterfaceVersion Enumeration</span></span>

<span data-ttu-id="3affc-104">Especifica una interfaz, una versión de .NET Framework, o la versión de .NET Framework en la que se incorporó una interfaz.</span><span class="sxs-lookup"><span data-stu-id="3affc-104">Specifies an interface, a version of the .NET Framework, or a version of the .NET Framework in which an interface was introduced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3affc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3affc-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugInterfaceVersion {  
  
    CorDebugInvalidVersion            = 0,  
    CorDebugVersion_1_0               = CorDebugInvalidVersion + 1,  
  
    ver_ICorDebugManagedCallback      = CorDebugVersion_1_0,  
    ver_ICorDebugUnmanagedCallback    = CorDebugVersion_1_0,  
    ver_ICorDebug                     = CorDebugVersion_1_0,  
    ver_ICorDebugController           = CorDebugVersion_1_0,  
    ver_ICorDebugAppDomain            = CorDebugVersion_1_0,  
    ver_ICorDebugAssembly             = CorDebugVersion_1_0,  
    ver_ICorDebugProcess              = CorDebugVersion_1_0,  
    ver_ICorDebugBreakpoint           = CorDebugVersion_1_0,  
    ver_ICorDebugFunctionBreakpoint   = CorDebugVersion_1_0,  
    ver_ICorDebugModuleBreakpoint     = CorDebugVersion_1_0,  
    ver_ICorDebugValueBreakpoint      = CorDebugVersion_1_0,  
    ver_ICorDebugStepper              = CorDebugVersion_1_0,  
    ver_ICorDebugRegisterSet          = CorDebugVersion_1_0,  
    ver_ICorDebugThread               = CorDebugVersion_1_0,  
    ver_ICorDebugChain                = CorDebugVersion_1_0,  
    ver_ICorDebugFrame                = CorDebugVersion_1_0,  
    ver_ICorDebugILFrame              = CorDebugVersion_1_0,  
    ver_ICorDebugNativeFrame          = CorDebugVersion_1_0,  
    ver_ICorDebugModule               = CorDebugVersion_1_0,  
    ver_ICorDebugFunction             = CorDebugVersion_1_0,  
    ver_ICorDebugCode                 = CorDebugVersion_1_0,  
    ver_ICorDebugClass                = CorDebugVersion_1_0,  
    ver_ICorDebugEval                 = CorDebugVersion_1_0,  
    ver_ICorDebugValue                = CorDebugVersion_1_0,  
    ver_ICorDebugGenericValue         = CorDebugVersion_1_0,  
    ver_ICorDebugReferenceValue       = CorDebugVersion_1_0,  
    ver_ICorDebugHeapValue            = CorDebugVersion_1_0,  
    ver_ICorDebugObjectValue          = CorDebugVersion_1_0,  
    ver_ICorDebugBoxValue             = CorDebugVersion_1_0,  
    ver_ICorDebugStringValue          = CorDebugVersion_1_0,  
    ver_ICorDebugArrayValue           = CorDebugVersion_1_0,  
    ver_ICorDebugContext              = CorDebugVersion_1_0,  
    ver_ICorDebugEnum                 = CorDebugVersion_1_0,  
    ver_ICorDebugObjectEnum           = CorDebugVersion_1_0,  
    ver_ICorDebugBreakpointEnum       = CorDebugVersion_1_0,  
    ver_ICorDebugStepperEnum          = CorDebugVersion_1_0,  
    ver_ICorDebugProcessEnum          = CorDebugVersion_1_0,  
    ver_ICorDebugThreadEnum           = CorDebugVersion_1_0,  
    ver_ICorDebugFrameEnum            = CorDebugVersion_1_0,  
    ver_ICorDebugChainEnum            = CorDebugVersion_1_0,  
    ver_ICorDebugModuleEnum           = CorDebugVersion_1_0,  
    ver_ICorDebugValueEnum            = CorDebugVersion_1_0,  
    ver_ICorDebugCodeEnum             = CorDebugVersion_1_0,  
    ver_ICorDebugTypeEnum             = CorDebugVersion_1_0,  
    ver_ICorDebugErrorInfoEnum        = CorDebugVersion_1_0,  
    ver_ICorDebugAppDomainEnum        = CorDebugVersion_1_0,  
    ver_ICorDebugAssemblyEnum         = CorDebugVersion_1_0,  
    ver_ICorDebugEditAndContinueErrorInfo
                                      = CorDebugVersion_1_0,  
    ver_ICorDebugEditAndContinueSnapshot
                                      = CorDebugVersion_1_0,  
  
    CorDebugVersion_1_1               = CorDebugVersion_1_0 + 1,  
    // No interface definitions in version 1.1.  
  
    CorDebugVersion_2_0 = CorDebugVersion_1_1 + 1,  
  
    ver_ICorDebugManagedCallback2    = CorDebugVersion_2_0,  
    ver_ICorDebugAppDomain2          = CorDebugVersion_2_0,  
    ver_ICorDebugProcess2            = CorDebugVersion_2_0,  
    ver_ICorDebugStepper2            = CorDebugVersion_2_0,  
    ver_ICorDebugRegisterSet2        = CorDebugVersion_2_0,  
    ver_ICorDebugThread2             = CorDebugVersion_2_0,  
    ver_ICorDebugILFrame2            = CorDebugVersion_2_0,  
    ver_ICorDebugModule2             = CorDebugVersion_2_0,  
    ver_ICorDebugFunction2           = CorDebugVersion_2_0,  
    ver_ICorDebugCode2               = CorDebugVersion_2_0,  
    ver_ICorDebugClass2              = CorDebugVersion_2_0,  
    ver_ICorDebugValue2              = CorDebugVersion_2_0,  
    ver_ICorDebugEval2               = CorDebugVersion_2_0,  
    ver_ICorDebugObjectValue2        = CorDebugVersion_2_0,  
  
    // CLR v4 - next major CLR version after CLR v2  
    // Includes Silverlight 4  
    CorDebugVersion_4_0 = CorDebugVersion_2_0 + 1,  
  
    ver_ICorDebugThread3             = CorDebugVersion_4_0,  
    ver_ICorDebugThread4             = CorDebugVersion_4_0,  
    ver_ICorDebugStackWalk           = CorDebugVersion_4_0,  
    ver_ICorDebugNativeFrame2        = CorDebugVersion_4_0,  
    ver_ICorDebugInternalFrame2      = CorDebugVersion_4_0,  
    ver_ICorDebugRuntimeUnwindableFrame = CorDebugVersion_4_0,  
    ver_ICorDebugHeapValue3          = CorDebugVersion_4_0,  
    ver_ICorDebugBlockingObjectEnum  = CorDebugVersion_4_0,  
    ver_ICorDebugValue3 = CorDebugVersion_4_0,  
  
    CorDebugVersion_4_5 = CorDebugVersion_4_0 + 1,  
  
    ver_ICorDebugComObjectValue = CorDebugVersion_4_5,  
    ver_ICorDebugAppDomain3 = CorDebugVersion_4_5,  
    ver_ICorDebugCode3 = CorDebugVersion_4_5,  
    ver_ICorDebugILFrame3 = CorDebugVersion_4_5,  
  
    CorDebugLatestVersion = CorDebugVersion_4_5  
  
} CorDebugInterfaceVersion;  
```  
  
## <a name="members"></a><span data-ttu-id="3affc-106">Members</span><span class="sxs-lookup"><span data-stu-id="3affc-106">Members</span></span>  

 <span data-ttu-id="3affc-107">En la tabla siguiente se incluyen vínculos de cada valor de enumeración a la interfaz correspondiente.</span><span class="sxs-lookup"><span data-stu-id="3affc-107">The following table provides links from each enumeration value to the corresponding interface.</span></span> <span data-ttu-id="3affc-108">Además, la tabla indica la primera versión de .NET Framework en la que se admitía la interfaz.</span><span class="sxs-lookup"><span data-stu-id="3affc-108">In addition, the table indicates the first version of the .NET Framework that the interface was supported in.</span></span>  
  
|<span data-ttu-id="3affc-109">Miembro</span><span class="sxs-lookup"><span data-stu-id="3affc-109">Member</span></span>|<span data-ttu-id="3affc-110">Especifica</span><span class="sxs-lookup"><span data-stu-id="3affc-110">Specifies</span></span>|<span data-ttu-id="3affc-111">Versión de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3affc-111">.NET Framework version</span></span>|  
|------------|---------------|----------------------------|  
|`CorDebugInvalidVersion`|<span data-ttu-id="3affc-112">La versión de .NET Framework no es válida.</span><span class="sxs-lookup"><span data-stu-id="3affc-112">The version of the .NET Framework is invalid.</span></span>|-|  
|`CorDebugVersion_1_0`|<span data-ttu-id="3affc-113">La versión de .NET Framework, incluidos todos sus Service Packs, es 1.0.</span><span class="sxs-lookup"><span data-stu-id="3affc-113">The version of the .NET Framework, including all its service packs, is 1.0.</span></span>|<span data-ttu-id="3affc-114">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-114">1.0</span></span>|  
|`CorDebugVersion_1_1`|<span data-ttu-id="3affc-115">La versión de .NET Framework, incluidos todos los Service Packs, es 1.1.</span><span class="sxs-lookup"><span data-stu-id="3affc-115">The version of the .NET Framework, including all service packs, is 1.1.</span></span>|<span data-ttu-id="3affc-116">1.1</span><span class="sxs-lookup"><span data-stu-id="3affc-116">1.1</span></span>|  
|`CorDebugVersion_2_0`|<span data-ttu-id="3affc-117">La versión de .NET Framework, incluidos todos los Service Packs, es 2,0.</span><span class="sxs-lookup"><span data-stu-id="3affc-117">The version of the .NET Framework, including all service packs, is 2.0.</span></span>|<span data-ttu-id="3affc-118">2.0</span><span class="sxs-lookup"><span data-stu-id="3affc-118">2.0</span></span>|  
|`CorDebugVersion_4_0`|<span data-ttu-id="3affc-119">La versión de .NET Framework, incluidos todos los Service Packs, es 4.</span><span class="sxs-lookup"><span data-stu-id="3affc-119">The version of the .NET Framework, including all service packs, is 4.</span></span>|<span data-ttu-id="3affc-120">4</span><span class="sxs-lookup"><span data-stu-id="3affc-120">4</span></span>|  
|`CorDebugVersion_4_5`|<span data-ttu-id="3affc-121">La versión de .NET Framework, incluidos todos los Service Packs, es 4,5.</span><span class="sxs-lookup"><span data-stu-id="3affc-121">The version of the .NET Framework, including all service packs, is 4.5.</span></span>|<span data-ttu-id="3affc-122">4.5.</span><span class="sxs-lookup"><span data-stu-id="3affc-122">4.5</span></span>|  
|`ver_ICorDebugManagedCallback`|[<span data-ttu-id="3affc-123">ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="3affc-123">ICorDebugManagedCallback</span></span>](icordebugmanagedcallback-interface.md)|<span data-ttu-id="3affc-124">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-124">1.0</span></span>|  
|`ver_ICorDebugUnmanagedCallback`|[<span data-ttu-id="3affc-125">ICorDebugUnmanagedCallback</span><span class="sxs-lookup"><span data-stu-id="3affc-125">ICorDebugUnmanagedCallback</span></span>](icordebugunmanagedcallback-interface.md)|<span data-ttu-id="3affc-126">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-126">1.0</span></span>|  
|`ver_ICorDebug`|[<span data-ttu-id="3affc-127">ICorDebug</span><span class="sxs-lookup"><span data-stu-id="3affc-127">ICorDebug</span></span>](icordebug-interface.md)|<span data-ttu-id="3affc-128">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-128">1.0</span></span>|  
|`ver_ICorDebugController`|[<span data-ttu-id="3affc-129">ICorDebugController</span><span class="sxs-lookup"><span data-stu-id="3affc-129">ICorDebugController</span></span>](icordebugcontroller-interface.md)|<span data-ttu-id="3affc-130">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-130">1.0</span></span>|  
|`ver_ICorDebugAppDomain`|[<span data-ttu-id="3affc-131">ICorDebugAppDomain</span><span class="sxs-lookup"><span data-stu-id="3affc-131">ICorDebugAppDomain</span></span>](icordebugappdomain-interface.md)|<span data-ttu-id="3affc-132">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-132">1.0</span></span>|  
|`ver_ICorDebugAssembly`|[<span data-ttu-id="3affc-133">ICorDebugAssembly</span><span class="sxs-lookup"><span data-stu-id="3affc-133">ICorDebugAssembly</span></span>](icordebugassembly-interface.md)|<span data-ttu-id="3affc-134">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-134">1.0</span></span>|  
|`ver_ICorDebugProcess`|[<span data-ttu-id="3affc-135">ICorDebugProcess</span><span class="sxs-lookup"><span data-stu-id="3affc-135">ICorDebugProcess</span></span>](icordebugprocess-interface.md)|<span data-ttu-id="3affc-136">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-136">1.0</span></span>|  
|`ver_ICorDebugBreakpoint`|[<span data-ttu-id="3affc-137">ICorDebugBreakpoint</span><span class="sxs-lookup"><span data-stu-id="3affc-137">ICorDebugBreakpoint</span></span>](icordebugbreakpoint-interface.md)|<span data-ttu-id="3affc-138">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-138">1.0</span></span>|  
|`ver_ICorDebugFunctionBreakpoint`|[<span data-ttu-id="3affc-139">ICorDebugFunctionBreakpoint</span><span class="sxs-lookup"><span data-stu-id="3affc-139">ICorDebugFunctionBreakpoint</span></span>](icordebugfunctionbreakpoint-interface.md)|<span data-ttu-id="3affc-140">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-140">1.0</span></span>|  
|`ver_ICorDebugModuleBreakpoint`|[<span data-ttu-id="3affc-141">ICorDebugModuleBreakpoint</span><span class="sxs-lookup"><span data-stu-id="3affc-141">ICorDebugModuleBreakpoint</span></span>](icordebugmodulebreakpoint-interface.md)|<span data-ttu-id="3affc-142">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-142">1.0</span></span>|  
|`ver_ICorDebugValueBreakpoint`|[<span data-ttu-id="3affc-143">Icordebugvaluebreakpoint (</span><span class="sxs-lookup"><span data-stu-id="3affc-143">ICorDebugValueBreakpoint</span></span>](icordebugvaluebreakpoint-interface.md)|<span data-ttu-id="3affc-144">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-144">1.0</span></span>|  
|`ver_ICorDebugStepper`|[<span data-ttu-id="3affc-145">ICorDebugStepper</span><span class="sxs-lookup"><span data-stu-id="3affc-145">ICorDebugStepper</span></span>](icordebugstepper-interface.md)|<span data-ttu-id="3affc-146">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-146">1.0</span></span>|  
|`ver_ICorDebugRegisterSet`|[<span data-ttu-id="3affc-147">ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="3affc-147">ICorDebugRegisterSet</span></span>](icordebugregisterset-interface.md)|<span data-ttu-id="3affc-148">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-148">1.0</span></span>|  
|`ver_ICorDebugThread`|[<span data-ttu-id="3affc-149">ICorDebugThread</span><span class="sxs-lookup"><span data-stu-id="3affc-149">ICorDebugThread</span></span>](icordebugthread-interface.md)|<span data-ttu-id="3affc-150">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-150">1.0</span></span>|  
|`ver_ICorDebugChain`|[<span data-ttu-id="3affc-151">ICorDebugChain</span><span class="sxs-lookup"><span data-stu-id="3affc-151">ICorDebugChain</span></span>](icordebugchain-interface.md)|<span data-ttu-id="3affc-152">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-152">1.0</span></span>|  
|`ver_ICorDebugFrame`|[<span data-ttu-id="3affc-153">ICorDebugFrame</span><span class="sxs-lookup"><span data-stu-id="3affc-153">ICorDebugFrame</span></span>](icordebugframe-interface.md)|<span data-ttu-id="3affc-154">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-154">1.0</span></span>|  
|`ver_ICorDebugILFrame`|[<span data-ttu-id="3affc-155">ICorDebugILFrame</span><span class="sxs-lookup"><span data-stu-id="3affc-155">ICorDebugILFrame</span></span>](icordebugilframe-interface.md)|<span data-ttu-id="3affc-156">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-156">1.0</span></span>|  
|`ver_ICorDebugNativeFrame`|[<span data-ttu-id="3affc-157">ICorDebugNativeFrame</span><span class="sxs-lookup"><span data-stu-id="3affc-157">ICorDebugNativeFrame</span></span>](icordebugnativeframe-interface.md)|<span data-ttu-id="3affc-158">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-158">1.0</span></span>|  
|`ver_ICorDebugModule`|[<span data-ttu-id="3affc-159">ICorDebugModule</span><span class="sxs-lookup"><span data-stu-id="3affc-159">ICorDebugModule</span></span>](icordebugmodule-interface.md)|<span data-ttu-id="3affc-160">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-160">1.0</span></span>|  
|`ver_ICorDebugFunction`|[<span data-ttu-id="3affc-161">ICorDebugFunction</span><span class="sxs-lookup"><span data-stu-id="3affc-161">ICorDebugFunction</span></span>](icordebugfunction-interface1.md)|<span data-ttu-id="3affc-162">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-162">1.0</span></span>|  
|`ver_ICorDebugCode`|[<span data-ttu-id="3affc-163">ICorDebugCode</span><span class="sxs-lookup"><span data-stu-id="3affc-163">ICorDebugCode</span></span>](icordebugcode-interface1.md)|<span data-ttu-id="3affc-164">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-164">1.0</span></span>|  
|`ver_ICorDebugClass`|[<span data-ttu-id="3affc-165">ICorDebugClass</span><span class="sxs-lookup"><span data-stu-id="3affc-165">ICorDebugClass</span></span>](icordebugclass-interface.md)|<span data-ttu-id="3affc-166">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-166">1.0</span></span>|  
|`ver_ICorDebugEval`|[<span data-ttu-id="3affc-167">ICorDebugEval</span><span class="sxs-lookup"><span data-stu-id="3affc-167">ICorDebugEval</span></span>](icordebugeval-interface.md)|<span data-ttu-id="3affc-168">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-168">1.0</span></span>|  
|`ver_ICorDebugValue`|[<span data-ttu-id="3affc-169">ICorDebugValue</span><span class="sxs-lookup"><span data-stu-id="3affc-169">ICorDebugValue</span></span>](icordebugvalue-interface.md)|<span data-ttu-id="3affc-170">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-170">1.0</span></span>|  
|`ver_ICorDebugGenericValue`|[<span data-ttu-id="3affc-171">ICorDebugGenericValue</span><span class="sxs-lookup"><span data-stu-id="3affc-171">ICorDebugGenericValue</span></span>](icordebuggenericvalue-interface.md)|<span data-ttu-id="3affc-172">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-172">1.0</span></span>|  
|`ver_ICorDebugReferenceValue`|[<span data-ttu-id="3affc-173">ICorDebugReferenceValue</span><span class="sxs-lookup"><span data-stu-id="3affc-173">ICorDebugReferenceValue</span></span>](icordebugreferencevalue-interface.md)|<span data-ttu-id="3affc-174">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-174">1.0</span></span>|  
|`ver_ICorDebugHeapValue`|[<span data-ttu-id="3affc-175">ICorDebugHeapValue</span><span class="sxs-lookup"><span data-stu-id="3affc-175">ICorDebugHeapValue</span></span>](icordebugheapvalue-interface.md)|<span data-ttu-id="3affc-176">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-176">1.0</span></span>|  
|`ver_ICorDebugObjectValue`|[<span data-ttu-id="3affc-177">ICorDebugObjectValue</span><span class="sxs-lookup"><span data-stu-id="3affc-177">ICorDebugObjectValue</span></span>](icordebugobjectvalue-interface.md)|<span data-ttu-id="3affc-178">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-178">1.0</span></span>|  
|`ver_ICorDebugBoxValue`|[<span data-ttu-id="3affc-179">ICorDebugBoxValue</span><span class="sxs-lookup"><span data-stu-id="3affc-179">ICorDebugBoxValue</span></span>](icordebugboxvalue-interface.md)|<span data-ttu-id="3affc-180">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-180">1.0</span></span>|  
|`ver_ICorDebugStringValue`|[<span data-ttu-id="3affc-181">ICorDebugStringValue</span><span class="sxs-lookup"><span data-stu-id="3affc-181">ICorDebugStringValue</span></span>](icordebugstringvalue-interface.md)|<span data-ttu-id="3affc-182">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-182">1.0</span></span>|  
|`ver_ICorDebugArrayValue`|[<span data-ttu-id="3affc-183">ICorDebugArrayValue</span><span class="sxs-lookup"><span data-stu-id="3affc-183">ICorDebugArrayValue</span></span>](icordebugarrayvalue-interface.md)|<span data-ttu-id="3affc-184">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-184">1.0</span></span>|  
|`ver_ICorDebugContext`|[<span data-ttu-id="3affc-185">ICorDebugContext</span><span class="sxs-lookup"><span data-stu-id="3affc-185">ICorDebugContext</span></span>](icordebugcontext-interface.md)|<span data-ttu-id="3affc-186">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-186">1.0</span></span>|  
|`ver_ICorDebugEnum`|[<span data-ttu-id="3affc-187">ICorDebugEnum</span><span class="sxs-lookup"><span data-stu-id="3affc-187">ICorDebugEnum</span></span>](icordebugenum-interface1.md)|<span data-ttu-id="3affc-188">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-188">1.0</span></span>|  
|`ver_ICorDebugObjectEnum`|[<span data-ttu-id="3affc-189">ICorDebugObjectEnum</span><span class="sxs-lookup"><span data-stu-id="3affc-189">ICorDebugObjectEnum</span></span>](icordebugobjectenum-interface.md)|<span data-ttu-id="3affc-190">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-190">1.0</span></span>|  
|`ver_ICorDebugBreakpointEnum`|[<span data-ttu-id="3affc-191">ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="3affc-191">ICorDebugBreakpointEnum</span></span>](icordebugbreakpointenum-interface.md)|<span data-ttu-id="3affc-192">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-192">1.0</span></span>|  
|`ver_ICorDebugStepperEnum`|[<span data-ttu-id="3affc-193">ICorDebugStepperEnum</span><span class="sxs-lookup"><span data-stu-id="3affc-193">ICorDebugStepperEnum</span></span>](icordebugstepperenum-interface.md)|<span data-ttu-id="3affc-194">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-194">1.0</span></span>|  
|`ver_ICorDebugProcessEnum`|[<span data-ttu-id="3affc-195">ICorDebugProcessEnum</span><span class="sxs-lookup"><span data-stu-id="3affc-195">ICorDebugProcessEnum</span></span>](icordebugprocessenum-interface.md)|<span data-ttu-id="3affc-196">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-196">1.0</span></span>|  
|`ver_ICorDebugThreadEnum`|[<span data-ttu-id="3affc-197">ICorDebugThreadEnum (</span><span class="sxs-lookup"><span data-stu-id="3affc-197">ICorDebugThreadEnum</span></span>](icordebugthreadenum-interface1.md)|<span data-ttu-id="3affc-198">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-198">1.0</span></span>|  
|`ver_ICorDebugFrameEnum`|[<span data-ttu-id="3affc-199">ICorDebugFrameEnum</span><span class="sxs-lookup"><span data-stu-id="3affc-199">ICorDebugFrameEnum</span></span>](icordebugframeenum-interface.md)|<span data-ttu-id="3affc-200">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-200">1.0</span></span>|  
|`ver_ICorDebugChainEnum`|[<span data-ttu-id="3affc-201">ICorDebugChainEnum</span><span class="sxs-lookup"><span data-stu-id="3affc-201">ICorDebugChainEnum</span></span>](icordebugchainenum-interface.md)|<span data-ttu-id="3affc-202">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-202">1.0</span></span>|  
|`ver_ICorDebugModuleEnum`|[<span data-ttu-id="3affc-203">ICorDebugModuleEnum</span><span class="sxs-lookup"><span data-stu-id="3affc-203">ICorDebugModuleEnum</span></span>](icordebugmoduleenum-interface.md)|<span data-ttu-id="3affc-204">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-204">1.0</span></span>|  
|`ver_ICorDebugValueEnum`|[<span data-ttu-id="3affc-205">ICorDebugValueEnum</span><span class="sxs-lookup"><span data-stu-id="3affc-205">ICorDebugValueEnum</span></span>](icordebugvalueenum-interface.md)|<span data-ttu-id="3affc-206">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-206">1.0</span></span>|  
|`ver_ICorDebugCodeEnum`|[<span data-ttu-id="3affc-207">ICorDebugCodeEnum</span><span class="sxs-lookup"><span data-stu-id="3affc-207">ICorDebugCodeEnum</span></span>](icordebugcodeenum-interface.md)|<span data-ttu-id="3affc-208">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-208">1.0</span></span>|  
|`ver_ICorDebugTypeEnum`|[<span data-ttu-id="3affc-209">ICorDebugTypeEnum</span><span class="sxs-lookup"><span data-stu-id="3affc-209">ICorDebugTypeEnum</span></span>](icordebugtypeenum-interface.md)|<span data-ttu-id="3affc-210">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-210">1.0</span></span>|  
|`ver_ICorDebugErrorInfoEnum`|[<span data-ttu-id="3affc-211">ICorDebugErrorInfoEnum</span><span class="sxs-lookup"><span data-stu-id="3affc-211">ICorDebugErrorInfoEnum</span></span>](icordebugerrorinfoenum-interface.md)|<span data-ttu-id="3affc-212">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-212">1.0</span></span>|  
|`ver_ICorDebugAppDomainEnum`|[<span data-ttu-id="3affc-213">ICorDebugAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="3affc-213">ICorDebugAppDomainEnum</span></span>](icordebugappdomainenum-interface.md)|<span data-ttu-id="3affc-214">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-214">1.0</span></span>|  
|`ver_ICorDebugAssemblyEnum`|[<span data-ttu-id="3affc-215">ICorDebugAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="3affc-215">ICorDebugAssemblyEnum</span></span>](icordebugassemblyenum-interface.md)|<span data-ttu-id="3affc-216">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-216">1.0</span></span>|  
|`ver_ICorDebugEditAndContinueErrorInfo`|[<span data-ttu-id="3affc-217">ICorDebugEditAndContinueErrorInfo</span><span class="sxs-lookup"><span data-stu-id="3affc-217">ICorDebugEditAndContinueErrorInfo</span></span>](icordebugeditandcontinueerrorinfo-interface.md)|<span data-ttu-id="3affc-218">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-218">1.0</span></span>|  
|`ver_ICorDebugEditAndContinueSnapshot`|[<span data-ttu-id="3affc-219">ICorDebugEditAndContinueSnapshot</span><span class="sxs-lookup"><span data-stu-id="3affc-219">ICorDebugEditAndContinueSnapshot</span></span>](icordebugeditandcontinuesnapshot-interface.md)|<span data-ttu-id="3affc-220">1.0</span><span class="sxs-lookup"><span data-stu-id="3affc-220">1.0</span></span>|  
|`ver_ICorDebugManagedCallback2`|[<span data-ttu-id="3affc-221">ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="3affc-221">ICorDebugManagedCallback2</span></span>](icordebugmanagedcallback2-interface.md)|<span data-ttu-id="3affc-222">2.0</span><span class="sxs-lookup"><span data-stu-id="3affc-222">2.0</span></span>|  
|`ver_ICorDebugAppDomain2`|[<span data-ttu-id="3affc-223">ICorDebugAppDomain2</span><span class="sxs-lookup"><span data-stu-id="3affc-223">ICorDebugAppDomain2</span></span>](icordebugappdomain2-interface.md)|<span data-ttu-id="3affc-224">2.0</span><span class="sxs-lookup"><span data-stu-id="3affc-224">2.0</span></span>|  
|`ver_ICorDebugProcess2`|[<span data-ttu-id="3affc-225">ICorDebugProcess2</span><span class="sxs-lookup"><span data-stu-id="3affc-225">ICorDebugProcess2</span></span>](icordebugprocess2-interface1.md)|<span data-ttu-id="3affc-226">2.0</span><span class="sxs-lookup"><span data-stu-id="3affc-226">2.0</span></span>|  
|`ver_ICorDebugStepper2`|[<span data-ttu-id="3affc-227">ICorDebugStepper2</span><span class="sxs-lookup"><span data-stu-id="3affc-227">ICorDebugStepper2</span></span>](icordebugstepper2-interface1.md)|<span data-ttu-id="3affc-228">2.0</span><span class="sxs-lookup"><span data-stu-id="3affc-228">2.0</span></span>|  
|`ver_ICorDebugRegisterSet2`|[<span data-ttu-id="3affc-229">ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="3affc-229">ICorDebugRegisterSet2</span></span>](icordebugregisterset2-interface.md)|<span data-ttu-id="3affc-230">2.0</span><span class="sxs-lookup"><span data-stu-id="3affc-230">2.0</span></span>|  
|`ver_ICorDebugThread2`|[<span data-ttu-id="3affc-231">ICorDebugThread2</span><span class="sxs-lookup"><span data-stu-id="3affc-231">ICorDebugThread2</span></span>](icordebugthread2-interface.md)|<span data-ttu-id="3affc-232">2.0</span><span class="sxs-lookup"><span data-stu-id="3affc-232">2.0</span></span>|  
|`ver_ICorDebugILFrame2`|[<span data-ttu-id="3affc-233">ICorDebugILFrame2</span><span class="sxs-lookup"><span data-stu-id="3affc-233">ICorDebugILFrame2</span></span>](icordebugilframe2-interface.md)|<span data-ttu-id="3affc-234">2.0</span><span class="sxs-lookup"><span data-stu-id="3affc-234">2.0</span></span>|  
|`ver_ICorDebugModule2`|[<span data-ttu-id="3affc-235">ICorDebugModule2</span><span class="sxs-lookup"><span data-stu-id="3affc-235">ICorDebugModule2</span></span>](icordebugmodule2-interface.md)|<span data-ttu-id="3affc-236">2.0</span><span class="sxs-lookup"><span data-stu-id="3affc-236">2.0</span></span>|  
|`ver_ICorDebugFunction2`|[<span data-ttu-id="3affc-237">ICorDebugFunction2</span><span class="sxs-lookup"><span data-stu-id="3affc-237">ICorDebugFunction2</span></span>](icordebugfunction2-interface.md)|<span data-ttu-id="3affc-238">2.0</span><span class="sxs-lookup"><span data-stu-id="3affc-238">2.0</span></span>|  
|`ver_ICorDebugCode2`|[<span data-ttu-id="3affc-239">ICorDebugCode2</span><span class="sxs-lookup"><span data-stu-id="3affc-239">ICorDebugCode2</span></span>](icordebugcode2-interface.md)|<span data-ttu-id="3affc-240">2.0</span><span class="sxs-lookup"><span data-stu-id="3affc-240">2.0</span></span>|  
|`ver_ICorDebugClass2`|<span data-ttu-id="3affc-241">ICorDebugClass2</span><span class="sxs-lookup"><span data-stu-id="3affc-241">"ICorDebugClass2"</span></span>|<span data-ttu-id="3affc-242">2.0</span><span class="sxs-lookup"><span data-stu-id="3affc-242">2.0</span></span>|  
|`ver_ICorDebugValue2`|<span data-ttu-id="3affc-243">ICorDebugValue2</span><span class="sxs-lookup"><span data-stu-id="3affc-243">"ICorDebugValue2"</span></span>|<span data-ttu-id="3affc-244">2.0</span><span class="sxs-lookup"><span data-stu-id="3affc-244">2.0</span></span>|  
|`ver_ICorDebugEval2`|<span data-ttu-id="3affc-245">"ICorDebugEval2".</span><span class="sxs-lookup"><span data-stu-id="3affc-245">The "ICorDebugEval2".</span></span>|<span data-ttu-id="3affc-246">2.0</span><span class="sxs-lookup"><span data-stu-id="3affc-246">2.0</span></span>|  
|`ver_ICorDebugObjectValue2`|<span data-ttu-id="3affc-247">Icordebugobjectvalue2 (</span><span class="sxs-lookup"><span data-stu-id="3affc-247">"ICorDebugObjectValue2"</span></span>|<span data-ttu-id="3affc-248">2.0</span><span class="sxs-lookup"><span data-stu-id="3affc-248">2.0</span></span>|  
|`ver_ICorDebugThread3`|[<span data-ttu-id="3affc-249">ICorDebugThread3</span><span class="sxs-lookup"><span data-stu-id="3affc-249">ICorDebugThread3</span></span>](icordebugthread3-interface.md)|<span data-ttu-id="3affc-250">4</span><span class="sxs-lookup"><span data-stu-id="3affc-250">4</span></span>|  
|`ver_ICorDebugThread4`|[<span data-ttu-id="3affc-251">ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="3affc-251">ICorDebugThread4</span></span>](icordebugthread4-interface.md)|<span data-ttu-id="3affc-252">4</span><span class="sxs-lookup"><span data-stu-id="3affc-252">4</span></span>|  
|`ver_ICorDebugStackWalk`|[<span data-ttu-id="3affc-253">ICorDebugStackWalk</span><span class="sxs-lookup"><span data-stu-id="3affc-253">ICorDebugStackWalk</span></span>](icordebugstackwalk-interface.md)|<span data-ttu-id="3affc-254">4</span><span class="sxs-lookup"><span data-stu-id="3affc-254">4</span></span>|  
|`ver_ICorDebugNativeFrame2`|[<span data-ttu-id="3affc-255">ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="3affc-255">ICorDebugNativeFrame2</span></span>](icordebugnativeframe2-interface.md)|<span data-ttu-id="3affc-256">4</span><span class="sxs-lookup"><span data-stu-id="3affc-256">4</span></span>|  
|`ver_ICorDebugInternalFrame2`|[<span data-ttu-id="3affc-257">ICorDebugInternalFrame2</span><span class="sxs-lookup"><span data-stu-id="3affc-257">ICorDebugInternalFrame2</span></span>](icordebuginternalframe2-interface.md)|<span data-ttu-id="3affc-258">4</span><span class="sxs-lookup"><span data-stu-id="3affc-258">4</span></span>|  
|`ver_ICorDebugRuntimeUnwindableFrame`|[<span data-ttu-id="3affc-259">ICorDebugRuntimeUnwindableFrame</span><span class="sxs-lookup"><span data-stu-id="3affc-259">ICorDebugRuntimeUnwindableFrame</span></span>](icordebugruntimeunwindableframe-interface.md)|<span data-ttu-id="3affc-260">4</span><span class="sxs-lookup"><span data-stu-id="3affc-260">4</span></span>|  
|`ver_ICorDebugHeapValue3`|[<span data-ttu-id="3affc-261">ICorDebugHeapValue3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3affc-261">ICorDebugHeapValue3 Interface</span></span>](icordebugheapvalue3-interface.md)|<span data-ttu-id="3affc-262">4</span><span class="sxs-lookup"><span data-stu-id="3affc-262">4</span></span>|  
|`ver_ICorDebugBlockingObjectEnum`|[<span data-ttu-id="3affc-263">ICorDebugBlockingObjectEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3affc-263">ICorDebugBlockingObjectEnum Interface</span></span>](icordebugblockingobjectenum-interface.md)|<span data-ttu-id="3affc-264">4</span><span class="sxs-lookup"><span data-stu-id="3affc-264">4</span></span>|  
|`ver_ICorDebugValue3`|[<span data-ttu-id="3affc-265">ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="3affc-265">ICorDebugValue3</span></span>](icordebugvalue3-interface.md)|<span data-ttu-id="3affc-266">4</span><span class="sxs-lookup"><span data-stu-id="3affc-266">4</span></span>|  
|`ver_ICorDebugComObjectValue`|[<span data-ttu-id="3affc-267">ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="3affc-267">ICorDebugComObjectValue</span></span>](icordebugcomobjectvalue-interface.md)|<span data-ttu-id="3affc-268">4.5.</span><span class="sxs-lookup"><span data-stu-id="3affc-268">4.5</span></span>|  
|`ver_ICorDebugAppDomain3`|[<span data-ttu-id="3affc-269">ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="3affc-269">ICorDebugAppDomain3</span></span>](icordebugappdomain3-interface.md)|<span data-ttu-id="3affc-270">4.5.</span><span class="sxs-lookup"><span data-stu-id="3affc-270">4.5</span></span>|  
|`ver_ICorDebugCode3`|[<span data-ttu-id="3affc-271">ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="3affc-271">ICorDebugCode3</span></span>](icordebugcode3-interface.md)|<span data-ttu-id="3affc-272">4.5.</span><span class="sxs-lookup"><span data-stu-id="3affc-272">4.5</span></span>|  
|`ver_ICorDebugILFrame3`|[<span data-ttu-id="3affc-273">ICorDebugILFrame3</span><span class="sxs-lookup"><span data-stu-id="3affc-273">ICorDebugILFrame3</span></span>](icordebugilframe3-interface.md)|<span data-ttu-id="3affc-274">4.5.</span><span class="sxs-lookup"><span data-stu-id="3affc-274">4.5</span></span>|  
|`CorDebugLatestVersion`|<span data-ttu-id="3affc-275">La versión de .NET Framework, incluidos todos sus Service Packs, es la última versión.</span><span class="sxs-lookup"><span data-stu-id="3affc-275">The version of the .NET Framework, including all of its service packs, is the latest version.</span></span>|-|  
  
## <a name="remarks"></a><span data-ttu-id="3affc-276">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3affc-276">Remarks</span></span>  

 <span data-ttu-id="3affc-277">Un depurador puede utilizar la `CorDebugInterfaceVersion` enumeración en la función [CreateDebuggingInterfaceFromVersion (](../hosting/createdebugginginterfacefromversion-function.md) para especificar la versión más alta de los .NET Framework que admite el depurador.</span><span class="sxs-lookup"><span data-stu-id="3affc-277">A debugger can use the `CorDebugInterfaceVersion` enumeration in the [CreateDebuggingInterfaceFromVersion](../hosting/createdebugginginterfacefromversion-function.md) function to specify the highest version of the .NET Framework that the debugger supports.</span></span>  
  
## <a name="interface-names"></a><span data-ttu-id="3affc-278">Nombres de interfaz</span><span class="sxs-lookup"><span data-stu-id="3affc-278">Interface Names</span></span>  

 <span data-ttu-id="3affc-279">El número que aparece al final de los nombres de interfaz en la API de depuración (por ejemplo, "3" en `ICorDebugThread3`) especifica la versión de la interfaz, no la versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3affc-279">The number that appears at the end of the interface names in the debugging API (for example, the "3" in `ICorDebugThread3`) specifies the version of the interface, not the version of the .NET Framework.</span></span> <span data-ttu-id="3affc-280">Todos los nombres de interfaz en la API de depuración incluyen números de versión, excepto las interfaces que se incorporaron en .NET Framework versión 1.</span><span class="sxs-lookup"><span data-stu-id="3affc-280">All interface names in the debugging API include version numbers except for interfaces that were introduced in the .NET Framework version 1.</span></span> <span data-ttu-id="3affc-281">Cualquier correspondencia entre los números de versión de las interfaces y los números de versión de .NET Framework es pura coincidencia.</span><span class="sxs-lookup"><span data-stu-id="3affc-281">Any correspondence between interface version numbers and.NET Framework version numbers are coincidental.</span></span>  
  
- <span data-ttu-id="3affc-282">Las interfaces que se incorporaron en .NET Framework versión 1.0 no incluyen números, porque implícitamente son todas de la versión 1.</span><span class="sxs-lookup"><span data-stu-id="3affc-282">Interfaces that were introduced in the .NET Framework version 1.0 do not include numbers, because they are all implicitly version 1.</span></span>  
  
- <span data-ttu-id="3affc-283">.NET Framework versión 1.1 usa las interfaces de la versión 1.0 y no incorpora ninguna interfaz de depuración nueva.</span><span class="sxs-lookup"><span data-stu-id="3affc-283">The .NET Framework version 1.1 uses version 1.0 interfaces, and does not introduce any new debugging interfaces.</span></span>  
  
- <span data-ttu-id="3affc-284">Las 14 interfaces de depuración que se incorporaron en .NET Framework versión 2.0 son extensiones lógicas de sus homólogas de la versión 1, e incluyen el número "2" en sus nombres.</span><span class="sxs-lookup"><span data-stu-id="3affc-284">The 14 debugging interfaces introduced in the .NET Framework version 2.0 are logical extensions of their version 1 counterparts and include the number "2" in their names.</span></span>  
  
- <span data-ttu-id="3affc-285">.NET Framework versión 3.0 y versión 3.5 usa las interfaces de .NET Framework 2.0 existentes y no incorpora ninguna interfaz nueva.</span><span class="sxs-lookup"><span data-stu-id="3affc-285">The .NET Framework versions 3.0 and 3.5 use the existing .NET Framework 2.0 interfaces, and do not introduce any new interfaces.</span></span>  
  
- <span data-ttu-id="3affc-286">El .NET Framework 4 introduce una combinación de versiones de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="3affc-286">The .NET Framework 4 introduces a mix of interface versions.</span></span> <span data-ttu-id="3affc-287">Por ejemplo, tanto `ICorDebugThread3` como `ICorDebugThread4` aparecen como la tercera y cuarta versión de la interfaz `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="3affc-287">For example, both `ICorDebugThread3` and `ICorDebugThread4` appear as the third and fourth versions of the `ICorDebugThread` interface.</span></span> <span data-ttu-id="3affc-288">El .NET Framework 4 también introduce la primera versión de la `ICorDebugStackWalk` interfaz y la segunda versión de la `ICorDebugNativeFrame` interfaz ( `ICorDebugNativeFrame2` ).</span><span class="sxs-lookup"><span data-stu-id="3affc-288">The .NET Framework 4 also introduces the first version of the `ICorDebugStackWalk` interface and the second version of the `ICorDebugNativeFrame` interface (`ICorDebugNativeFrame2`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3affc-289">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3affc-289">Requirements</span></span>  

 <span data-ttu-id="3affc-290">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3affc-290">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3affc-291">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3affc-291">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3affc-292">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3affc-292">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3affc-293">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3affc-293">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3affc-294">Vea también</span><span class="sxs-lookup"><span data-stu-id="3affc-294">See also</span></span>

- [<span data-ttu-id="3affc-295">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="3affc-295">Debugging Enumerations</span></span>](debugging-enumerations.md)
