---
title: 'Función ProcessUnhandledException: referencia de la API no administrada de WPF'
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ProcessUnhandledException
api_location:
- PresentationHost_v0400.dll
ms.assetid: 495ce5f6-bb4d-4b30-807a-c3c35f1ca95c
ms.openlocfilehash: 757e5ac3aa2dc4c87b210b026998523bd82045c1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743918"
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a>Función ProcessUnhandledException (referencia de la API no administrada de WPF)
Esta API es compatible con la infraestructura de Windows Presentation Foundation (WPF) y no está diseñada para utilizarse directamente desde el código.  
  
 Lo utiliza la infraestructura de Windows Presentation Foundation (WPF) para el control de excepciones.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
## <a name="parameters"></a>Parámetros  
 errorMsg  
 El mensaje de error.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [.NET Framework requisitos del sistema](../../get-started/system-requirements.md).  
  
 **DLL**  
  
 En el .NET Framework 3,0 y 3,5: PresentationHostDLL. dll  
  
 En el .NET Framework 4 y versiones posteriores: PresentationHost_v0400. dll  
  
 **Versión de .NET Framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Referencia de API no administrada de WPF](wpf-unmanaged-api-reference.md)
