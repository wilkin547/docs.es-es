---
description: 'Más información sobre: enumeración CorDebugRegister ('
title: CorDebugRegister (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugRegister
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugRegister
helpviewer_keywords:
- CorDebugRegister enumeration [.NET Framework debugging]
ms.assetid: 003bb138-7960-4291-ac88-0d87e470ff70
topic_type:
- apiref
ms.openlocfilehash: 7a5dc771a239a82448f898e2f518e920993ec35a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661891"
---
# <a name="cordebugregister-enumeration"></a><span data-ttu-id="4ca4b-103">CorDebugRegister (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="4ca4b-103">CorDebugRegister Enumeration</span></span>

<span data-ttu-id="4ca4b-104">Especifica los registros asociados con una arquitectura de procesador determinada.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-104">Specifies the registers associated with a given processor architecture.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ca4b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4ca4b-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="4ca4b-106">Members</span><span class="sxs-lookup"><span data-stu-id="4ca4b-106">Members</span></span>  
  
|<span data-ttu-id="4ca4b-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="4ca4b-107">Member</span></span>|<span data-ttu-id="4ca4b-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="4ca4b-108">Description</span></span>|  
|------------|-----------------|  
|`REGISTER_INSTRUCTION_POINTER`|<span data-ttu-id="4ca4b-109">Registro de puntero de instrucción en un procesador cualquiera.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-109">An instruction pointer register on any processor.</span></span>|  
|`REGISTER_STACK_POINTER`|<span data-ttu-id="4ca4b-110">Registro de puntero de pila en un procesador cualquiera.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-110">A stack pointer register on any processor.</span></span>|  
|`REGISTER_FRAME_POINTER`|<span data-ttu-id="4ca4b-111">Registro de puntero de marco en un procesador cualquiera.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-111">A frame pointer register on any processor.</span></span>|  
|`REGISTER_X86_EIP`|<span data-ttu-id="4ca4b-112">Registro de puntero de instrucción en el procesador x86.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-112">The instruction pointer register on the x86 processor.</span></span>|  
|`REGISTER_X86_ESP`|<span data-ttu-id="4ca4b-113">Registro de puntero de pila en el procesador x86.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-113">The stack pointer register on the x86 processor.</span></span>|  
|`REGISTER_X86_EBP`|<span data-ttu-id="4ca4b-114">Registro de puntero base en el procesador x86.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-114">The base pointer register on the x86 processor.</span></span>|  
|`REGISTER_X86_EAX`|<span data-ttu-id="4ca4b-115">Registro de datos A en el procesador x86.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-115">The A data register on the x86 processor.</span></span>|  
|`REGISTER_X86_ECX`|<span data-ttu-id="4ca4b-116">Registro de datos C en el procesador x86.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-116">The C data register on the x86 processor.</span></span>|  
|`REGISTER_X86_EDX`|<span data-ttu-id="4ca4b-117">Registro de datos D en el procesador x86.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-117">The D data register on the x86 processor.</span></span>|  
|`REGISTER_X86_EBX`|<span data-ttu-id="4ca4b-118">Registro de datos B en el procesador x86.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-118">The B data register on the x86 processor.</span></span>|  
|`REGISTER_X86_ESI`|<span data-ttu-id="4ca4b-119">Registro de índice de origen en el procesador x86.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-119">The source index register on the x86 processor.</span></span>|  
|`REGISTER_X86_EDI`|<span data-ttu-id="4ca4b-120">Registro de índice de destino en el procesador x86.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-120">The destination index register on the x86 processor.</span></span>|  
|`REGISTER_X86_FPSTACK_0`|<span data-ttu-id="4ca4b-121">Registro de pila 0 en el procesador de punto flotante (FP) x86.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-121">The stack register 0 on the x86 floating-point (FP) processor.</span></span>|  
|`REGISTER_X86_FPSTACK_1`|<span data-ttu-id="4ca4b-122">Registro de pila número 1 en el procesador FP x86.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-122">The #1 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_2`|<span data-ttu-id="4ca4b-123">Registro de pila número 2 en el procesador FP x86.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-123">The #2 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_3`|<span data-ttu-id="4ca4b-124">Registro de pila número 3 en el procesador FP x86.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-124">The #3 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_4`|<span data-ttu-id="4ca4b-125">Registro de pila número 4 en el procesador FP x86.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-125">The #4 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_5`|<span data-ttu-id="4ca4b-126">Registro de pila número 5 en el procesador FP x86.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-126">The #5 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_6`|<span data-ttu-id="4ca4b-127">Registro de pila número 6 en el procesador FP x86.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-127">The #6 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_X86_FPSTACK_7`|<span data-ttu-id="4ca4b-128">Registro de pila número 7 en el procesador FP x86.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-128">The #7 stack register on the x86 FP processor.</span></span>|  
|`REGISTER_AMD64_RIP`|<span data-ttu-id="4ca4b-129">Registro de puntero de instrucción en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-129">The instruction pointer register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RSP`|<span data-ttu-id="4ca4b-130">Registro de puntero de pila en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-130">The stack pointer register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RBP`|<span data-ttu-id="4ca4b-131">Registro de puntero base en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-131">The base pointer register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RAX`|<span data-ttu-id="4ca4b-132">Registro de datos A en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-132">The A data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RCX`|<span data-ttu-id="4ca4b-133">Registro de datos C en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-133">The C data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RDX`|<span data-ttu-id="4ca4b-134">Registro de datos D en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-134">The D data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RBX`|<span data-ttu-id="4ca4b-135">Registro de datos B en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-135">The B data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RSI`|<span data-ttu-id="4ca4b-136">Registro de índice de origen en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-136">The source index register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_RDI`|<span data-ttu-id="4ca4b-137">Registro de índice de destino en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-137">The destination index register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R8`|<span data-ttu-id="4ca4b-138">Registro de datos número 8 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-138">The #8 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R9`|<span data-ttu-id="4ca4b-139">Registro de datos número 9 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-139">The #9 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R10`|<span data-ttu-id="4ca4b-140">Registro de datos número 10 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-140">The #10 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R11`|<span data-ttu-id="4ca4b-141">Registro de datos número 11 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-141">The #11 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R12`|<span data-ttu-id="4ca4b-142">Registro de datos número 12 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-142">The #12 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R13`|<span data-ttu-id="4ca4b-143">Registro de datos número 13 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-143">The #13 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R14`|<span data-ttu-id="4ca4b-144">Registro de datos número 14 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-144">The #14 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_R15`|<span data-ttu-id="4ca4b-145">Registro de datos número 15 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-145">The #15 data register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM0`|<span data-ttu-id="4ca4b-146">Registro multimedia número 0 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-146">The #0 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM1`|<span data-ttu-id="4ca4b-147">Registro multimedia número 1 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-147">The #1 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM2`|<span data-ttu-id="4ca4b-148">Registro multimedia número 2 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-148">The #2 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM3`|<span data-ttu-id="4ca4b-149">Registro multimedia número 3 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-149">The #3 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM4`|<span data-ttu-id="4ca4b-150">Registro multimedia número 4 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-150">The #4 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM5`|<span data-ttu-id="4ca4b-151">Registro multimedia número 5 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-151">The #5 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM6`|<span data-ttu-id="4ca4b-152">Registro multimedia número 6 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-152">The #6 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM7`|<span data-ttu-id="4ca4b-153">Registro multimedia número 7 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-153">The #7 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM8`|<span data-ttu-id="4ca4b-154">Registro multimedia número 8 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-154">The #8 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM9`|<span data-ttu-id="4ca4b-155">Registro multimedia número 9 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-155">The #9 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM10`|<span data-ttu-id="4ca4b-156">Registro multimedia número 10 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-156">The #10 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM11`|<span data-ttu-id="4ca4b-157">Registro multimedia número 11 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-157">The #11 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM12`|<span data-ttu-id="4ca4b-158">Registro multimedia número 12 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-158">The #12 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM13`|<span data-ttu-id="4ca4b-159">Registro multimedia número 13 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-159">The #13 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM14`|<span data-ttu-id="4ca4b-160">Registro multimedia número 14 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-160">The #14 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_AMD64_XMM15`|<span data-ttu-id="4ca4b-161">Registro multimedia número 15 en el procesador AMD64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-161">The #15 multimedia register on the AMD64 processor.</span></span>|  
|`REGISTER_IA64_BSP`|<span data-ttu-id="4ca4b-162">Registro de puntero de pila en el procesador IA-64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-162">The stack pointer register on the IA-64 processor.</span></span>|  
|`REGISTER_IA64_R0`|<span data-ttu-id="4ca4b-163">Registro de datos número 0 en el procesador IA-64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-163">The #0 data register on the IA-64 processor.</span></span>|  
|`REGISTER_IA64_F0`|<span data-ttu-id="4ca4b-164">Registro de datos FP número 0 en el procesador IA-64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-164">The #0 FP data register on the IA-64 processor.</span></span>|  
|`REGISTER_ARM_PC`|<span data-ttu-id="4ca4b-165">Registro de contador de programas (R15) en el procesador ARM.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-165">The program counter register (R15) on the ARM processor.</span></span>|  
|`REGISTER_ARM_SP`|<span data-ttu-id="4ca4b-166">Registro de puntero de pila (R13) en el procesador ARM.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-166">The stack pointer register (R13) on the ARM processor.</span></span>|  
|`REGISTER_ARM_R0`|<span data-ttu-id="4ca4b-167">Registro de datos R0 en el procesador ARM.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-167">Data register R0 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R1`|<span data-ttu-id="4ca4b-168">Registro de datos R1 en el procesador ARM.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-168">Data register R1 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R2`|<span data-ttu-id="4ca4b-169">Registro de datos R2 en el procesador ARM.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-169">Data register R2 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R3`|<span data-ttu-id="4ca4b-170">Registro de datos R3 en el procesador ARM.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-170">Data register R3 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R4`|<span data-ttu-id="4ca4b-171">Registro R4 en el procesador ARM.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-171">Register R4 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R5`|<span data-ttu-id="4ca4b-172">Registro R5 en el procesador ARM.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-172">Register R5 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R6`|<span data-ttu-id="4ca4b-173">Registro R6 en el procesador ARM.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-173">Register R6 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R7`|<span data-ttu-id="4ca4b-174">Registro R7 (puntero de marco THUMB) en el procesador ARM.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-174">Register R7 (the THUMB frame pointer) on the ARM processor.</span></span>|  
|`REGISTER_ARM_R8`|<span data-ttu-id="4ca4b-175">Registro R8 en el procesador ARM.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-175">Register R8 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R9`|<span data-ttu-id="4ca4b-176">Registro R9 en el procesador ARM.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-176">Register R9 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R10`|<span data-ttu-id="4ca4b-177">Registro R10 en el procesador ARM.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-177">Register R10 on the ARM processor.</span></span>|  
|`REGISTER_ARM_R11`|<span data-ttu-id="4ca4b-178">Puntero de marco en el procesador ARM.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-178">The frame pointer on the ARM processor.</span></span>|  
|`REGISTER_ARM_R12`|<span data-ttu-id="4ca4b-179">Registro R12 en el procesador ARM.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-179">Register R12 on the ARM processor.</span></span>|  
|`REGISTER_ARM_LR`|<span data-ttu-id="4ca4b-180">Registro de vínculo (R14) en el procesador ARM.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-180">The link register (R14) on the ARM processor.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ca4b-181">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4ca4b-181">Remarks</span></span>  

 <span data-ttu-id="4ca4b-182">Hay 128 registros de datos de uso general y 128 registros de datos de punto flotante en el procesador IA-64, pero solo se proporcionan los valores `REGISTER_IA64_R0` y `REGISTER_IA64_F0`.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-182">There are 128 general-purpose data registers and 128 floating-point data registers on the IA-64 processor, but only values `REGISTER_IA64_R0` and `REGISTER_IA64_F0` are provided.</span></span> <span data-ttu-id="4ca4b-183">Los demás valores se pueden determinar de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="4ca4b-183">The other values can be determined as follows:</span></span>  
  
- <span data-ttu-id="4ca4b-184">Agregue el número de registro a `REGISTER_IA64_R0` para los valores `REGISTER_IA64_R1` a `REGISTER_IA64_R127`, que corresponden a los registros de datos del número 1 al número 127 en el procesador IA-64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-184">Add the register number to `REGISTER_IA64_R0` for values `REGISTER_IA64_R1` through `REGISTER_IA64_R127`, which correspond to the #1 data register through the #127 data register on the IA-64 processor.</span></span>  
  
- <span data-ttu-id="4ca4b-185">Agregue el número de registro a `REGISTER_IA64_F0` para los valores `REGISTER_IA64_F1` a `REGISTER_IA64_F127`, que corresponden a los registros de datos FP del número 1 al número 127 en el procesador IA-64.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-185">Add the register number to `REGISTER_IA64_F0` for values `REGISTER_IA64_F1` through `REGISTER_IA64_F127`, which correspond to the #1 FP data register through the #127 FP data register on the IA-64 processor.</span></span>  
  
 <span data-ttu-id="4ca4b-186">Por ejemplo, si necesita especificar el registro de datos número 83 en el procesador IA-64, use `REGISTER_IA64_R0` + 83.</span><span class="sxs-lookup"><span data-stu-id="4ca4b-186">For example, if you need to specify the #83 data register on the IA-64 processor, use `REGISTER_IA64_R0` + 83.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ca4b-187">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4ca4b-187">Requirements</span></span>  

 <span data-ttu-id="4ca4b-188">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ca4b-188">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ca4b-189">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4ca4b-189">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4ca4b-190">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ca4b-190">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ca4b-191">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ca4b-191">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ca4b-192">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ca4b-192">See also</span></span>

- [<span data-ttu-id="4ca4b-193">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="4ca4b-193">Debugging Enumerations</span></span>](debugging-enumerations.md)
