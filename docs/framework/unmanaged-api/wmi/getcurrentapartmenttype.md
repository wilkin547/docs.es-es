---
title: Función GetCurrentApartmentType (Referencia de API no administrada)
description: La función GetCurrentApartmentType recupera el tipo de apartamento en el que se ejecuta el autor de la llamada.
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
ms.openlocfilehash: 3fc88f7997ee5a6c25359243e1ee97a041050eb7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176830"
---
# <a name="getcurrentapartmenttype-function"></a>Función GetCurrentApartmentType
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
[en] Este parámetro no se utiliza.

`ptr`  
[en] Un puntero a un [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) instancia.

`aptType`  
[fuera] Puntero a un valor de enumeración [APTTYPE](/windows/win32/api/objidlbase/ne-objidlbase-apttype) que indica el apartamento del autor de la llamada.

## <a name="return-value"></a>Valor devuelto

|Constante  |Value  |Descripción  |
|---------|---------|---------|
| `S_OK` | 0 | La función se ha completado correctamente. |
| `E_FAIL` | 0x80000008 | El autor de la llamada no se está ejecutando en un apartamento. |
  
## <a name="remarks"></a>Observaciones

Esta función ajusta una llamada a la [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) método.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** WMINet_Utils.idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Consulte también

- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
