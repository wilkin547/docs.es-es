---
title: "Función GetPropertyHandle (referencia de API no administrada)"
description: "La función GetPropertyHandle devuelve un identificador único que una propiedad de identidades."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetPropertyHandle
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetPropertyHandle
helpviewer_keywords: GetPropertyHandle function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1ab3df6d2233059de76036da7ff27f5cc1808aaf
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="getpropertyhandle-function"></a>GetPropertyHandle (función)
Devuelve un identificador único que identifica una propiedad.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetPropertyHandle (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] LPCWSTR              wszPropertyName,
   [out] CIMTYPE*            pType,
   [out] long*               pHandle
); 
```  

## <a name="parameters"></a>Parámetros

`vFunc`  
[in] Este parámetro no se utiliza.

`ptr`  
[in] Un puntero a un [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) instancia.

`wszPropertyName`  
[in] Una cadena terminada en null de characaters codificados en UTF16 que contiene el nombre de propiedad.   

`pType`  
[out] Un puntero a un [ `CIMTYPE` ](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx) miembro de enumeración que representa el tipo CIM de la propiedad.

`pHandle`   
[out] Un puntero a un entero que contiene el identificador de propiedad.

## <a name="return-value"></a>Valor devuelto

Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | No se encontró el nombre de propiedad especificado. |
|`WBEM_E_INVALID_PARAMETER` | 0 x 80041008 | Un parámetro no es válido. |
|`WBEM_E_NOT_SUPPORTED` | 0x8004100C | La propiedad solicitada es de tipo son `CIM_OBJECT` o `CIM_ARRAY`. |
|`WBEM_S_NO_ERROR` | 0 | La llamada de función tuvo éxito.  |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada a la [IWbemClassObject::GetPropertyHandle](https://msdn.microsoft.com/library/aa391771(v=vs.85).aspx) método.

Puede utilizar este identificador para identificar las propiedades cuando se usa [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) métodos para leer o escribir valores de propiedad.

Pueden obtenerse identificadores para las propiedades de todos los tipos de datos distinto de `CIM_OBJECT` y `CIM_ARRAY`. Devuelve el trabajo de identificadores en todas las instancias de una clase.

## <a name="requirements"></a>Requisitos  
**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también  
[WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
