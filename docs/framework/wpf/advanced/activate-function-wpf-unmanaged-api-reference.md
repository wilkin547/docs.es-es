---
title: "Activar la función (referencia de la API no administrada de WPF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- cpp
api_name:
- Acrivate
api_location:
- PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d890f3bd69c721071695713e0750180d50ed1ddf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a>Activar la función (referencia de la API no administrada de WPF)
Esta API es compatible con la infraestructura de Windows Presentation Foundation (WPF) y no está diseñada para utilizarse directamente desde el código.  
  
 Usa la infraestructura de Windows Presentation Foundation (WPF) para la administración de windows.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
void Activate(  
    const ActivateParameters* pParameters,  
    __deref_out_ecount(1) LPUNKNOWN* ppInner,  
    );  
```  
  
#### <a name="parameters"></a>Parámetros  
 pParameters  
 Un puntero a los parámetros de activación de la ventana.  
  
 ppInner  
 Un puntero a la dirección de un búfer único elemento que contiene un puntero a un <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> objeto.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos de sistema de .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **DLL:**  
  
 En .NET Framework 3.0 y 3.5: PresentationHostDLL.dll  
  
 En .NET Framework 4 y versiones posteriores: PresentationHost_v0400.dll  
  
 **Versión de .NET framework:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de API no administrada de WPF](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
