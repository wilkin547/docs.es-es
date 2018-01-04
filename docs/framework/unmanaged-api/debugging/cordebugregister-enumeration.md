---
title: "CorDebugRegister (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugRegister
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugRegister
helpviewer_keywords: CorDebugRegister enumeration [.NET Framework debugging]
ms.assetid: 003bb138-7960-4291-ac88-0d87e470ff70
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3f168e686a127b2763099d2cfaea7ff396c4e734
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugregister-enumeration"></a><span data-ttu-id="ac00e-102">CorDebugRegister (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="ac00e-102">CorDebugRegister Enumeration</span></span>
<span data-ttu-id="ac00e-103">Especifica los registros asociados con una arquitectura de procesador determinada.</span><span class="sxs-lookup"><span data-stu-id="ac00e-103">Specifies the registers associated with a given processor architecture.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac00e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac00e-104">Syntax</span></span>  
  
```  
typedef enum CorDebugRegister {  
  
    REGISTER_INSTRUCTION_POINTER = 0,  
    REGISTER_STACK_POINTER,  
    REGISTER_FRAME_POINTER,  
  
    REGISTER_X86_EIP = 0,  
    REGISTER_X86_ESP,  
    REGISTER_X86_EBP,  
  
    REGISTER_X86_EAX,  
    REGISTER_X86_ECX,  
    REGISTER_X86_EDX,  
    REGISTER_X86_EBX,  
  
    REGISTER_X86_ESI,  
    REGISTER_X86_EDI,  
  
    REGISTER_X86_FPSTACK_0,  
    REGISTER_X86_FPSTACK_1,  
    REGISTER_X86_FPSTACK_2,  
    REGISTER_X86_FPSTACK_3,  
    REGISTER_X86_FPSTACK_4,  
    REGISTER_X86_FPSTACK_5,  
    REGISTER_X86_FPSTACK_6,  
    REGISTER_X86_FPSTACK_7,  
  
    REGISTER_AMD64_RIP = 0,  
    REGISTER_AMD64_RSP,  
    REGISTER_AMD64_RBP,  
    REGISTER_AMD64_RAX,  
    REGISTER_AMD64_RCX,  
    REGISTER_AMD64_RDX,  
    REGISTER_AMD64_RBX,  
    REGISTER_AMD64_RSI,  
    REGISTER_AMD64_RDI,  
    REGISTER_AMD64_R8,  
    REGISTER_AMD64_R9,  
    REGISTER_AMD64_R10,  
    REGISTER_AMD64_R11,  
    REGISTER_AMD64_R12,  
    REGISTER_AMD64_R13,  
    REGISTER_AMD64_R14,  
    REGISTER_AMD64_R15,  
  
    REGISTER_AMD64_XMM0,  
    REGISTER_AMD64_XMM1,  
    REGISTER_AMD64_XMM2,  
    REGISTER_AMD64_XMM3,  
    REGISTER_AMD64_XMM4,  
    REGISTER_AMD64_XMM5,  
    REGISTER_AMD64_XMM6,  
    REGISTER_AMD64_XMM7,  
    REGISTER_AMD64_XMM8,  
    REGISTER_AMD64_XMM9,  
    REGISTER_AMD64_XMM10,  
    REGISTER_AMD64_XMM11,  
    REGISTER_AMD64_XMM12,  
    REGISTER_AMD64_XMM13,  
    REGISTER_AMD64_XMM14,  
    REGISTER_AMD64_XMM15,  
  
    REGISTER_IA64_BSP = REGISTER_FRAME_POINTER,  
    REGISTER_IA64_R0  = REGISTER_IA64_BSP + 1,  
    REGISTER_IA64_F0  = REGISTER_IA64_R0  + 128,  
    REGISTER_ARM_PC = 0,  
    REGISTER_ARM_SP,  
    REGISTER_ARM_R0,  
    REGISTER_ARM_R1,  
    REGISTER_ARM_R2,  
    REGISTER_ARM_R3,  
    REGISTER_ARM_R4,  
    REGISTER_ARM_R5,  
    REGISTER_ARM_R6,  
    REGISTER_ARM_R7,  
    REGISTER_ARM_R8,  
    REGISTER_ARM_R9,  
    REGISTER_ARM_R10,  
    REGISTER_ARM_R11,  
    REGISTER_ARM_R12,  
    REGISTER_ARM_LR,  
  
} CorDebugRegister;  
```  
  
