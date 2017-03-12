---
title: "Valor de suma de comprobaci&#243;n incorrecto; no tiene d&#237;gitos hexadecimales o el n&#250;mero de d&#237;gitos hexadecimales es impar | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc42033"
  - "vbc42033"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42033"
ms.assetid: 4575554d-3615-46e4-9c6a-18e9c338e4ed
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Valor de suma de comprobaci&#243;n incorrecto; no tiene d&#237;gitos hexadecimales o el n&#250;mero de d&#237;gitos hexadecimales es impar
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Un valor de suma de comprobación contiene dígitos hexadecimales no válidos o un número impar de dígitos.  
  
 Cuando ASP.NET genera un archivo de origen de Visual Basic \(extensión .vb\), calcula una suma de comprobación y la coloca en un archivo se origen oculto que se identifica por medio de `#externalchecksum`.  Un usuario también puede generar un archivo .vb con el mismo fin, aunque lo más conveniente es dejar este proceso para uso interno.  
  
 De forma predeterminada, este mensaje es una advertencia.  Para más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configurar advertencias en Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Identificador del error:** BC42033  
  
### Para corregir este error  
  
1.  Si ASP.NET genera el archivo de origen de Visual Basic, reinicie la compilación del proyecto.  
  
2.  Si esta advertencia persiste tras el reinicio, reinstale ASP.NET e intente compilar de nuevo.  
  
3.  Si la advertencia persiste o no usa ASP.NET, reúna información sobre las circunstancias y notifíquelo a los Servicios de soporte técnico de Microsoft.  
  
## Vea también  
 [ASP.NET Overview](../Topic/ASP.NET%20Overview.md)   
 [Hable con nosotros](/visual-studio/ide/talk-to-us)