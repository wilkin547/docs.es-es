---
title: COR_PRF_ASSEMBLY_REFERENCE_INFO (Estructura)
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: c8c1d916-8d1a-4f82-8128-9fd3732383fc
ms.openlocfilehash: 861b31e5621e9a7b40403d249c6a5c8c4ac25db8
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501045"
---
# <a name="cor_prf_assembly_reference_info-structure"></a>COR_PRF_ASSEMBLY_REFERENCE_INFO (Estructura)
[Compatible con .NET Framework 4.5.2 y versiones posteriores]  
  
 Proporciona a Common Language Runtime información sobre una referencia de ensamblado que debe tener en cuenta a la hora de realizar un rastreo de cierre de referencias de ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef struct _COR_PRF_ASSEMBLY_REFERENCE_INFO {  
    void* pbPublicKeyOrToken;  
    ULONG cbPublicKeyOrToken;  
    LPCWSTR szName;  
    ASSEMBLYMETADATA* pMetaData;  
    void* pbHashValue;  
    ULONG cbHashValue;  
    DWORD dwAssemblyRefFlags;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`pbPublicKeyOrToken`|Puntero a la clave pública o token del ensamblado.|  
|`cbPublicKeyOrToken`|Número de bytes en la clave pública o token.|  
|`szName`|Nombre del ensamblado al que se hace referencia.|  
|`pMetaData`|Puntero a los metadatos del ensamblado.|  
|`pbHashValue`|Puntero a un objeto binario grande (BLOB) de hash.|  
|`cbHashValue`|Número de bytes en el BLOB de hash.|  
|`dwAssemblyRefFlags`|Marcas del ensamblado.|  
  
## <a name="remarks"></a>Comentarios  
 El generador de perfiles rellena la estructura `COR_PRF_EX_CLAUSE_INFO` cuando declara referencias de ensamblado adicionales que Common Language Runtime debe tener en cuenta al realizar un rastreo de cierre de referencias de ensamblado.  
  
 Si el generador de perfiles se registra para el método de devolución de llamada [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) , el tiempo de ejecución pasa la ruta de acceso y el nombre del ensamblado que se va a cargar, junto con un puntero a un objeto de interfaz [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) a ese método. Después, el generador de perfiles puede llamar al método [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) con un `COR_PRF_ASSEMBLY_REFERENCE_INFO` objeto para cada ensamblado de destino al que tiene previsto hacer referencia desde el ensamblado especificado en la devolución de llamada [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [Estructuras para generación de perfiles](profiling-structures.md)
- [GetAssemblyReferences (método)](icorprofilercallback6-getassemblyreferences-method.md)
- [Método AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)
