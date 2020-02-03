---
title: 'Función LoadFromHistory: referencia de la API no administrada de WPF'
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- LoadFromHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
ms.openlocfilehash: 7807e073d1f09ac6a6213aee6d86d53cc75a3c56
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76727933"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a>Función LoadFromHistory (referencia de la API no administrada de WPF)
Esta API es compatible con la infraestructura de Windows Presentation Foundation (WPF) y no está diseñada para utilizarse directamente desde el código.  
  
 Lo usa la infraestructura de Windows Presentation Foundation (WPF) para la administración de Windows.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,   
        IBindCtx* pBindCtx  
)  
```  
  
## <a name="parameters"></a>Parámetros  
 pHistoryStream  
 Un puntero a un flujo de información del historial.  
  
 pBindCtx  
 Un puntero a un contexto de enlace.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [.NET Framework requisitos del sistema](../../get-started/system-requirements.md).  
  
 **DLL**  
  
 En el .NET Framework 3,0 y 3,5: PresentationHostDLL. dll  
  
 En el .NET Framework 4 y versiones posteriores: PresentationHost_v0400. dll  
  
 **Versión de .NET Framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Referencia de API no administrada de WPF](wpf-unmanaged-api-reference.md)
