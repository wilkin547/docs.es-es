---
title: "Error de automatizaci&#243;n | Microsoft Docs"
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
  - "vbrID440"
dev_langs: 
  - "VB"
ms.assetid: 2c4be5c5-2f0d-4a2b-96fe-d1b24f08fc4c
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Error de automatizaci&#243;n
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Se ha producido un error al ejecutar un método u obtener o establecer una propiedad de una variable de objeto.  El error se notificó a través de la aplicación que creó el objeto.  
  
### Para corregir este error  
  
1.  Compruebe las propiedades del objeto `Err` para conocer el origen y naturaleza del error.  
  
2.  Use la instrucción `On Error Resume Next` justo antes de la instrucción de acceso y busque los errores justo después de la instrucción de acceso.  
  
## Vea también  
 [Tipos de error](../../../visual-basic/programming-guide/language-features/error-types.md)   
 [Hable con nosotros](/visual-studio/ide/talk-to-us)