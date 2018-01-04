---
title: "CorMethodImpl (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorMethodImpl
api_location: mscoree.dll
api_type: COM
f1_keywords: CorMethodImpl
helpviewer_keywords: CorMethodImpl enumeration [.NET Framework metadata]
ms.assetid: ffbb3caf-20da-4a4b-8983-77376e72b990
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e82eb50e4850ffbb4d5fc67d9603a3128cf8bcf6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
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
|`miManagedMask`|Marcas que indican si el código es administrado o no administrado.|  
|`miUnmanaged`|Especifica que la implementación del método es no administrada.|  
|`miManaged`|Especifica que se administra la implementación del método.|  
|`miForwardRef`|Especifica que se define el método. Esta marca se utiliza principalmente en escenarios de combinación.|  
|`miPreserveSig`|Especifica que la firma del método no se puede trastocar para una conversión HRESULT.|  
|`miInternalCall`|Reservado para uso interno por common language runtime.|  
|`miSynchronized`|Especifica que el método tiene un único subproceso a través de su cuerpo.|  
|`miNoInlining`|Especifica que el método no se puede insertar.|  
|`miAggressiveInlining`|Especifica que el método debe ser entre línea si es posible.|  
|`miNoOptimization`|Especifica que el método no se debe optimizar.|  
|`miMaxMethodImplVal`|El valor válido máximo para un `CorMethodImpl`.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorHdr.h  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
