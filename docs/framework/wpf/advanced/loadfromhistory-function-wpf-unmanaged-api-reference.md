---
title: LoadFromHistory (función) (referencia de API no administrada de WPF)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- LoadFromHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
ms.openlocfilehash: 42be46d836a299139bded938237fe2a06e9794a5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646938"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a>LoadFromHistory (función) (referencia de API no administrada de WPF)
Esta API admite la infraestructura de Windows Presentation Foundation (WPF) y no está pensada para utilizarse directamente desde el código.  
  
 Usa la infraestructura de Windows Presentation Foundation (WPF) para la administración de windows.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,   
        IBindCtx* pBindCtx  
)  
```  
  
#### <a name="parameters"></a>Parámetros  
 pHistoryStream  
 Un puntero a una secuencia de información de historial.  
  
 pBindCtx  
 Un puntero a un contexto de enlace.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [requisitos del sistema de .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **ARCHIVO DLL:**  
  
 En .NET Framework 3.0 y 3.5: PresentationHostDLL.dll  
  
 En .NET Framework 4 y versiones posteriores: PresentationHost_v0400.dll  
  
 **Versión de .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Referencia de API no administrada de WPF](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
