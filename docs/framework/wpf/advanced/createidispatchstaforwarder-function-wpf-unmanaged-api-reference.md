---
title: 'Función CreateIDispatchSTAForwarder: referencia de la API no administrada de WPF'
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: 67f2542733fb9c6af197c99ede2bd097ce876b5d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738035"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a>Función CreateIDispatchSTAForwarder (referencia de la API no administrada de WPF)
Esta API es compatible con la infraestructura de Windows Presentation Foundation (WPF) y no está diseñada para utilizarse directamente desde el código.  
  
 Lo utiliza la infraestructura de Windows Presentation Foundation (WPF) para la administración de subprocesos y ventanas.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a>Parameters  
  
## <a name="property-valuereturn-value"></a>Valor de propiedad y valor devuelto  
 pDispatchDelegate  
 Puntero a una interfaz de `IDispatch`.  
  
 ppForwarder  
 Puntero a la dirección de una interfaz de `IDispatch`.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Consulte [.NET Framework requisitos del sistema](../../get-started/system-requirements.md).  
  
 **DLL**  
  
 En el .NET Framework 3,0 y 3,5: PresentationHostDLL. dll  
  
 En el .NET Framework 4 y versiones posteriores: PresentationHost_v0400. dll  
  
 **Versión de .NET Framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de API no administrada de WPF](wpf-unmanaged-api-reference.md)
