---
title: CreateIDispatchSTAForwarder (función) (referencia de API no administrada de WPF)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: c4da322bf779e084f12529d0da6949ef6ada5cf3
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57379658"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a>CreateIDispatchSTAForwarder (función) (referencia de API no administrada de WPF)
Esta API admite la infraestructura de Windows Presentation Foundation (WPF) y no está pensada para utilizarse directamente desde el código.  
  
 Usa la infraestructura de Windows Presentation Foundation (WPF) para la administración de subprocesos y windows.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
#### <a name="parameters"></a>Parámetros  
  
## <a name="property-valuereturn-value"></a>Valor de propiedad y valor devuelto  
 pDispatchDelegate  
 Un puntero a un `IDispatch` interfaz.  
  
 ppForwarder  
 Un puntero a la dirección de un `IDispatch` interfaz.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [requisitos del sistema de .NET Framework](../../get-started/system-requirements.md).  
  
 **ARCHIVO DLL:**  
  
 En .NET Framework 3.0 y 3.5: PresentationHostDLL.dll  
  
 En .NET Framework 4 y versiones posteriores: PresentationHost_v0400.dll  
  
 **Versión de .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Referencia de API no administrada de WPF](wpf-unmanaged-api-reference.md)
