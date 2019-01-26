---
title: Tipos de datos comunes (Referencia de la API no administrada)
ms.date: 03/30/2017
ms.assetid: e4ab2c4c-9433-4eba-9e9a-096de406cafb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 98b83abce36b6e8a66ec3580af109b66b7ae09d8
ms.sourcegitcommit: d9a0071d0fd490ae006c816f78a563b9946e269a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2019
ms.locfileid: "55065835"
---
# <a name="common-data-types-unmanaged-api-reference"></a>Tipos de datos comunes (Referencia de la API no administrada)
En este tema se enumeran los tipos de datos que usan las API no administradas de .NET Framework y que se definen mediante instrucciones `typedef` de C/C++. Normalmente, estos tipos de datos son alias de tipos de datos primitivos de C/C++. Normalmente, los valores de estos tipos de datos son opacos; es decir, son devueltos por una función o un método determinados para que se puedan pasar a otras funciones o métodos sin modificar.  
  
|Tipo de datos|Definición|Definido en|Descripción|  
|---------------|----------------|----------------|-----------------|  
|AppDomainID|`typedef UINT_PTR AppDomainID;`|corprof.h|Identificador de un dominio de aplicación.|  
|AssemblyID|`typedef UINT_PTR AssemblyID;`|corprof.h|Identificador de un ensamblado.|  
|ClassID|`typedef UINT_PTR ClassID;`|corprof.h|Identificador de una clase administrada.|  
|CLRDATA_ADDRESS|`typedef ULONG64 CLRDATA_ADDRESS;`|clrdata.h|Una dirección de memoria de 64 bits.|
|CLRDATA_ENUM|`typedef ULONG64 CLRDATA_ADDRESS;`|No disponible|Una dirección de memoria de 64 bits.|
|CONNID|`typedef DWORD CONNID;`|cordebug.h, mscoree.h|Identificador de conexión de un subproceso que se conecta a una instancia de Microsoft SQL Server.|  
|ContextID|`typedef UINT_PTR ContextID;`|corprof.h|Identificador del contexto asociado a un subproceso administrado determinado.|  
|COR_PRF_ELT_INFO|`typedef UINT_PTR COR_PRF_ELT_INFO;`|corprof.h|Controlador opaco que representa información sobre un marco de pila determinado.|  
|COR_PRF_FRAME_INFO|`typedef UINT_PTR COR_PRF_FRAME_INFO;`|corprof.h|Controlador opaco que apunta a un marco de pila. Es válido solo durante la devolución de llamada a la que se pasa.|  
|CORDB_ADDRESS|`typedef ULONG64 CORDB_ADDRESS;`|cordebug.h|Dirección en memoria.|  
|CORDB_CONTINUE_STATUS|`typedef DWORD CORDB_CONTINUE_STATUS;`|cordebug.h|Estado de la continuación.|  
|CORDB_REGISTER|`typedef ULONG64 CORDB_REGISTER;`|cordebug.h|Valor de un registro de CPU.|
|FunctionID|`typedef UINT_PTR FunctionID;`|corprof.h|Identificador de una función o un método.|  
|GCHandleID|`typedef UINT_PTR GCHandleID;`|corprof.h|Controlador de recolección de elementos no utilizados.|  
|mdMethodDef|`typedef mdToken mdMethodDef;`|cordebug.h|Un token de definición de método.|
|mdToken|`typedef UINT32 mdToken;`|corprof.h|Un token de metadatos (una fila en una tabla de metadatos).|  
|ModuleID|`typedef UINT_PTR ModuleID;`|corprof.h|Identificador de un módulo de ensamblado.|  
|ObjectID|`typedef UINT_PTR ObjectID;`|corprof.h|Identificador de un objeto.|  
|ProcessID|`typedef UINT_PTR ProcessID;`|corprof.h|Identificador de un proceso administrado.|  
|ReJITID|`typedef UINT_PTR ReJITID;`|corprof.h|Identificador de una función con compilación JIT .|  
|TASKID|`typedef UINT64 TASKID;`|cordebug.h, mscoree.h|El identificador de un [ICLRTask](../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instancia.|  
|ThreadID|`typedef UINT_PTR ThreadID;`|corprof.h|Identificador de un subproceso administrado.|  
  
## <a name="see-also"></a>Vea también
- [Referencia de API no administrada](../../../docs/framework/unmanaged-api/index.md)
