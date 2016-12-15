---
title: "Esta clase no admite automatizaci&#243;n o no admite la interfaz esperada | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrID430"
dev_langs: 
  - "VB"
ms.assetid: d985bb7e-e48e-443e-86f2-ddb86758757c
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Esta clase no admite automatizaci&#243;n o no admite la interfaz esperada
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La clase especificada en la llamada a la función `GetObject` o a la función `CreateObject` no ha expuesto una interfaz de programación, o bien el proyecto se ha cambiado de .dll a .exe \(o a la inversa\).  
  
### Para corregir este error  
  
1.  Consulte la documentación de la aplicación que creó el objeto para conocer las limitaciones en cuanto al uso de la automatización con esta clase de objeto.  
  
2.  Si cambió un proyecto de .dll a .exe o a la inversa, deberá eliminar manualmente el registro del antiguo .dll o .exe.  
  
## Vea también  
 [Tipos de error](../../../visual-basic/programming-guide/language-features/error-types.md)   
 [Hable con nosotros](/visual-studio/ide/talk-to-us)