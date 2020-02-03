---
title: 'Función ForwardTranslateAccelerator: referencia de la API no administrada de WPF'
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
ms.openlocfilehash: f6e8208ffe2c186234f30f31e346ca6b1d0be4c0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747039"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a>Función ForwardTranslateAccelerator (referencia de la API no administrada de WPF)
Esta API es compatible con la infraestructura de Windows Presentation Foundation (WPF) y no está diseñada para utilizarse directamente desde el código.  
  
 Lo usa la infraestructura de Windows Presentation Foundation (WPF) para la administración de Windows.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,   
   VARIANT_BOOL appUnhandled  
)  
```  
  
## <a name="parameters"></a>Parámetros  
 pMsg  
 Un puntero a un mensaje.  
  
 appUnhandled  
 `true` cuando la aplicación ya tiene la oportunidad de controlar el mensaje de entrada, pero no la ha controlado; de lo contrario, `false`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [.NET Framework requisitos del sistema](../../get-started/system-requirements.md).  
  
 **DLL**  
  
 En el .NET Framework 3,0 y 3,5: PresentationHostDLL. dll  
  
 En el .NET Framework 4 y versiones posteriores: PresentationHost_v0400. dll  
  
 **Versión de .NET Framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Referencia de API no administrada de WPF](wpf-unmanaged-api-reference.md)
