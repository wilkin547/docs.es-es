---
title: "IEnumRAWINPUTDEVIC:Next | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Método Next"
ms.assetid: 3698b44d-510e-4d18-b32b-85f17188ee26
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# IEnumRAWINPUTDEVIC:Next
Enumera las siguientes estructuras `celt` [RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) en la lista del enumerador y las devuelve en `rgelt` junto con el número real de elementos enumerados en `pceltFetched`.  
  
## Sintaxis  
  
```  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
#### Parámetros  
 `celt`  
  
 \[in\] Número de estructuras [RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) devueltas en `rgelt`.  
  
 `rgelt`  
  
 \[out\] Matriz de tamaño celt \(o superior\) para recibir estructuras RAWINPUTDEVICE enumeradas.  
  
 `pceltFetched`  
  
 \[out\] Puntero al número de elementos proporcionados realmente en `rgelt`.  El llamador puede pasar `NULL` si `rgelt` es uno.  
  
## Valor de propiedad y valor devuelto  
 HRESULT: S\_OK si el número de elementos proporcionado es `celt`. En caso contrario, S\_FALSE.