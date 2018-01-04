---
title: "Función CreateIDispatchSTAForwarder (referencia de la API no administrada de WPF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: CreateIDispatchSTAForwarder
api_location: PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5139784fdc067c09d032c0bf37114e0eb1caac33
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a>Función CreateIDispatchSTAForwarder (referencia de la API no administrada de WPF)
Esta API es compatible con la infraestructura de Windows Presentation Foundation (WPF) y no está diseñada para utilizarse directamente desde el código.  
  
 Usa la infraestructura de Windows Presentation Foundation (WPF) para la administración de subprocesos y de windows.  
  
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
 **Plataformas:** vea [requisitos de sistema de .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **DLL:**  
  
 En .NET Framework 3.0 y 3.5: PresentationHostDLL.dll  
  
 En .NET Framework 4 y versiones posteriores: PresentationHost_v0400.dll  
  
 **Versión de .NET framework:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de API no administrada de WPF](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
