---
title: Función QualifierSet_GetNames (referencia de API no administrada)
description: La función QualifierSet_GetNames recupera los nombres de calificadores de un objeto o una propiedad.
ms.date: 11/06/2017
api_name:
- QualifierSet_GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_GetNames
helpviewer_keywords:
- QualifierSet_GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7c96439cf50c18e336baa70cf463b9463203290
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461183"
---
# <a name="qualifiersetgetnames-function"></a>QualifierSet_GetNames (función)
Recupera los nombres de todos los calificadores o de ciertos calificadores que están disponibles en el objeto actual o la propiedad. 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT QualifierSet_GetNames (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags,
   [out] SAFEARRAY (BSTR)**  pstrNames
); 
```  

## <a name="parameters"></a>Parámetros

`vFunc`   
[in] Este parámetro no se utiliza.

`ptr`   
[in] Un puntero a un [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instancia.

`lFlags`   
[in] Uno de los siguientes indicadores o valores que especifica los nombres que desee incluir en la enumeración.

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|  | 0 | Devolver los nombres de todos los calificadores. |
| `WBEM_FLAG_LOCAL_ONLY` | 0 x 10 | Devolver solo los nombres de calificadores específicos que el objeto o la propiedad actual. <br/> Para una propiedad: devolver solo los calificadores específicos a la propiedad (incluidas las invalidaciones) y no los calificadores se propagan desde la definición de clase. <br/> Para una instancia: devolver solo los nombres de calificador de específicos de la instancia. <br/> Para una clase: devolver solo calificadores específicos a la beiong de la clase derivada.
|`WBEM_FLAG_PROPAGATED_ONLY` | 0 x 20 | Devuelve solo los nombres de calificadores propagan de otro objeto. <br/> Para una propiedad: devuelven solo los calificadores se propagan a esta propiedad en la definición de clase y no los de la propiedad en Sí. <br/> Para una instancia: devolución propagan sólo los calificadores de la definición de clase. <br/> Para una clase: devolver sólo los nombres de calificador que se heredaron de las clases principales. |

`pstrNames` [out] Un nuevo `SAFEARRAY` que contiene los nombres solicitados. La matriz puede tener 0 elementos. Si se produce un error, un nuevo `SAFEARRAY` no se devuelve.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Un parámetro no es válido. |
|`WBEM_E_OUT_OF_MEMORY` | 0 x 80041006 | No hay suficiente memoria disponible para iniciar una nueva enumeración. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función tuvo éxito.  |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemQualifierSet::GetNames](https://msdn.microsoft.com/library/aa391868(v=vs.85).aspx) método.

Una vez que haya recuperado los nombres de calificador, se puede tener acceso a cada calificador por su nombre mediante una llamada a la [QualifierSet_Get](qualifierset-get.md) (función). 

No es un error de un determinado objeto de tener cero calificadores, por lo que el número de cadenas en `pstrNames` en el valor devuelto puede ser 0, incluso si la función devuelve `WBEM_S_NO_ERROR`.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también  
[WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
