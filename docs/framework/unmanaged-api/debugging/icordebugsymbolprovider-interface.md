---
title: ICorDebugSymbolProvider (Interfaz)
ms.date: 03/30/2017
ms.assetid: 85b24196-b6c6-4bda-9de3-47180bd6ff96
ms.openlocfilehash: 6f7a8a2b12c047b956a3b6e85fe8365e0360b3f2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791529"
---
# <a name="icordebugsymbolprovider-interface"></a>ICorDebugSymbolProvider (Interfaz)
Proporciona métodos que pueden utilizarse para recuperar información de símbolos de depuración.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetAssemblyImageBytes (método)](icordebugsymbolprovider-getassemblyimagebytes-method.md)|Lee datos de un ensamblado combinado a partir de una dirección virtual relativa (RVA) del ensamblado combinado.|  
|[GetAssemblyImageMetadata (método)](icordebugsymbolprovider-getassemblyimagemetadata-method.md)|Devuelve los metadatos desde un ensamblado combinado.|  
|[GetCodeRange (método)](icordebugsymbolprovider-getcoderange-method.md)|Obtiene el tamaño y la dirección de inicio del método a partir de una dirección virtual relativa (RVA) en un método.|  
|[GetInstanceFieldSymbols (método)](icordebugsymbolprovider-getinstancefieldsymbols-method.md)|Obtiene los símbolos de campo de instancia que corresponden a una firma Typespec.|  
|[GetMergedAssemblyRecords (método)](icordebugsymbolprovider-getmergedassemblyrecords-method.md)|Obtiene los registros de símbolos para todos los ensamblados combinados.|  
|[GetMethodLocalSymbols (método)](icordebugsymbolprovider-getmethodlocalsymbols-method.md)|Obtiene los símbolos locales del método a partir de la dirección virtual relativa (RVA) de ese método.|  
|[GetMethodParameterSymbols (método)](icordebugsymbolprovider-getmethodparametersymbols-method.md)|Obtiene los símbolos de parámetro del método a partir de la dirección virtual relativa (RVA) de ese método.|  
|[GetMethodProps (método)](icordebugsymbolprovider-getmethodprops-method.md)|Devuelve información acerca de las propiedades del método, como el token de metadatos del método e información acerca de sus parámetros genéricos, a partir de una dirección virtual relativa (RVA) en ese método.|  
|[GetObjectSize (método)](icordebugsymbolprovider-getobjectsize-method.md)|Devuelve el tamaño del objeto para un objeto basado en su firma Typespec.|  
|[GetStaticFieldSymbols (método)](icordebugsymbolprovider-getstaticfieldsymbols-method.md)|Obtiene los símbolos de campo estáticos que corresponden a una firma Typespec.|  
|[GetTypeProps (método)](icordebugsymbolprovider-gettypeprops-method.md)|Devuelve información acerca de las propiedades de un tipo, como el número de firmas de sus parámetros genéricos, dada una dirección virtual relativa (RVA) en una tabla virtual.|  
  
## <a name="remarks"></a>Notas  
  
> [!NOTE]
> Esta interfaz solo está disponible con .NET Native. Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](debugging-interfaces.md)
- [Depuración](index.md)
