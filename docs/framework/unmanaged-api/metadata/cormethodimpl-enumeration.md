---
title: CorMethodImpl (Enumeración)
ms.date: 03/30/2017
api_name:
- CorMethodImpl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodImpl
helpviewer_keywords:
- CorMethodImpl enumeration [.NET Framework metadata]
ms.assetid: ffbb3caf-20da-4a4b-8983-77376e72b990
topic_type:
- apiref
ms.openlocfilehash: b32e8f0b03ef6d550c384f3d932cc295a7270028
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007668"
---
# <a name="cormethodimpl-enumeration"></a>CorMethodImpl (Enumeración)
Contiene valores que describen las características de implementación de un método.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorMethodImpl {  
  
    miCodeTypeMask      =   0x0003,  
    miIL                =   0x0000,  
    miNative            =   0x0001,  
    miOPTIL             =   0x0002,  
    miRuntime           =   0x0003,  
  
    miManagedMask       =   0x0004,  
    miUnmanaged         =   0x0004,  
    miManaged           =   0x0000,  
  
    miForwardRef        =   0x0010,  
    miPreserveSig       =   0x0080,  
  
    miInternalCall      =   0x1000,  
    miSynchronized      =   0x0020,  
    miNoInlining        =   0x0008,  
    miAggressiveInlining =  0x0100,  
    miNoOptimization     =  0x0040,  
    miMaxMethodImplVal  =   0xffff  
  
} CorMethodImpl;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`miCodeTypeMask`|Marcas que describen el tipo de código.|  
|`miIL`|Especifica que la implementación del método es el lenguaje intermedio de Microsoft (MSIL).|  
|`miNative`|Especifica que la implementación del método es nativa.|  
|`miOPTIL`|Especifica que la implementación del método es OPTIl.|  
|`miRuntime`|Especifica que la implementación del método la proporciona el Common Language Runtime.|  
|`miManagedMask`|Marcas que indican si el código es administrado o no administrado.|  
|`miUnmanaged`|Especifica que la implementación del método no está administrada.|  
|`miManaged`|Especifica que la implementación del método está administrada.|  
|`miForwardRef`|Especifica que el método está definido. Esta marca se utiliza principalmente en escenarios de combinación.|  
|`miPreserveSig`|Especifica que la firma del método no se puede alterar para una conversión HRESULT.|  
|`miInternalCall`|Reservado para uso interno por el Common Language Runtime.|  
|`miSynchronized`|Especifica que el método tiene un único subproceso a través de su cuerpo.|  
|`miNoInlining`|Especifica que el método no se puede insertar.|  
|`miAggressiveInlining`|Especifica que el método debe insertarse si es posible.|  
|`miNoOptimization`|Especifica que el método no se debe optimizar.|  
|`miMaxMethodImplVal`|Valor máximo válido para `CorMethodImpl` .|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones para metadatos](metadata-enumerations.md)