## <a name="members"></a><span data-ttu-id="ac00e-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="ac00e-105">Members</span></span>  
  
|<span data-ttu-id="ac00e-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="ac00e-106">Member</span></span>|<span data-ttu-id="ac00e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ac00e-107">Description</span></span>|  
|------------|-----------------|  
|`REGISTER_INSTRUCTION_POINTER`|<span data-ttu-id="ac00e-108">Registro de puntero de instrucción en un procesador cualquiera.</span><span class="sxs-lookup"><span data-stu-id="ac00e-108">An instruction pointer register on any processor.</span></span>|  
|`REGISTER_STACK_POINTER`|<span data-ttu-id="ac00e-109">Registro de puntero de pila en un procesador cualquiera.</span><span class="sxs-lookup"><span data-stu-id="ac00e-109">A stack pointer register on any processor.</span></span>|  
|`REGISTER_FRAME_POINTER`|<span data-ttu-id="ac00e-110">Registro de puntero de marco en un procesador cualquiera.</span><span class="sxs-lookup"><span data-stu-id="ac00e-110">A frame pointer register on any processor.</span></span>|  
|`REGISTER_X86_EIP`|<span data-ttu-id="ac00e-111">Registro de puntero de instrucción en el procesador x86.</span><span class="sxs-lookup"><span data-stu-id="ac00e-111">The instruction pointer register on the x86 processor.</span></span>|  
|`REGISTER_X86_ESP`|<span data-ttu-id="ac00e-112">Registro de puntero de pila en el procesador x86.</span><span class="sxs-lookup"><span data-stu-id="ac00e-112">The stack pointer register on the x86 processor.</span></span>|  
|`REGISTER_X86_EBP`|<span data-ttu-id="ac00e-113">Registro de puntero base en el procesador x86.</span><span class="sxs-lookup"><span data-stu-id="ac00e-113">The base pointer register on the x86 processor.</span></span>|  
|`REGISTER_X86_EAX`|<span data-ttu-id="ac00e-114">Registro de datos A en el procesador x86.</span><span class="sxs-lookup"><span data-stu-id="ac00e-114">The A data register on the x86 processor.</span></span>|  
|`REGISTER_X86_ECX`|<span data-ttu-id="ac00e-115">Registro de datos C en el procesador x86.</span><span class="sxs-lookup"><span data-stu-id="ac00e-115">The C data register on the x86 processor.</span></span>|  
|`REGISTER_X86_EDX`|<span data-ttu-id="ac00e-116">Registro de datos D en el procesador x86.</span><span class="sxs-lookup"><span data-stu-id="ac00e-116">The D data register on the x86 processor.</span></span>|  
|`REGISTER_X86_EBX`|<span data-ttu-id="ac00e-117">Registro de datos B en el procesador x86.</span><span class="sxs-lookup"><span data-stu-id="ac00e-117">The B data register on the x86 processor.</span></span>|  
|`REGISTER_X86_ESI`|<span data-ttu-id="ac00e-118">Registro de índice de origen en el procesador x86.</span><span class="sxs-lookup"><span data-stu-id="ac00e-118">The source index register on the x86 processor.</span></span>|  
|`REGISTER_X86_EDI`|<span data-ttu-id="ac00e-119">Registro de índice de destino en el procesador x86.</span><span class="sxs-lookup"><span data-stu-id="ac00e-119">The destination index register on the x86 processor.</span></span>|  
|`REGISTER_X86_FPSTACK_0`|<span data-ttu-id="ac00e-120">Registro de pila 0 en el procesador de punto flotante (FP) x86.</span><span class="sxs-lookup"><span data-stu-id="ac00e-120">The stack register 0 on the x86 floating-point (FP) processor.</span></span>|  
|`REGISTER_X86_FPSTACK_1`|<span data-ttu-id="ac00e-121">Registro de pila número 1 en el procesador FP x86.</span><span class="sxs-lookup"><span data-stu-id="ac00e-121">The #1 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_2`|<span data-ttu-id="ac00e-122">Registro de pila número 2 en el procesador FP x86.</span><span class="sxs-lookup"><span data-stu-id="ac00e-122">The #2 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_3`|<span data-ttu-id="ac00e-123">Registro de pila número 3 en el procesador FP x86.</span><span class="sxs-lookup"><span data-stu-id="ac00e-123">The #3 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_4`|<span data-ttu-id="ac00e-124">Registro de pila número 4 en el procesador FP x86.</span><span class="sxs-lookup"><span data-stu-id="ac00e-124">The #4 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_5`|<span data-ttu-id="ac00e-125">Registro de pila número 5 en el procesador FP x86.</span><span class="sxs-lookup"><span data-stu-id="ac00e-125">The #5 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_6`|<span data-ttu-id="ac00e-126">Registro de pila número 6 en el procesador FP x86.</span><span class="sxs-lookup"><span data-stu-id="ac00e-126">The #6 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_7`|<span data-ttu-id="ac00e-127">Registro de pila número 7 en el procesador FP x86.</span><span class="sxs-lookup"><span data-stu-id="ac00e-127">The #7 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_AMD64_RIP`|<span data-ttu-id="ac00e-128">Registro de puntero de instrucción en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-128">The instruction pointer register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RSP`|<span data-ttu-id="ac00e-129">Registro de puntero de pila en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-129">The stack pointer register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RBP`|<span data-ttu-id="ac00e-130">Registro de puntero base en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-130">The base pointer register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RAX`|<span data-ttu-id="ac00e-131">Registro de datos A en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-131">The A data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RCX`|<span data-ttu-id="ac00e-132">Registro de datos C en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-132">The C data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RDX`|<span data-ttu-id="ac00e-133">Registro de datos D en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-133">The D data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RBX`|<span data-ttu-id="ac00e-134">Registro de datos B en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-134">The B data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RSI`|<span data-ttu-id="ac00e-135">Registro de índice de origen en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-135">The source index register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RDI`|<span data-ttu-id="ac00e-136">Registro de índice de destino en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-136">The destination index register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R8`|<span data-ttu-id="ac00e-137">Registro de datos número 8 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-137">The #8 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R9`|<span data-ttu-id="ac00e-138">Registro de datos número 9 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-138">The #9 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R10`|<span data-ttu-id="ac00e-139">Registro de datos número 10 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-139">The #10 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R11`|<span data-ttu-id="ac00e-140">Registro de datos número 11 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-140">The #11 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R12`|<span data-ttu-id="ac00e-141">Registro de datos número 12 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-141">The #12 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R13`|<span data-ttu-id="ac00e-142">Registro de datos número 13 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-142">The #13 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R14`|<span data-ttu-id="ac00e-143">Registro de datos número 14 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-143">The #14 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R15`|<span data-ttu-id="ac00e-144">Registro de datos número 15 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-144">The #15 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM0`|<span data-ttu-id="ac00e-145">Registro multimedia número 0 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-145">The #0 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM1`|<span data-ttu-id="ac00e-146">Registro multimedia número 1 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-146">The #1 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM2`|<span data-ttu-id="ac00e-147">Registro multimedia número 2 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-147">The #2 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM3`|<span data-ttu-id="ac00e-148">Registro multimedia número 3 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-148">The #3 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM4`|<span data-ttu-id="ac00e-149">Registro multimedia número 4 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-149">The #4 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM5`|<span data-ttu-id="ac00e-150">Registro multimedia número 5 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-150">The #5 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM6`|<span data-ttu-id="ac00e-151">Registro multimedia número 6 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-151">The #6 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM7`|<span data-ttu-id="ac00e-152">Registro multimedia número 7 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-152">The #7 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM8`|<span data-ttu-id="ac00e-153">Registro multimedia número 8 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-153">The #8 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM9`|<span data-ttu-id="ac00e-154">Registro multimedia número 9 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-154">The #9 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM10`|<span data-ttu-id="ac00e-155">Registro multimedia número 10 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-155">The #10 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM11`|<span data-ttu-id="ac00e-156">Registro multimedia número 11 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-156">The #11 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM12`|<span data-ttu-id="ac00e-157">Registro multimedia número 12 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-157">The #12 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM13`|<span data-ttu-id="ac00e-158">Registro multimedia número 13 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-158">The #13 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM14`|<span data-ttu-id="ac00e-159">Registro multimedia número 14 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-159">The #14 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM15`|<span data-ttu-id="ac00e-160">Registro multimedia número 15 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-160">The #15 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_IA64_BSP`|<span data-ttu-id="ac00e-161">Registro de puntero de pila en el procesador IA-64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-161">The stack pointer register on the IA-64 processor.</span></span>|  
|`REGISTER_IA64_R0`|<span data-ttu-id="ac00e-162">Registro de datos número 0 en el procesador IA-64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-162">The #0 data register on the IA-64 processor.</span></span>|  
|`REGISTER_IA64_F0`|<span data-ttu-id="ac00e-163">Registro de datos FP número 0 en el procesador IA-64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-163">The #0 FP data register on the IA-64 processor.</span></span>|  
|`REGISTER_ARM_PC`|<span data-ttu-id="ac00e-164">Registro de contador de programas (R15) en el procesador ARM.</span><span class="sxs-lookup"><span data-stu-id="ac00e-164">The program counter register (R15) on the ARM processor.</span></span>|  
|`REGISTER_ARM_SP`|<span data-ttu-id="ac00e-165">Registro de puntero de pila (R13) en el procesador ARM.</span><span class="sxs-lookup"><span data-stu-id="ac00e-165">The stack pointer register (R13) on the ARM processor.</span></span>|  
|`REGISTER_ARM_R0`|<span data-ttu-id="ac00e-166">Registro de datos R0 en el procesador ARM.</span><span class="sxs-lookup"><span data-stu-id="ac00e-166">Data register R0 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R1`|<span data-ttu-id="ac00e-167">Registro de datos R1 en el procesador ARM.</span><span class="sxs-lookup"><span data-stu-id="ac00e-167">Data register R1 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R2`|<span data-ttu-id="ac00e-168">Registro de datos R2 en el procesador ARM.</span><span class="sxs-lookup"><span data-stu-id="ac00e-168">Data register R2 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R3`|<span data-ttu-id="ac00e-169">Registro de datos R3 en el procesador ARM.</span><span class="sxs-lookup"><span data-stu-id="ac00e-169">Data register R3 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R4`|<span data-ttu-id="ac00e-170">Registro R4 en el procesador ARM.</span><span class="sxs-lookup"><span data-stu-id="ac00e-170">Register R4 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R5`|<span data-ttu-id="ac00e-171">Registro R5 en el procesador ARM.</span><span class="sxs-lookup"><span data-stu-id="ac00e-171">Register R5 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R6`|<span data-ttu-id="ac00e-172">Registro R6 en el procesador ARM.</span><span class="sxs-lookup"><span data-stu-id="ac00e-172">Register R6 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R7`|<span data-ttu-id="ac00e-173">Registro R7 (puntero de marco THUMB) en el procesador ARM.</span><span class="sxs-lookup"><span data-stu-id="ac00e-173">Register R7 (the THUMB frame pointer) on the ARM processor.</span></span>|  
|`REGISTER_ARM_R8`|<span data-ttu-id="ac00e-174">Registro R8 en el procesador ARM.</span><span class="sxs-lookup"><span data-stu-id="ac00e-174">Register R8 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R9`|<span data-ttu-id="ac00e-175">Registro R9 en el procesador ARM.</span><span class="sxs-lookup"><span data-stu-id="ac00e-175">Register R9 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R10`|<span data-ttu-id="ac00e-176">Registro R10 en el procesador ARM.</span><span class="sxs-lookup"><span data-stu-id="ac00e-176">Register R10 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R11`|<span data-ttu-id="ac00e-177">Puntero de marco en el procesador ARM.</span><span class="sxs-lookup"><span data-stu-id="ac00e-177">The frame pointer on the ARM processor.</span></span>|  
|`REGISTER_ARM_R12`|<span data-ttu-id="ac00e-178">Registro R12 en el procesador ARM.</span><span class="sxs-lookup"><span data-stu-id="ac00e-178">Register R12 on the ARM processor.</span></span>|  
|`REGISTER_ARM_LR`|<span data-ttu-id="ac00e-179">Registro de vínculo (R14) en el procesador ARM.</span><span class="sxs-lookup"><span data-stu-id="ac00e-179">The link register (R14) on the ARM processor.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac00e-180">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ac00e-180">Remarks</span></span>  
 <span data-ttu-id="ac00e-181">Hay 128 registros de datos de uso general y 128 registros de datos de punto flotante en el procesador IA-64, pero solo se proporcionan los valores `REGISTER_IA64_R0` y `REGISTER_IA64_F0`.</span><span class="sxs-lookup"><span data-stu-id="ac00e-181">There are 128 general-purpose data registers and 128 floating-point data registers on the IA-64 processor, but only values `REGISTER_IA64_R0` and `REGISTER_IA64_F0` are provided.</span></span> <span data-ttu-id="ac00e-182">Los demás valores se pueden determinar de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="ac00e-182">The other values can be determined as follows:</span></span>  
  
