---
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
ms.openlocfilehash: 70d9ee06d64cc80306a1988aa6e28859cadb9ecf
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778403"
---
# <a name="cordebuginterfaceversion-enumeration"></a><span data-ttu-id="aa69a-102">CorDebugInterfaceVersion (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="aa69a-102">CorDebugInterfaceVersion Enumeration</span></span>
<span data-ttu-id="aa69a-103">Especifica una interfaz, una versión de .NET Framework, o la versión de .NET Framework en la que se incorporó una interfaz.</span><span class="sxs-lookup"><span data-stu-id="aa69a-103">Specifies an interface, a version of the .NET Framework, or a version of the .NET Framework in which an interface was introduced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa69a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aa69a-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="aa69a-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="aa69a-105">Members</span></span>  
 <span data-ttu-id="aa69a-106">En la tabla siguiente se incluyen vínculos de cada valor de enumeración a la interfaz correspondiente.</span><span class="sxs-lookup"><span data-stu-id="aa69a-106">The following table provides links from each enumeration value to the corresponding interface.</span></span> <span data-ttu-id="aa69a-107">Además, la tabla indica la primera versión de .NET Framework en la que se admitía la interfaz.</span><span class="sxs-lookup"><span data-stu-id="aa69a-107">In addition, the table indicates the first version of the .NET Framework that the interface was supported in.</span></span>  
  
