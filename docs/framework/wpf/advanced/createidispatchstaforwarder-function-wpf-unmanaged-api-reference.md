---
title: CreateIDispatchSTAForwarder Function - Referencia de API no administrada de WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: e151ffa6eb5f1dc7479c699e0d7f9f3f57833ebd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174724"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a>Función CreateIDispatchSTAForwarder (Referencia de la API no administrada de WPF)
Esta API admite la infraestructura de Windows Presentation Foundation (WPF) y no está diseñada para usarse directamente desde el código.  
  
 Utilizado por la infraestructura de Windows Presentation Foundation (WPF) para la administración de subprocesos y ventanas.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a>Parámetros  
  
## <a name="property-valuereturn-value"></a>Valor de propiedad y valor devuelto  
 pDispatchDelegate  
 Un puntero `IDispatch` a una interfaz.  
  
 ppForwarder  
 Un puntero a la `IDispatch` dirección de una interfaz.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte Requisitos del sistema de [.NET Framework](../../get-started/system-requirements.md).  
  
 **Dll:**  
  
 En .NET Framework 3.0 y 3.5: PresentationHostDLL.dll  
  
 En .NET Framework 4 y versiones posteriores: PresentationHost_v0400.dll  
  
 **Versión de .NET Framework:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Referencia de API no administrada de WPF](wpf-unmanaged-api-reference.md)