-   <span data-ttu-id="ac00e-183">Agregue el número de registro a `REGISTER_IA64_R0` para los valores `REGISTER_IA64_R1` a `REGISTER_IA64_R127`, que corresponden a los registros de datos del número 1 al número 127 en el procesador IA-64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-183">Add the register number to `REGISTER_IA64_R0` for values `REGISTER_IA64_R1` through `REGISTER_IA64_R127`, which correspond to the #1 data register through the #127 data register on the IA-64 processor.</span></span>  
  
-   <span data-ttu-id="ac00e-184">Agregue el número de registro a `REGISTER_IA64_F0` para los valores `REGISTER_IA64_F1` a `REGISTER_IA64_F127`, que corresponden a los registros de datos FP del número 1 al número 127 en el procesador IA-64.</span><span class="sxs-lookup"><span data-stu-id="ac00e-184">Add the register number to `REGISTER_IA64_F0` for values `REGISTER_IA64_F1` through `REGISTER_IA64_F127`, which correspond to the #1 FP data register through the #127 FP data register on the IA-64 processor.</span></span>  
  
 <span data-ttu-id="ac00e-185">Por ejemplo, si necesita especificar el registro de datos número 83 en el procesador IA-64, use `REGISTER_IA64_R0` + 83.</span><span class="sxs-lookup"><span data-stu-id="ac00e-185">For example, if you need to specify the #83 data register on the IA-64 processor, use `REGISTER_IA64_R0` + 83.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac00e-186">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ac00e-186">Requirements</span></span>  
 <span data-ttu-id="ac00e-187">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac00e-187">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac00e-188">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ac00e-188">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ac00e-189">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac00e-189">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac00e-190">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac00e-190">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac00e-191">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac00e-191">See Also</span></span>  
 [<span data-ttu-id="ac00e-192">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="ac00e-192">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
