---
title: Tipos de datos comunes (Referencia de la API no administrada)
ms.date: 03/30/2017
ms.assetid: e4ab2c4c-9433-4eba-9e9a-096de406cafb
ms.openlocfilehash: 5c00ff6d0947b5d847a9622dce02bd310491818c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673987"
---
# <a name="common-data-types-unmanaged-api-reference"></a>Tipos de datos comunes (Referencia de la API no administrada)

En este tema se enumeran los tipos de datos que usan las API no administradas de .NET Framework y que se definen mediante instrucciones `typedef` de C/C++. Normalmente, estos tipos de datos son alias de tipos de datos primitivos de C/C++. Normalmente, los valores de estos tipos de datos son opacos; es decir, son devueltos por una función o un método determinados para que se puedan pasar a otras funciones o métodos sin modificar.  
  
|Tipo de datos|Definición|Definido en|Descripción|  
|---------------|----------------|----------------|-----------------|  
|AppDomainID|`typedef UINT_PTR AppDomainID;`|corprof.h|Identificador de un dominio de aplicación.|  
|AssemblyID|`typedef UINT_PTR AssemblyID;`|corprof.h|Identificador de un ensamblado.|  
|ClassID|`typedef UINT_PTR ClassID;`|corprof.h|Identificador de una clase administrada.|  
|CLRDATA_ADDRESS|`typedef ULONG64 CLRDATA_ADDRESS;`|Clrdata. h|Una dirección de memoria de 64 bits.|
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
|mdMethodDef|`typedef mdToken mdMethodDef;`|cordebug.h|Token de definición de método.|
|mdToken|`typedef UINT32 mdToken;`|corprof.h|Un token de metadatos (una fila en una tabla de metadatos).|  
|ModuleID|`typedef UINT_PTR ModuleID;`|corprof.h|Identificador de un módulo de ensamblado.|  
|ObjectID|`typedef UINT_PTR ObjectID;`|corprof.h|Identificador de un objeto.|  
|PCCOR_SIGNATURE|`typedef SIZE_T PCCOR_SIGNATURE;`|cordebug.h|Un puntero a un miembro o a una firma de metadatos.|
|ProcessID|`typedef UINT_PTR ProcessID;`|corprof.h|Identificador de un proceso administrado.|  
|ReJITID|`typedef UINT_PTR ReJITID;`|corprof.h|Identificador de una función con compilación JIT .|  
|SIZE_T|`typedef ULONG_PTR SIZE_T;`|corsym. h|Un puntero a una dirección de memoria de 64 bits.|
|TASKID|`typedef UINT64 TASKID;`|cordebug.h, mscoree.h|Identificador de una instancia de [ICLRTask](./hosting/iclrtask-interface.md) .|  
|ThreadID|`typedef UINT_PTR ThreadID;`|corprof.h|Identificador de un subproceso administrado.|  
  
## <a name="see-also"></a>Consulte también

- [Referencia de API no administrada](index.md)
