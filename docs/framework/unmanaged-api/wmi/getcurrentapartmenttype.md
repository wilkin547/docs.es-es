---
title: Función GetCurrentApartmentType (referencia de la API no administrada)
description: La función GetCurrentApartmentType recupera el tipo de apartamento en el que se está ejecutando el autor de la llamada.
ms.date: 11/06/2017
api_name:
- GetCurrentApartmentType
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetCurrentApartmentType
helpviewer_keywords:
- GetCurrentApartmentType function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 6ecd2b49d6850a8fae25ddca54f855fdda2ccabb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120353"
---
# <a name="getcurrentapartmenttype-function"></a>GetCurrentApartmentType función)
Recupera el tipo de contenedor en el que se está ejecutando el llamador.   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc, 
   [in] IComThreadingInfo*    ptr, 
   [out] APTTYPE*             aptType
); 
```  

## <a name="parameters"></a>Parámetros

`vFunc`  
de Este parámetro no se utiliza.

`ptr`  
de Puntero a una instancia de [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) .

`aptType`  
enuncia Un puntero a un valor de enumeración [APTTYPE](/windows/win32/api/objidlbase/ne-objidlbase-apttype) que indica el apartamento del llamador.

## <a name="return-value"></a>Valor devuelto

|Constante  |Valor  |Descripción  |
|---------|---------|---------|
| `S_OK` | 0 | La función se completó correctamente. |
| `E_FAIL` | 0x80000008 | El autor de la llamada no se está ejecutando en un contenedor. |
  
## <a name="remarks"></a>Comentarios

Esta función contiene una llamada al método [IComThreadingInfo:: GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) .

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils. idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de la API no administrada)](index.md)
