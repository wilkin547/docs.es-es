---
title: Función QualifierSet_GetNames (referencia de API no administrada)
description: La función QualifierSet_GetNames recupera los nombres de los calificadores de un objeto o propiedad.
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
ms.openlocfilehash: 84059c5e5542e13b1d4fc4efcfc4c7f418db391e
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44181555"
---
# <a name="qualifiersetgetnames-function"></a>Función QualifierSet_GetNames
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
[in] Este parámetro se usa.

`ptr`   
[in] Un puntero a un [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instancia.

`lFlags`   
[in] Uno de los siguientes indicadores o valores que especifica los nombres que se va a incluir en la enumeración.

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|  | 0 | Devuelve los nombres de todos los calificadores. |
| `WBEM_FLAG_LOCAL_ONLY` | 0 x 10 | Devolver solo los nombres de los calificadores específicos que el objeto o propiedad actual. <br/> Para una propiedad: devolver solo los calificadores específicos a la propiedad (incluidas las invalidaciones) y no los calificadores se propagan desde la definición de clase. <br/> Para una instancia: devolver solo los nombres de calificador específicos de la instancia. <br/> Para una clase: devolver solo los calificadores específica el beiong de la clase derivada.
|`WBEM_FLAG_PROPAGATED_ONLY` | 0 x 20 | Si la devolución propagan los nombres de los calificadores de otro objeto. <br/> Para una propiedad: devuelven solo los calificadores se propagan a esta propiedad desde la definición de clase y no los de la propiedad propiamente dicha. <br/> Para una instancia: devolución propagan solo esos calificadores de la definición de clase. <br/> Para una clase: sólo los nombres de calificador heredados de las clases principales de retorno. |

`pstrNames` [out] Un nuevo `SAFEARRAY` que contiene los nombres solicitados. La matriz puede tener 0 elementos. Si se produce un error, un nuevo `SAFEARRAY` no se devuelve.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Un parámetro no es válido. |
|`WBEM_E_OUT_OF_MEMORY` | 0 x 80041006 | No hay suficiente memoria disponible para comenzar una nueva enumeración. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función fue correcta.  |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemQualifierSet::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-getnames) método.

Una vez que haya recuperado los nombres de calificador, puede acceder a cada calificador por nombre mediante una llamada a la [QualifierSet_Get](qualifierset-get.md) función. 

No es un error para un objeto determinado tener calificadores de cero, por lo que el número de cadenas en `pstrNames` en el valor devuelto puede ser 0, aunque la función devuelve `WBEM_S_NO_ERROR`.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también  
[WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
