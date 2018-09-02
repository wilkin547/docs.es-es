---
title: Función QualifierSet_BeginEnumeration (referencia de API no administrada)
description: La función QualifierSet_BeginEnumeration restablece un enumerador de los calificadores de un objeto.
ms.date: 11/06/2017
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
ms.openlocfilehash: 2d20701237501834c611c4e498c39597cf275176
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43407039"
---
# <a name="qualifiersetbeginenumeration-function"></a>Función QualifierSet_BeginEnumeration
Restablece un enumerador de los calificadores de un objeto al principio de la enumeración.  

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
[in] Este parámetro se usa.

`ptr`   
[in] Un puntero a un [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instancia.

`lFlags`   
[in] Una combinación bit a bit de los marcadores o los valores descritos en la [comentarios](#remarks) sección que especifica los calificadores que se va a incluir en la enumeración.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | El `lFlags` parámetro no es válido. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Una segunda llamada a `QualifierSet_BeginEnumeration` se realizó sin una llamada intermedia a [ `QualifierSet_EndEnumeration` ](qualifierset-endenumeration.md). |
|`WBEM_E_OUT_OF_MEMORY` | 0 x 80041006 | No hay suficiente memoria disponible para comenzar una nueva enumeración. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función fue correcta.  |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemQualifierSet::BeginEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration) método.

Para enumerar todos los calificadores en un objeto, este método debe llamarse antes de la primera llamada a [QualifierSet_Next](qualifierset-next.md). El orden en el que se enumeran los calificadores se garantiza que todos los idiomas para una enumeración especificada.

Las marcas que se pueden pasar como el `lEnumFlags` argumento se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código.   

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|  | 0 | Devuelve los nombres de todos los calificadores. |
| `WBEM_FLAG_LOCAL_ONLY` | 0 x 10 | Devolver solo los nombres de los calificadores específicos que el objeto o propiedad actual. <br/> Para una propiedad: devolver solo los calificadores específicos a la propiedad (incluidas las invalidaciones) y no los calificadores se propagan desde la definición de clase. <br/> Para una instancia: devolver solo los nombres de calificador específicos de la instancia. <br/> Para una clase: devolver solo los calificadores específica el beiong de la clase derivada.
|`WBEM_FLAG_PROPAGATED_ONLY` | 0 x 20 | Si la devolución propagan los nombres de los calificadores de otro objeto. <br/> Para una propiedad: devuelven solo los calificadores se propagan a esta propiedad desde la definición de clase y no los de la propiedad propiamente dicha. <br/> Para una instancia: devolución propagan solo esos calificadores de la definición de clase. <br/> Para una clase: sólo los nombres de calificador heredados de las clases principales de retorno. |

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también  
[WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
