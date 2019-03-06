---
title: ProcessUnhandledException (función) (referencia de API no administrada de WPF)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ProcessUnhandledException
api_location:
- PresentationHost_v0400.dll
ms.assetid: 495ce5f6-bb4d-4b30-807a-c3c35f1ca95c
ms.openlocfilehash: c3997415c19483a69e66d8fe68c6ec9241f7ad0d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356247"
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a>ProcessUnhandledException (función) (referencia de API no administrada de WPF)
Esta API admite la infraestructura de Windows Presentation Foundation (WPF) y no está pensada para utilizarse directamente desde el código.  
  
 Usa la infraestructura de Windows Presentation Foundation (WPF) para el control de excepciones.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
#### <a name="parameters"></a>Parámetros  
 errorMsg  
 Mensaje de error.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [requisitos del sistema de .NET Framework](../../get-started/system-requirements.md).  
  
 **ARCHIVO DLL:**  
  
 En .NET Framework 3.0 y 3.5: PresentationHostDLL.dll  
  
 En .NET Framework 4 y versiones posteriores: PresentationHost_v0400.dll  
  
 **Versión de .NET framework:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Referencia de API no administrada de WPF](wpf-unmanaged-api-reference.md)
