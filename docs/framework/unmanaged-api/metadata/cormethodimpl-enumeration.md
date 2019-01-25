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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8ef293daea1a768c26adf05d14107a42889226e0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491290"
---
# <a name="cormethodimpl-enumeration"></a>CorMethodImpl (Enumeración)
Contiene valores que describen las características de implementación de un método.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
|`miOPTIL`|Especifica que la implementación del método es OPTIL.|  
|`miRuntime`|Especifica que common language runtime proporciona la implementación del método.|  
|`miManagedMask`|Marcadores que indican si el código es managed o unmanaged.|  
|`miUnmanaged`|Especifica que la implementación del método es no administrada.|  
|`miManaged`|Especifica que se administra la implementación del método.|  
|`miForwardRef`|Especifica que el método está definido. Esta marca se utiliza principalmente en escenarios de combinación.|  
|`miPreserveSig`|Especifica que la firma del método no se puede trastocar para una conversión de HRESULT.|  
|`miInternalCall`|Reservado para uso interno por common language runtime.|  
|`miSynchronized`|Especifica que el método tiene un único subproceso a través de su cuerpo.|  
|`miNoInlining`|Especifica que el método no se puede insertar.|  
|`miAggressiveInlining`|Especifica que el método debe insertarse si es posible.|  
|`miNoOptimization`|Especifica que el método no se debe optimizar.|  
|`miMaxMethodImplVal`|El máximo valor válido para un `CorMethodImpl`.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorHdr.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
