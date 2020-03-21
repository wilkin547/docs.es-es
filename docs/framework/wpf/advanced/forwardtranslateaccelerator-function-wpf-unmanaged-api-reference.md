---
title: 'ForwardTranslateAccelerator (función): referencia de API no administrada de WPF'
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
ms.openlocfilehash: a0a01be3000dc53df7855cb74015ba1164206838
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186630"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a>Función ForwardTranslateAccelerator (Referencia de API no administrada)
Esta API admite la infraestructura de Windows Presentation Foundation (WPF) y no está diseñada para usarse directamente desde el código.  
  
 Utilizado por la infraestructura de Windows Presentation Foundation (WPF) para la administración de Windows.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,
   VARIANT_BOOL appUnhandled  
)  
```  
  
## <a name="parameters"></a>Parámetros  
 Pmsg  
 Un puntero a un mensaje.  
  
 appUnhandled  
 `true`cuando la aplicación ya tiene la oportunidad de controlar el mensaje de entrada, pero no lo ha manejado; de `false`lo contrario, .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte Requisitos del sistema de [.NET Framework](../../get-started/system-requirements.md).  
  
 **Dll:**  
  
 En .NET Framework 3.0 y 3.5: PresentationHostDLL.dll  
  
 En .NET Framework 4 y versiones posteriores: PresentationHost_v0400.dll  
  
 **Versión de .NET Framework:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Referencia de API no administrada de WPF](wpf-unmanaged-api-reference.md)
