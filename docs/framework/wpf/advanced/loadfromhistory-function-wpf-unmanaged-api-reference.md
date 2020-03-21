---
title: LoadFromHistory Function - Referencia de API no administrada de WPF
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- LoadFromHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
ms.openlocfilehash: be9b8658614e678b4370044a753554859d230fed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141580"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a>Función LoadFromHistory (Referencia de la API no administrada de WPF)
Esta API admite la infraestructura de Windows Presentation Foundation (WPF) y no está diseñada para usarse directamente desde el código.  
  
 Utilizado por la infraestructura de Windows Presentation Foundation (WPF) para la administración de Windows.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,
        IBindCtx* pBindCtx  
)  
```  
  
## <a name="parameters"></a>Parámetros  
 pHistoryStream  
 Un puntero a una secuencia de información del historial.  
  
 pBindCtx  
 Puntero a un contexto de enlace.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte Requisitos del sistema de [.NET Framework](../../get-started/system-requirements.md).  
  
 **Dll:**  
  
 En .NET Framework 3.0 y 3.5: PresentationHostDLL.dll  
  
 En .NET Framework 4 y versiones posteriores: PresentationHost_v0400.dll  
  
 **Versión de .NET Framework:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Referencia de API no administrada de WPF](wpf-unmanaged-api-reference.md)
