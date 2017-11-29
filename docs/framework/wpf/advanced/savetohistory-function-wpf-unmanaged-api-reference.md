---
title: "Función SaveToHistory (referencia de la API no administrada de WPF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: SaveToHistory
api_location: PresentationHost_v0400.dll
ms.assetid: 6dd101a3-44ad-4143-b228-772156f9b8ff
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b30884433f81aa5e4bf1241ae4fe34494bef788e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="savetohistory-function-wpf-unmanaged-api-reference"></a>Función SaveToHistory (referencia de la API no administrada de WPF)
Esta API es compatible con la infraestructura de Windows Presentation Foundation (WPF) y no está diseñada para utilizarse directamente desde el código.  
  
 Usa la infraestructura de Windows Presentation Foundation (WPF) para la administración de windows.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SaveToHistory(  
   __in_ecount(1) IStream* pHistoryStream  
)  
```  
  
#### <a name="parameters"></a>Parámetros  
 pHistoryStream  
 Un puntero a la secuencia de historial.  
  
## <a name="requirements"></a>Requisitos  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos de sistema de .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **DLL:**  
  
 En .NET Framework 3.0 y 3.5: PresentationHostDLL.dll  
  
 En .NET Framework 4 y versiones posteriores: PresentationHost_v0400.dll  
  
 **Versión de .NET framework:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de API no administrada de WPF](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
