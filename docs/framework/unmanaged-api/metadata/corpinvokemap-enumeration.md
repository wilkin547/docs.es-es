---
title: CorPinvokeMap (Enumeración)
ms.date: 03/30/2017
api_name:
- CorPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPinvokeMap
helpviewer_keywords:
- CorPinvokeMap enumeration [.NET Framework metadata]
ms.assetid: f14f986e-f6ce-42bc-aa23-18150c46d28c
topic_type:
- apiref
ms.openlocfilehash: 8216dc3030b18428ab52fbf8385d392f81057aa0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176154"
---
# <a name="corpinvokemap-enumeration"></a>CorPinvokeMap (Enumeración)
Especifica las opciones de una llamada PInvoke.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum  CorPinvokeMap {  
  
    pmNoMangle          = 0x0001,  
  
    pmCharSetMask       = 0x0006,  
    pmCharSetNotSpec    = 0x0000,  
    pmCharSetAnsi       = 0x0002,  
    pmCharSetUnicode    = 0x0004,  
    pmCharSetAuto       = 0x0006,  
  
    pmBestFitUseAssem   = 0x0000,  
    pmBestFitEnabled    = 0x0010,  
    pmBestFitDisabled   = 0x0020,  
    pmBestFitMask       = 0x0030,  
  
    pmThrowOnUnmappableCharUseAssem   = 0x0000,  
    pmThrowOnUnmappableCharEnabled    = 0x1000,  
    pmThrowOnUnmappableCharDisabled   = 0x2000,  
    pmThrowOnUnmappableCharMask       = 0x3000,  
  
    pmSupportsLastError = 0x0040,
  
    pmCallConvMask      = 0x0700,  
    pmCallConvWinapi    = 0x0100,  
    pmCallConvCdecl     = 0x0200,  
    pmCallConvStdcall   = 0x0300,  
    pmCallConvThiscall  = 0x0400,  
    pmCallConvFastcall  = 0x0500,  
  
    pmMaxValue          = 0xFFFF  
  
} CorPinvokeMap;  
```  
  
## <a name="members"></a>Members  
  
|Member|Descripción|  
|------------|-----------------|  
|`pmNoMangle`|Utilice cada nombre de miembro según lo especificado.|  
|`pmCharSetMask`|Reservado.|  
|`pmCharSetNotSpec`|Reservado.|  
|`pmCharSetAnsi`|Calcula las referencias de las cadenas como cadenas de caracteres de varios bytes.|  
|`pmCharSetUnicode`|Calcula referencias de las cadenas como caracteres Unicode de 2 bytes.|  
|`pmCharSetAuto`|Calcula automáticamente las referencias de las cadenas como corresponde al sistema operativo de destino. El valor predeterminado es Unicode en Windows NT, Windows 2000, Windows XP y la familia Windows Server 2003; el valor predeterminado es ANSI en Windows 98 y Windows Me.|  
|`pmBestFitUseAssem`|Reservado.|  
|`pmBestFitEnabled`|Realice la asignación de mejor ajuste de caracteres Unicode que carecen de una coincidencia exacta en el juego de caracteres ANSI.|  
|`pmBestFitDisabled`|No realice la asignación de mejor ajuste de caracteres Unicode. En este caso, todos los caracteres no manejables serán reemplazados por un '?'.|  
|`pmBestFitMask`|Reservado.|  
|`pmThrowOnUnmappableCharUseAssem`|Reservado.|  
|`pmThrowOnUnmappableCharEnabled`|Producir una excepción cuando el serializador de interoperabilidad encuentra un carácter que no se puede asignar.|  
|`pmThrowOnUnmappableCharDisabled`|No produzca una excepción cuando el serializador de interoperabilidad encuentre un carácter que no se pueda aplicar.|  
|`pmThrowOnUnmappableCharMask`|Reserved|  
|`pmSupportsLastError`|Permita que el destinatario llame `SetLastError` a la función Win32 antes de volver desde el método con atributos.|  
|`pmCallConvMask`|Reserved|  
|`pmCallConvWinapi`|Use la convención de llamada de plataforma predeterminada. Por ejemplo, en Windows `StdCall` el valor predeterminado es `Cdecl`y en Windows CE .NET es .|  
|`pmCallConvCdecl`|Use `Cdecl` la convención de llamada. En este caso, el autor de la llamada limpia la pila. Esto permite llamar `varargs` a funciones con (es decir, funciones que aceptan un número variable de parámetros).|  
|`pmCallConvStdcall`|Use `StdCall` la convención de llamada. En este caso, el destinatario limpia la pila. Esta es la convención predeterminada para la llamada a funciones no administradas con invocación de plataforma.|  
|`pmCallConvThiscall`|Use `ThisCall` la convención de llamada. En este caso, el `this` primer parámetro es el puntero y se almacena en el registro ECX. Los demás parámetros se insertan en la pila. La `ThisCall` convención de llamada se usa para llamar a métodos en clases exportadas desde un archivo DLL no administrado.|  
|`pmCallConvFastcall`|Reservado.|  
|`pmMaxValue`|Reservado.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
