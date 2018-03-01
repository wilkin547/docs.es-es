---
title: "Función QualifierSet_BeginEnumeration (referencia de API no administrada)"
description: "La función QualifierSet_BeginEnumeration restablece el enumerador de los calificadores de un objeto."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- QualifierSet_BeginEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_BeginEnumeration
helpviewer_keywords:
- QualifierSet_BeginEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 440dde03f4ed138a33eb6f817723d7c5c74f6d46
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="qualifiersetbeginenumeration-function"></a>QualifierSet_BeginEnumeration (función)
Restablece el enumerador de los calificadores de un objeto al principio de la enumeración.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT QualifierSet_BeginEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags
); 
```  

## <a name="parameters"></a>Parámetros

`vFunc`   
[in] Este parámetro no se utiliza.

`ptr`   
[in] Un puntero a un [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instancia.

`lFlags`   
[in] Una combinación bit a bit de los indicadores o valores que se describen en la [comentarios](#remarks) sección que especifica los calificadores que se incluirán en la enumeración.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | El `lFlags` parámetro no es válido. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Una segunda llamada a `QualifierSet_BeginEnumeration` se realizó sin una llamada intermedia a [ `QualifierSet_EndEnumeration` ](qualifierset-endenumeration.md). |
|`WBEM_E_OUT_OF_MEMORY` | 0 x 80041006 | No hay suficiente memoria disponible para iniciar una nueva enumeración. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función tuvo éxito.  |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemQualifierSet::BeginEnumeration](https://msdn.microsoft.com/library/aa391861(v=vs.85).aspx) método.

Para enumerar todos los calificadores en un objeto, debe llamar a este método antes de la primera llamada a [QualifierSet_Next](qualifierset-next.md). Se garantiza el orden en el que se enumeran los calificadores que puede variar con respecto de una enumeración especificada.

Las marcas que se pueden pasar como el `lEnumFlags` argumento se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código.   

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|  | 0 | Devolver los nombres de todos los calificadores. |
| `WBEM_FLAG_LOCAL_ONLY` | 0 x 10 | Devolver solo los nombres de calificadores específicos que el objeto o la propiedad actual. <br/> Para una propiedad: devolver solo los calificadores específicos a la propiedad (incluidas las invalidaciones) y no los calificadores se propagan desde la definición de clase. <br/> Para una instancia: devolver solo los nombres de calificador de específicos de la instancia. <br/> Para una clase: devolver solo calificadores específicos a la beiong de la clase derivada.
|`WBEM_FLAG_PROPAGATED_ONLY` | 0 x 20 | Devuelve solo los nombres de calificadores propagan de otro objeto. <br/> Para una propiedad: devuelven solo los calificadores se propagan a esta propiedad en la definición de clase y no los de la propiedad en Sí. <br/> Para una instancia: devolución propagan sólo los calificadores de la definición de clase. <br/> Para una clase: devolver sólo los nombres de calificador que se heredaron de las clases principales. |

## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también  
[WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