|<span data-ttu-id="aa69a-108">Miembro</span><span class="sxs-lookup"><span data-stu-id="aa69a-108">Member</span></span>|<span data-ttu-id="aa69a-109">Especifica</span><span class="sxs-lookup"><span data-stu-id="aa69a-109">Specifies</span></span>|<span data-ttu-id="aa69a-110">Versión de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="aa69a-110">.NET Framework version</span></span>|  
|------------|---------------|----------------------------|  
|`CorDebugInvalidVersion`|<span data-ttu-id="aa69a-111">La versión de .NET Framework no es válida.</span><span class="sxs-lookup"><span data-stu-id="aa69a-111">The version of the .NET Framework is invalid.</span></span>|-|  
|`CorDebugVersion_1_0`|<span data-ttu-id="aa69a-112">La versión de .NET Framework, incluidos todos sus Service Packs, es 1.0.</span><span class="sxs-lookup"><span data-stu-id="aa69a-112">The version of the .NET Framework, including all its service packs, is 1.0.</span></span>|<span data-ttu-id="aa69a-113">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-113">1.0</span></span>|  
|`CorDebugVersion_1_1`|<span data-ttu-id="aa69a-114">La versión de .NET Framework, incluidos todos los Service Packs, es 1.1.</span><span class="sxs-lookup"><span data-stu-id="aa69a-114">The version of the .NET Framework, including all service packs, is 1.1.</span></span>|<span data-ttu-id="aa69a-115">1.1</span><span class="sxs-lookup"><span data-stu-id="aa69a-115">1.1</span></span>|  
|`CorDebugVersion_2_0`|<span data-ttu-id="aa69a-116">La versión de .NET Framework, incluidos todos los Service Packs, es 2,0.</span><span class="sxs-lookup"><span data-stu-id="aa69a-116">The version of the .NET Framework, including all service packs, is 2.0.</span></span>|<span data-ttu-id="aa69a-117">2.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-117">2.0</span></span>|  
|`CorDebugVersion_4_0`|<span data-ttu-id="aa69a-118">La versión de .NET Framework, incluidos todos los Service Packs, es 4.</span><span class="sxs-lookup"><span data-stu-id="aa69a-118">The version of the .NET Framework, including all service packs, is 4.</span></span>|<span data-ttu-id="aa69a-119">4</span><span class="sxs-lookup"><span data-stu-id="aa69a-119">4</span></span>|  
|`CorDebugVersion_4_5`|<span data-ttu-id="aa69a-120">La versión de .NET Framework, incluidos todos los Service Packs, es 4,5.</span><span class="sxs-lookup"><span data-stu-id="aa69a-120">The version of the .NET Framework, including all service packs, is 4.5.</span></span>|<span data-ttu-id="aa69a-121">4.5</span><span class="sxs-lookup"><span data-stu-id="aa69a-121">4.5</span></span>|  
|`ver_ICorDebugManagedCallback`|[<span data-ttu-id="aa69a-122">ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="aa69a-122">ICorDebugManagedCallback</span></span>](icordebugmanagedcallback-interface.md)|<span data-ttu-id="aa69a-123">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-123">1.0</span></span>|  
|`ver_ICorDebugUnmanagedCallback`|[<span data-ttu-id="aa69a-124">ICorDebugUnmanagedCallback</span><span class="sxs-lookup"><span data-stu-id="aa69a-124">ICorDebugUnmanagedCallback</span></span>](icordebugunmanagedcallback-interface.md)|<span data-ttu-id="aa69a-125">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-125">1.0</span></span>|  
|`ver_ICorDebug`|[<span data-ttu-id="aa69a-126">ICorDebug</span><span class="sxs-lookup"><span data-stu-id="aa69a-126">ICorDebug</span></span>](icordebug-interface.md)|<span data-ttu-id="aa69a-127">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-127">1.0</span></span>|  
|`ver_ICorDebugController`|[<span data-ttu-id="aa69a-128">ICorDebugController</span><span class="sxs-lookup"><span data-stu-id="aa69a-128">ICorDebugController</span></span>](icordebugcontroller-interface.md)|<span data-ttu-id="aa69a-129">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-129">1.0</span></span>|  
|`ver_ICorDebugAppDomain`|[<span data-ttu-id="aa69a-130">ICorDebugAppDomain</span><span class="sxs-lookup"><span data-stu-id="aa69a-130">ICorDebugAppDomain</span></span>](icordebugappdomain-interface.md)|<span data-ttu-id="aa69a-131">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-131">1.0</span></span>|  
|`ver_ICorDebugAssembly`|[<span data-ttu-id="aa69a-132">ICorDebugAssembly</span><span class="sxs-lookup"><span data-stu-id="aa69a-132">ICorDebugAssembly</span></span>](icordebugassembly-interface.md)|<span data-ttu-id="aa69a-133">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-133">1.0</span></span>|  
|`ver_ICorDebugProcess`|[<span data-ttu-id="aa69a-134">ICorDebugProcess</span><span class="sxs-lookup"><span data-stu-id="aa69a-134">ICorDebugProcess</span></span>](icordebugprocess-interface.md)|<span data-ttu-id="aa69a-135">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-135">1.0</span></span>|  
|`ver_ICorDebugBreakpoint`|[<span data-ttu-id="aa69a-136">ICorDebugBreakpoint</span><span class="sxs-lookup"><span data-stu-id="aa69a-136">ICorDebugBreakpoint</span></span>](icordebugbreakpoint-interface.md)|<span data-ttu-id="aa69a-137">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-137">1.0</span></span>|  
|`ver_ICorDebugFunctionBreakpoint`|[<span data-ttu-id="aa69a-138">ICorDebugFunctionBreakpoint</span><span class="sxs-lookup"><span data-stu-id="aa69a-138">ICorDebugFunctionBreakpoint</span></span>](icordebugfunctionbreakpoint-interface.md)|<span data-ttu-id="aa69a-139">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-139">1.0</span></span>|  
|`ver_ICorDebugModuleBreakpoint`|[<span data-ttu-id="aa69a-140">ICorDebugModuleBreakpoint</span><span class="sxs-lookup"><span data-stu-id="aa69a-140">ICorDebugModuleBreakpoint</span></span>](icordebugmodulebreakpoint-interface.md)|<span data-ttu-id="aa69a-141">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-141">1.0</span></span>|  
|`ver_ICorDebugValueBreakpoint`|[<span data-ttu-id="aa69a-142">ICorDebugValueBreakpoint</span><span class="sxs-lookup"><span data-stu-id="aa69a-142">ICorDebugValueBreakpoint</span></span>](icordebugvaluebreakpoint-interface.md)|<span data-ttu-id="aa69a-143">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-143">1.0</span></span>|  
|`ver_ICorDebugStepper`|[<span data-ttu-id="aa69a-144">ICorDebugStepper</span><span class="sxs-lookup"><span data-stu-id="aa69a-144">ICorDebugStepper</span></span>](icordebugstepper-interface.md)|<span data-ttu-id="aa69a-145">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-145">1.0</span></span>|  
|`ver_ICorDebugRegisterSet`|[<span data-ttu-id="aa69a-146">ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="aa69a-146">ICorDebugRegisterSet</span></span>](icordebugregisterset-interface.md)|<span data-ttu-id="aa69a-147">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-147">1.0</span></span>|  
|`ver_ICorDebugThread`|[<span data-ttu-id="aa69a-148">ICorDebugThread</span><span class="sxs-lookup"><span data-stu-id="aa69a-148">ICorDebugThread</span></span>](icordebugthread-interface.md)|<span data-ttu-id="aa69a-149">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-149">1.0</span></span>|  
|`ver_ICorDebugChain`|[<span data-ttu-id="aa69a-150">ICorDebugChain</span><span class="sxs-lookup"><span data-stu-id="aa69a-150">ICorDebugChain</span></span>](icordebugchain-interface.md)|<span data-ttu-id="aa69a-151">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-151">1.0</span></span>|  
|`ver_ICorDebugFrame`|[<span data-ttu-id="aa69a-152">ICorDebugFrame</span><span class="sxs-lookup"><span data-stu-id="aa69a-152">ICorDebugFrame</span></span>](icordebugframe-interface.md)|<span data-ttu-id="aa69a-153">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-153">1.0</span></span>|  
|`ver_ICorDebugILFrame`|[<span data-ttu-id="aa69a-154">ICorDebugILFrame</span><span class="sxs-lookup"><span data-stu-id="aa69a-154">ICorDebugILFrame</span></span>](icordebugilframe-interface.md)|<span data-ttu-id="aa69a-155">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-155">1.0</span></span>|  
|`ver_ICorDebugNativeFrame`|[<span data-ttu-id="aa69a-156">ICorDebugNativeFrame</span><span class="sxs-lookup"><span data-stu-id="aa69a-156">ICorDebugNativeFrame</span></span>](icordebugnativeframe-interface.md)|<span data-ttu-id="aa69a-157">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-157">1.0</span></span>|  
|`ver_ICorDebugModule`|[<span data-ttu-id="aa69a-158">ICorDebugModule</span><span class="sxs-lookup"><span data-stu-id="aa69a-158">ICorDebugModule</span></span>](icordebugmodule-interface.md)|<span data-ttu-id="aa69a-159">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-159">1.0</span></span>|  
|`ver_ICorDebugFunction`|[<span data-ttu-id="aa69a-160">ICorDebugFunction</span><span class="sxs-lookup"><span data-stu-id="aa69a-160">ICorDebugFunction</span></span>](icordebugfunction-interface1.md)|<span data-ttu-id="aa69a-161">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-161">1.0</span></span>|  
|`ver_ICorDebugCode`|[<span data-ttu-id="aa69a-162">ICorDebugCode</span><span class="sxs-lookup"><span data-stu-id="aa69a-162">ICorDebugCode</span></span>](icordebugcode-interface1.md)|<span data-ttu-id="aa69a-163">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-163">1.0</span></span>|  
|`ver_ICorDebugClass`|[<span data-ttu-id="aa69a-164">ICorDebugClass</span><span class="sxs-lookup"><span data-stu-id="aa69a-164">ICorDebugClass</span></span>](icordebugclass-interface.md)|<span data-ttu-id="aa69a-165">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-165">1.0</span></span>|  
|`ver_ICorDebugEval`|[<span data-ttu-id="aa69a-166">ICorDebugEval</span><span class="sxs-lookup"><span data-stu-id="aa69a-166">ICorDebugEval</span></span>](icordebugeval-interface.md)|<span data-ttu-id="aa69a-167">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-167">1.0</span></span>|  
|`ver_ICorDebugValue`|[<span data-ttu-id="aa69a-168">ICorDebugValue</span><span class="sxs-lookup"><span data-stu-id="aa69a-168">ICorDebugValue</span></span>](icordebugvalue-interface.md)|<span data-ttu-id="aa69a-169">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-169">1.0</span></span>|  
|`ver_ICorDebugGenericValue`|[<span data-ttu-id="aa69a-170">ICorDebugGenericValue</span><span class="sxs-lookup"><span data-stu-id="aa69a-170">ICorDebugGenericValue</span></span>](icordebuggenericvalue-interface.md)|<span data-ttu-id="aa69a-171">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-171">1.0</span></span>|  
|`ver_ICorDebugReferenceValue`|[<span data-ttu-id="aa69a-172">ICorDebugReferenceValue</span><span class="sxs-lookup"><span data-stu-id="aa69a-172">ICorDebugReferenceValue</span></span>](icordebugreferencevalue-interface.md)|<span data-ttu-id="aa69a-173">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-173">1.0</span></span>|  
|`ver_ICorDebugHeapValue`|[<span data-ttu-id="aa69a-174">ICorDebugHeapValue</span><span class="sxs-lookup"><span data-stu-id="aa69a-174">ICorDebugHeapValue</span></span>](icordebugheapvalue-interface.md)|<span data-ttu-id="aa69a-175">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-175">1.0</span></span>|  
|`ver_ICorDebugObjectValue`|[<span data-ttu-id="aa69a-176">ICorDebugObjectValue</span><span class="sxs-lookup"><span data-stu-id="aa69a-176">ICorDebugObjectValue</span></span>](icordebugobjectvalue-interface.md)|<span data-ttu-id="aa69a-177">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-177">1.0</span></span>|  
|`ver_ICorDebugBoxValue`|[<span data-ttu-id="aa69a-178">ICorDebugBoxValue</span><span class="sxs-lookup"><span data-stu-id="aa69a-178">ICorDebugBoxValue</span></span>](icordebugboxvalue-interface.md)|<span data-ttu-id="aa69a-179">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-179">1.0</span></span>|  
|`ver_ICorDebugStringValue`|[<span data-ttu-id="aa69a-180">ICorDebugStringValue</span><span class="sxs-lookup"><span data-stu-id="aa69a-180">ICorDebugStringValue</span></span>](icordebugstringvalue-interface.md)|<span data-ttu-id="aa69a-181">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-181">1.0</span></span>|  
|`ver_ICorDebugArrayValue`|[<span data-ttu-id="aa69a-182">ICorDebugArrayValue</span><span class="sxs-lookup"><span data-stu-id="aa69a-182">ICorDebugArrayValue</span></span>](icordebugarrayvalue-interface.md)|<span data-ttu-id="aa69a-183">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-183">1.0</span></span>|  
|`ver_ICorDebugContext`|[<span data-ttu-id="aa69a-184">ICorDebugContext</span><span class="sxs-lookup"><span data-stu-id="aa69a-184">ICorDebugContext</span></span>](icordebugcontext-interface.md)|<span data-ttu-id="aa69a-185">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-185">1.0</span></span>|  
|`ver_ICorDebugEnum`|[<span data-ttu-id="aa69a-186">ICorDebugEnum</span><span class="sxs-lookup"><span data-stu-id="aa69a-186">ICorDebugEnum</span></span>](icordebugenum-interface1.md)|<span data-ttu-id="aa69a-187">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-187">1.0</span></span>|  
|`ver_ICorDebugObjectEnum`|[<span data-ttu-id="aa69a-188">ICorDebugObjectEnum</span><span class="sxs-lookup"><span data-stu-id="aa69a-188">ICorDebugObjectEnum</span></span>](icordebugobjectenum-interface.md)|<span data-ttu-id="aa69a-189">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-189">1.0</span></span>|  
|`ver_ICorDebugBreakpointEnum`|[<span data-ttu-id="aa69a-190">ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="aa69a-190">ICorDebugBreakpointEnum</span></span>](icordebugbreakpointenum-interface.md)|<span data-ttu-id="aa69a-191">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-191">1.0</span></span>|  
|`ver_ICorDebugStepperEnum`|[<span data-ttu-id="aa69a-192">ICorDebugStepperEnum</span><span class="sxs-lookup"><span data-stu-id="aa69a-192">ICorDebugStepperEnum</span></span>](icordebugstepperenum-interface.md)|<span data-ttu-id="aa69a-193">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-193">1.0</span></span>|  
|`ver_ICorDebugProcessEnum`|[<span data-ttu-id="aa69a-194">ICorDebugProcessEnum</span><span class="sxs-lookup"><span data-stu-id="aa69a-194">ICorDebugProcessEnum</span></span>](icordebugprocessenum-interface.md)|<span data-ttu-id="aa69a-195">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-195">1.0</span></span>|  
|`ver_ICorDebugThreadEnum`|[<span data-ttu-id="aa69a-196">ICorDebugThreadEnum</span><span class="sxs-lookup"><span data-stu-id="aa69a-196">ICorDebugThreadEnum</span></span>](icordebugthreadenum-interface1.md)|<span data-ttu-id="aa69a-197">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-197">1.0</span></span>|  
|`ver_ICorDebugFrameEnum`|[<span data-ttu-id="aa69a-198">ICorDebugFrameEnum</span><span class="sxs-lookup"><span data-stu-id="aa69a-198">ICorDebugFrameEnum</span></span>](icordebugframeenum-interface.md)|<span data-ttu-id="aa69a-199">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-199">1.0</span></span>|  
|`ver_ICorDebugChainEnum`|[<span data-ttu-id="aa69a-200">ICorDebugChainEnum</span><span class="sxs-lookup"><span data-stu-id="aa69a-200">ICorDebugChainEnum</span></span>](icordebugchainenum-interface.md)|<span data-ttu-id="aa69a-201">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-201">1.0</span></span>|  
|`ver_ICorDebugModuleEnum`|[<span data-ttu-id="aa69a-202">ICorDebugModuleEnum</span><span class="sxs-lookup"><span data-stu-id="aa69a-202">ICorDebugModuleEnum</span></span>](icordebugmoduleenum-interface.md)|<span data-ttu-id="aa69a-203">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-203">1.0</span></span>|  
|`ver_ICorDebugValueEnum`|[<span data-ttu-id="aa69a-204">ICorDebugValueEnum</span><span class="sxs-lookup"><span data-stu-id="aa69a-204">ICorDebugValueEnum</span></span>](icordebugvalueenum-interface.md)|<span data-ttu-id="aa69a-205">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-205">1.0</span></span>|  
|`ver_ICorDebugCodeEnum`|[<span data-ttu-id="aa69a-206">ICorDebugCodeEnum</span><span class="sxs-lookup"><span data-stu-id="aa69a-206">ICorDebugCodeEnum</span></span>](icordebugcodeenum-interface.md)|<span data-ttu-id="aa69a-207">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-207">1.0</span></span>|  
|`ver_ICorDebugTypeEnum`|[<span data-ttu-id="aa69a-208">ICorDebugTypeEnum</span><span class="sxs-lookup"><span data-stu-id="aa69a-208">ICorDebugTypeEnum</span></span>](icordebugtypeenum-interface.md)|<span data-ttu-id="aa69a-209">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-209">1.0</span></span>|  
|`ver_ICorDebugErrorInfoEnum`|[<span data-ttu-id="aa69a-210">ICorDebugErrorInfoEnum</span><span class="sxs-lookup"><span data-stu-id="aa69a-210">ICorDebugErrorInfoEnum</span></span>](icordebugerrorinfoenum-interface.md)|<span data-ttu-id="aa69a-211">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-211">1.0</span></span>|  
|`ver_ICorDebugAppDomainEnum`|[<span data-ttu-id="aa69a-212">ICorDebugAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="aa69a-212">ICorDebugAppDomainEnum</span></span>](icordebugappdomainenum-interface.md)|<span data-ttu-id="aa69a-213">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-213">1.0</span></span>|  
|`ver_ICorDebugAssemblyEnum`|[<span data-ttu-id="aa69a-214">ICorDebugAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="aa69a-214">ICorDebugAssemblyEnum</span></span>](icordebugassemblyenum-interface.md)|<span data-ttu-id="aa69a-215">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-215">1.0</span></span>|  
|`ver_ICorDebugEditAndContinueErrorInfo`|[<span data-ttu-id="aa69a-216">ICorDebugEditAndContinueErrorInfo</span><span class="sxs-lookup"><span data-stu-id="aa69a-216">ICorDebugEditAndContinueErrorInfo</span></span>](icordebugeditandcontinueerrorinfo-interface.md)|<span data-ttu-id="aa69a-217">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-217">1.0</span></span>|  
|`ver_ICorDebugEditAndContinueSnapshot`|[<span data-ttu-id="aa69a-218">ICorDebugEditAndContinueSnapshot</span><span class="sxs-lookup"><span data-stu-id="aa69a-218">ICorDebugEditAndContinueSnapshot</span></span>](icordebugeditandcontinuesnapshot-interface.md)|<span data-ttu-id="aa69a-219">1.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-219">1.0</span></span>|  
|`ver_ICorDebugManagedCallback2`|[<span data-ttu-id="aa69a-220">ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="aa69a-220">ICorDebugManagedCallback2</span></span>](icordebugmanagedcallback2-interface.md)|<span data-ttu-id="aa69a-221">2.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-221">2.0</span></span>|  
|`ver_ICorDebugAppDomain2`|[<span data-ttu-id="aa69a-222">ICorDebugAppDomain2</span><span class="sxs-lookup"><span data-stu-id="aa69a-222">ICorDebugAppDomain2</span></span>](icordebugappdomain2-interface.md)|<span data-ttu-id="aa69a-223">2.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-223">2.0</span></span>|  
|`ver_ICorDebugProcess2`|[<span data-ttu-id="aa69a-224">ICorDebugProcess2</span><span class="sxs-lookup"><span data-stu-id="aa69a-224">ICorDebugProcess2</span></span>](icordebugprocess2-interface1.md)|<span data-ttu-id="aa69a-225">2.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-225">2.0</span></span>|  
|`ver_ICorDebugStepper2`|[<span data-ttu-id="aa69a-226">ICorDebugStepper2</span><span class="sxs-lookup"><span data-stu-id="aa69a-226">ICorDebugStepper2</span></span>](icordebugstepper2-interface1.md)|<span data-ttu-id="aa69a-227">2.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-227">2.0</span></span>|  
|`ver_ICorDebugRegisterSet2`|[<span data-ttu-id="aa69a-228">ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="aa69a-228">ICorDebugRegisterSet2</span></span>](icordebugregisterset2-interface.md)|<span data-ttu-id="aa69a-229">2.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-229">2.0</span></span>|  
|`ver_ICorDebugThread2`|[<span data-ttu-id="aa69a-230">ICorDebugThread2</span><span class="sxs-lookup"><span data-stu-id="aa69a-230">ICorDebugThread2</span></span>](icordebugthread2-interface.md)|<span data-ttu-id="aa69a-231">2.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-231">2.0</span></span>|  
|`ver_ICorDebugILFrame2`|[<span data-ttu-id="aa69a-232">ICorDebugILFrame2</span><span class="sxs-lookup"><span data-stu-id="aa69a-232">ICorDebugILFrame2</span></span>](icordebugilframe2-interface.md)|<span data-ttu-id="aa69a-233">2.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-233">2.0</span></span>|  
|`ver_ICorDebugModule2`|[<span data-ttu-id="aa69a-234">ICorDebugModule2</span><span class="sxs-lookup"><span data-stu-id="aa69a-234">ICorDebugModule2</span></span>](icordebugmodule2-interface.md)|<span data-ttu-id="aa69a-235">2.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-235">2.0</span></span>|  
|`ver_ICorDebugFunction2`|[<span data-ttu-id="aa69a-236">ICorDebugFunction2</span><span class="sxs-lookup"><span data-stu-id="aa69a-236">ICorDebugFunction2</span></span>](icordebugfunction2-interface.md)|<span data-ttu-id="aa69a-237">2.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-237">2.0</span></span>|  
|`ver_ICorDebugCode2`|[<span data-ttu-id="aa69a-238">ICorDebugCode2</span><span class="sxs-lookup"><span data-stu-id="aa69a-238">ICorDebugCode2</span></span>](icordebugcode2-interface.md)|<span data-ttu-id="aa69a-239">2.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-239">2.0</span></span>|  
|`ver_ICorDebugClass2`|<span data-ttu-id="aa69a-240">"ICorDebugClass2"</span><span class="sxs-lookup"><span data-stu-id="aa69a-240">"ICorDebugClass2"</span></span>|<span data-ttu-id="aa69a-241">2.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-241">2.0</span></span>|  
|`ver_ICorDebugValue2`|<span data-ttu-id="aa69a-242">ICorDebugValue2</span><span class="sxs-lookup"><span data-stu-id="aa69a-242">"ICorDebugValue2"</span></span>|<span data-ttu-id="aa69a-243">2.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-243">2.0</span></span>|  
|`ver_ICorDebugEval2`|<span data-ttu-id="aa69a-244">"ICorDebugEval2".</span><span class="sxs-lookup"><span data-stu-id="aa69a-244">The "ICorDebugEval2".</span></span>|<span data-ttu-id="aa69a-245">2.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-245">2.0</span></span>|  
|`ver_ICorDebugObjectValue2`|<span data-ttu-id="aa69a-246">"ICorDebugObjectValue2"</span><span class="sxs-lookup"><span data-stu-id="aa69a-246">"ICorDebugObjectValue2"</span></span>|<span data-ttu-id="aa69a-247">2.0</span><span class="sxs-lookup"><span data-stu-id="aa69a-247">2.0</span></span>|  
|`ver_ICorDebugThread3`|[<span data-ttu-id="aa69a-248">ICorDebugThread3</span><span class="sxs-lookup"><span data-stu-id="aa69a-248">ICorDebugThread3</span></span>](icordebugthread3-interface.md)|<span data-ttu-id="aa69a-249">4</span><span class="sxs-lookup"><span data-stu-id="aa69a-249">4</span></span>|  
|`ver_ICorDebugThread4`|[<span data-ttu-id="aa69a-250">ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="aa69a-250">ICorDebugThread4</span></span>](icordebugthread4-interface.md)|<span data-ttu-id="aa69a-251">4</span><span class="sxs-lookup"><span data-stu-id="aa69a-251">4</span></span>|  
|`ver_ICorDebugStackWalk`|[<span data-ttu-id="aa69a-252">ICorDebugStackWalk</span><span class="sxs-lookup"><span data-stu-id="aa69a-252">ICorDebugStackWalk</span></span>](icordebugstackwalk-interface.md)|<span data-ttu-id="aa69a-253">4</span><span class="sxs-lookup"><span data-stu-id="aa69a-253">4</span></span>|  
|`ver_ICorDebugNativeFrame2`|[<span data-ttu-id="aa69a-254">ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="aa69a-254">ICorDebugNativeFrame2</span></span>](icordebugnativeframe2-interface.md)|<span data-ttu-id="aa69a-255">4</span><span class="sxs-lookup"><span data-stu-id="aa69a-255">4</span></span>|  
|`ver_ICorDebugInternalFrame2`|[<span data-ttu-id="aa69a-256">ICorDebugInternalFrame2</span><span class="sxs-lookup"><span data-stu-id="aa69a-256">ICorDebugInternalFrame2</span></span>](icordebuginternalframe2-interface.md)|<span data-ttu-id="aa69a-257">4</span><span class="sxs-lookup"><span data-stu-id="aa69a-257">4</span></span>|  
|`ver_ICorDebugRuntimeUnwindableFrame`|[<span data-ttu-id="aa69a-258">ICorDebugRuntimeUnwindableFrame</span><span class="sxs-lookup"><span data-stu-id="aa69a-258">ICorDebugRuntimeUnwindableFrame</span></span>](icordebugruntimeunwindableframe-interface.md)|<span data-ttu-id="aa69a-259">4</span><span class="sxs-lookup"><span data-stu-id="aa69a-259">4</span></span>|  
|`ver_ICorDebugHeapValue3`|[<span data-ttu-id="aa69a-260">ICorDebugHeapValue3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa69a-260">ICorDebugHeapValue3 Interface</span></span>](icordebugheapvalue3-interface.md)|<span data-ttu-id="aa69a-261">4</span><span class="sxs-lookup"><span data-stu-id="aa69a-261">4</span></span>|  
|`ver_ICorDebugBlockingObjectEnum`|[<span data-ttu-id="aa69a-262">ICorDebugBlockingObjectEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aa69a-262">ICorDebugBlockingObjectEnum Interface</span></span>](icordebugblockingobjectenum-interface.md)|<span data-ttu-id="aa69a-263">4</span><span class="sxs-lookup"><span data-stu-id="aa69a-263">4</span></span>|  
|`ver_ICorDebugValue3`|[<span data-ttu-id="aa69a-264">ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="aa69a-264">ICorDebugValue3</span></span>](icordebugvalue3-interface.md)|<span data-ttu-id="aa69a-265">4</span><span class="sxs-lookup"><span data-stu-id="aa69a-265">4</span></span>|  
|`ver_ICorDebugComObjectValue`|[<span data-ttu-id="aa69a-266">ICorDebugComObjectValue</span><span class="sxs-lookup"><span data-stu-id="aa69a-266">ICorDebugComObjectValue</span></span>](icordebugcomobjectvalue-interface.md)|<span data-ttu-id="aa69a-267">4.5</span><span class="sxs-lookup"><span data-stu-id="aa69a-267">4.5</span></span>|  
|`ver_ICorDebugAppDomain3`|[<span data-ttu-id="aa69a-268">ICorDebugAppDomain3</span><span class="sxs-lookup"><span data-stu-id="aa69a-268">ICorDebugAppDomain3</span></span>](icordebugappdomain3-interface.md)|<span data-ttu-id="aa69a-269">4.5</span><span class="sxs-lookup"><span data-stu-id="aa69a-269">4.5</span></span>|  
|`ver_ICorDebugCode3`|[<span data-ttu-id="aa69a-270">ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="aa69a-270">ICorDebugCode3</span></span>](icordebugcode3-interface.md)|<span data-ttu-id="aa69a-271">4.5</span><span class="sxs-lookup"><span data-stu-id="aa69a-271">4.5</span></span>|  
|`ver_ICorDebugILFrame3`|[<span data-ttu-id="aa69a-272">ICorDebugILFrame3</span><span class="sxs-lookup"><span data-stu-id="aa69a-272">ICorDebugILFrame3</span></span>](icordebugilframe3-interface.md)|<span data-ttu-id="aa69a-273">4.5</span><span class="sxs-lookup"><span data-stu-id="aa69a-273">4.5</span></span>|  
|`CorDebugLatestVersion`|<span data-ttu-id="aa69a-274">La versión de .NET Framework, incluidos todos sus Service Packs, es la última versión.</span><span class="sxs-lookup"><span data-stu-id="aa69a-274">The version of the .NET Framework, including all of its service packs, is the latest version.</span></span>|-|  
  
## <a name="remarks"></a><span data-ttu-id="aa69a-275">Notas</span><span class="sxs-lookup"><span data-stu-id="aa69a-275">Remarks</span></span>  
 <span data-ttu-id="aa69a-276">Un depurador puede utilizar la enumeración `CorDebugInterfaceVersion` de la función [CreateDebuggingInterfaceFromVersion (](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) para especificar la versión más alta de la .NET Framework que admite el depurador.</span><span class="sxs-lookup"><span data-stu-id="aa69a-276">A debugger can use the `CorDebugInterfaceVersion` enumeration in the [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) function to specify the highest version of the .NET Framework that the debugger supports.</span></span>  
  
## <a name="interface-names"></a><span data-ttu-id="aa69a-277">Nombres de interfaz</span><span class="sxs-lookup"><span data-stu-id="aa69a-277">Interface Names</span></span>  
 <span data-ttu-id="aa69a-278">El número que aparece al final de los nombres de interfaz en la API de depuración (por ejemplo, "3" en `ICorDebugThread3`) especifica la versión de la interfaz, no la versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="aa69a-278">The number that appears at the end of the interface names in the debugging API (for example, the "3" in `ICorDebugThread3`) specifies the version of the interface, not the version of the .NET Framework.</span></span> <span data-ttu-id="aa69a-279">Todos los nombres de interfaz en la API de depuración incluyen números de versión, excepto las interfaces que se incorporaron en .NET Framework versión 1.</span><span class="sxs-lookup"><span data-stu-id="aa69a-279">All interface names in the debugging API include version numbers except for interfaces that were introduced in the .NET Framework version 1.</span></span> <span data-ttu-id="aa69a-280">Cualquier correspondencia entre los números de versión de las interfaces y los números de versión de .NET Framework es pura coincidencia.</span><span class="sxs-lookup"><span data-stu-id="aa69a-280">Any correspondence between interface version numbers and.NET Framework version numbers are coincidental.</span></span>  
  
- <span data-ttu-id="aa69a-281">Las interfaces que se incorporaron en .NET Framework versión 1.0 no incluyen números, porque implícitamente son todas de la versión 1.</span><span class="sxs-lookup"><span data-stu-id="aa69a-281">Interfaces that were introduced in the .NET Framework version 1.0 do not include numbers, because they are all implicitly version 1.</span></span>  
  
- <span data-ttu-id="aa69a-282">.NET Framework versión 1.1 usa las interfaces de la versión 1.0 y no incorpora ninguna interfaz de depuración nueva.</span><span class="sxs-lookup"><span data-stu-id="aa69a-282">The .NET Framework version 1.1 uses version 1.0 interfaces, and does not introduce any new debugging interfaces.</span></span>  
  
- <span data-ttu-id="aa69a-283">Las 14 interfaces de depuración que se incorporaron en .NET Framework versión 2.0 son extensiones lógicas de sus homólogas de la versión 1, e incluyen el número "2" en sus nombres.</span><span class="sxs-lookup"><span data-stu-id="aa69a-283">The 14 debugging interfaces introduced in the .NET Framework version 2.0 are logical extensions of their version 1 counterparts and include the number "2" in their names.</span></span>  
  
- <span data-ttu-id="aa69a-284">.NET Framework versión 3.0 y versión 3.5 usa las interfaces de .NET Framework 2.0 existentes y no incorpora ninguna interfaz nueva.</span><span class="sxs-lookup"><span data-stu-id="aa69a-284">The .NET Framework versions 3.0 and 3.5 use the existing .NET Framework 2.0 interfaces, and do not introduce any new interfaces.</span></span>  
  
- <span data-ttu-id="aa69a-285">El .NET Framework 4 introduce una combinación de versiones de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="aa69a-285">The .NET Framework 4 introduces a mix of interface versions.</span></span> <span data-ttu-id="aa69a-286">Por ejemplo, tanto `ICorDebugThread3` como `ICorDebugThread4` aparecen como la tercera y cuarta versión de la interfaz `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="aa69a-286">For example, both `ICorDebugThread3` and `ICorDebugThread4` appear as the third and fourth versions of the `ICorDebugThread` interface.</span></span> <span data-ttu-id="aa69a-287">El .NET Framework 4 también presenta la primera versión de la interfaz de `ICorDebugStackWalk` y la segunda versión de la interfaz de `ICorDebugNativeFrame` (`ICorDebugNativeFrame2`).</span><span class="sxs-lookup"><span data-stu-id="aa69a-287">The .NET Framework 4 also introduces the first version of the `ICorDebugStackWalk` interface and the second version of the `ICorDebugNativeFrame` interface (`ICorDebugNativeFrame2`).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa69a-288">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="aa69a-288">Requirements</span></span>  
 <span data-ttu-id="aa69a-289">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa69a-289">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa69a-290">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aa69a-290">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aa69a-291">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa69a-291">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aa69a-292">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa69a-292">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa69a-293">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa69a-293">See also</span></span>

- [<span data-ttu-id="aa69a-294">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="aa69a-294">Debugging Enumerations</span></span>](debugging-enumerations.md)
