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
# <a name="cordebugregister-enumeration"></a>CorDebugRegister (Enumeración)

Especifica los registros asociados con una arquitectura de procesador determinada.  
  
## <a name="syntax"></a>Sintaxis  
  
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
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`REGISTER_INSTRUCTION_POINTER`|Registro de puntero de instrucción en un procesador cualquiera.|  
|`REGISTER_STACK_POINTER`|Registro de puntero de pila en un procesador cualquiera.|  
|`REGISTER_FRAME_POINTER`|Registro de puntero de marco en un procesador cualquiera.|  
|`REGISTER_X86_EIP`|Registro de puntero de instrucción en el procesador x86.|  
|`REGISTER_X86_ESP`|Registro de puntero de pila en el procesador x86.|  
|`REGISTER_X86_EBP`|Registro de puntero base en el procesador x86.|  
|`REGISTER_X86_EAX`|Registro de datos A en el procesador x86.|  
|`REGISTER_X86_ECX`|Registro de datos C en el procesador x86.|  
|`REGISTER_X86_EDX`|Registro de datos D en el procesador x86.|  
|`REGISTER_X86_EBX`|Registro de datos B en el procesador x86.|  
|`REGISTER_X86_ESI`|Registro de índice de origen en el procesador x86.|  
|`REGISTER_X86_EDI`|Registro de índice de destino en el procesador x86.|  
|`REGISTER_X86_FPSTACK_0`|Registro de pila 0 en el procesador de punto flotante (FP) x86.|  
|`REGISTER_X86_FPSTACK_1`|Registro de pila número 1 en el procesador FP x86.|  
|`REGISTER_X86_FPSTACK_2`|Registro de pila número 2 en el procesador FP x86.|  
|`REGISTER_X86_FPSTACK_3`|Registro de pila número 3 en el procesador FP x86.|  
|`REGISTER_X86_FPSTACK_4`|Registro de pila número 4 en el procesador FP x86.|  
|`REGISTER_X86_FPSTACK_5`|Registro de pila número 5 en el procesador FP x86.|  
|`REGISTER_X86_FPSTACK_6`|Registro de pila número 6 en el procesador FP x86.|  
|`REGISTER_X86_FPSTACK_7`|Registro de pila número 7 en el procesador FP x86.|  
|`REGISTER_AMD64_RIP`|Registro de puntero de instrucción en el procesador AMD64.|  
|`REGISTER_AMD64_RSP`|Registro de puntero de pila en el procesador AMD64.|  
|`REGISTER_AMD64_RBP`|Registro de puntero base en el procesador AMD64.|  
|`REGISTER_AMD64_RAX`|Registro de datos A en el procesador AMD64.|  
|`REGISTER_AMD64_RCX`|Registro de datos C en el procesador AMD64.|  
|`REGISTER_AMD64_RDX`|Registro de datos D en el procesador AMD64.|  
|`REGISTER_AMD64_RBX`|Registro de datos B en el procesador AMD64.|  
|`REGISTER_AMD64_RSI`|Registro de índice de origen en el procesador AMD64.|  
|`REGISTER_AMD64_RDI`|Registro de índice de destino en el procesador AMD64.|  
|`REGISTER_AMD64_R8`|Registro de datos número 8 en el procesador AMD64.|  
|`REGISTER_AMD64_R9`|Registro de datos número 9 en el procesador AMD64.|  
|`REGISTER_AMD64_R10`|Registro de datos número 10 en el procesador AMD64.|  
|`REGISTER_AMD64_R11`|Registro de datos número 11 en el procesador AMD64.|  
|`REGISTER_AMD64_R12`|Registro de datos número 12 en el procesador AMD64.|  
|`REGISTER_AMD64_R13`|Registro de datos número 13 en el procesador AMD64.|  
|`REGISTER_AMD64_R14`|Registro de datos número 14 en el procesador AMD64.|  
|`REGISTER_AMD64_R15`|Registro de datos número 15 en el procesador AMD64.|  
|`REGISTER_AMD64_XMM0`|Registro multimedia número 0 en el procesador AMD64.|  
|`REGISTER_AMD64_XMM1`|Registro multimedia número 1 en el procesador AMD64.|  
|`REGISTER_AMD64_XMM2`|Registro multimedia número 2 en el procesador AMD64.|  
|`REGISTER_AMD64_XMM3`|Registro multimedia número 3 en el procesador AMD64.|  
|`REGISTER_AMD64_XMM4`|Registro multimedia número 4 en el procesador AMD64.|  
|`REGISTER_AMD64_XMM5`|Registro multimedia número 5 en el procesador AMD64.|  
|`REGISTER_AMD64_XMM6`|Registro multimedia número 6 en el procesador AMD64.|  
|`REGISTER_AMD64_XMM7`|Registro multimedia número 7 en el procesador AMD64.|  
|`REGISTER_AMD64_XMM8`|Registro multimedia número 8 en el procesador AMD64.|  
|`REGISTER_AMD64_XMM9`|Registro multimedia número 9 en el procesador AMD64.|  
|`REGISTER_AMD64_XMM10`|Registro multimedia número 10 en el procesador AMD64.|  
|`REGISTER_AMD64_XMM11`|Registro multimedia número 11 en el procesador AMD64.|  
|`REGISTER_AMD64_XMM12`|Registro multimedia número 12 en el procesador AMD64.|  
|`REGISTER_AMD64_XMM13`|Registro multimedia número 13 en el procesador AMD64.|  
|`REGISTER_AMD64_XMM14`|Registro multimedia número 14 en el procesador AMD64.|  
|`REGISTER_AMD64_XMM15`|Registro multimedia número 15 en el procesador AMD64.|  
|`REGISTER_IA64_BSP`|Registro de puntero de pila en el procesador IA-64.|  
|`REGISTER_IA64_R0`|Registro de datos número 0 en el procesador IA-64.|  
|`REGISTER_IA64_F0`|Registro de datos FP número 0 en el procesador IA-64.|  
|`REGISTER_ARM_PC`|Registro de contador de programas (R15) en el procesador ARM.|  
|`REGISTER_ARM_SP`|Registro de puntero de pila (R13) en el procesador ARM.|  
|`REGISTER_ARM_R0`|Registro de datos R0 en el procesador ARM.|  
|`REGISTER_ARM_R1`|Registro de datos R1 en el procesador ARM.|  
|`REGISTER_ARM_R2`|Registro de datos R2 en el procesador ARM.|  
|`REGISTER_ARM_R3`|Registro de datos R3 en el procesador ARM.|  
|`REGISTER_ARM_R4`|Registro R4 en el procesador ARM.|  
|`REGISTER_ARM_R5`|Registro R5 en el procesador ARM.|  
|`REGISTER_ARM_R6`|Registro R6 en el procesador ARM.|  
|`REGISTER_ARM_R7`|Registro R7 (puntero de marco THUMB) en el procesador ARM.|  
|`REGISTER_ARM_R8`|Registro R8 en el procesador ARM.|  
|`REGISTER_ARM_R9`|Registro R9 en el procesador ARM.|  
|`REGISTER_ARM_R10`|Registro R10 en el procesador ARM.|  
|`REGISTER_ARM_R11`|Puntero de marco en el procesador ARM.|  
|`REGISTER_ARM_R12`|Registro R12 en el procesador ARM.|  
|`REGISTER_ARM_LR`|Registro de vínculo (R14) en el procesador ARM.|  
  
## <a name="remarks"></a>Observaciones  

 Hay 128 registros de datos de uso general y 128 registros de datos de punto flotante en el procesador IA-64, pero solo se proporcionan los valores `REGISTER_IA64_R0` y `REGISTER_IA64_F0`. Los demás valores se pueden determinar de la siguiente manera:  
  
- Agregue el número de registro a `REGISTER_IA64_R0` para los valores `REGISTER_IA64_R1` a `REGISTER_IA64_R127`, que corresponden a los registros de datos del número 1 al número 127 en el procesador IA-64.  
  
- Agregue el número de registro a `REGISTER_IA64_F0` para los valores `REGISTER_IA64_F1` a `REGISTER_IA64_F127`, que corresponden a los registros de datos FP del número 1 al número 127 en el procesador IA-64.  
  
 Por ejemplo, si necesita especificar el registro de datos número 83 en el procesador IA-64, use `REGISTER_IA64_R0` + 83.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de depuración](debugging-enumerations.md)
