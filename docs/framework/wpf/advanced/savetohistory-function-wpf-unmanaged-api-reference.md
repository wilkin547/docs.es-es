---
title: 'Función SaveToHistory: referencia de la API no administrada de WPF'
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- SaveToHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: 6dd101a3-44ad-4143-b228-772156f9b8ff
ms.openlocfilehash: 7337e5dc23a3dce5de8270902bce228c49bc6edb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731747"
---
# <a name="savetohistory-function-wpf-unmanaged-api-reference"></a>Función SaveToHistory (referencia de la API no administrada de WPF)
Esta API es compatible con la infraestructura de Windows Presentation Foundation (WPF) y no está diseñada para utilizarse directamente desde el código.  
  
 Lo usa la infraestructura de Windows Presentation Foundation (WPF) para la administración de Windows.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SaveToHistory(  
   __in_ecount(1) IStream* pHistoryStream  
)  
```  
  
## <a name="parameters"></a>Parameters  
 pHistoryStream  
 Puntero a la secuencia del historial.  
  
## <a name="requirements"></a>Requisitos de  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Consulte [.NET Framework requisitos del sistema](../../get-started/system-requirements.md).  
  
 **DLL**  
  
 En el .NET Framework 3,0 y 3,5: PresentationHostDLL. dll  
  
 En el .NET Framework 4 y versiones posteriores: PresentationHost_v0400. dll  
  
 **Versión de .NET Framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Referencia de API no administrada de WPF](wpf-unmanaged-api-reference.md)
