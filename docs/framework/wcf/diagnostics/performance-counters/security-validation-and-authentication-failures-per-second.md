---
title: "Errores de autenticaci&#243;n y validaci&#243;n de la seguridad por segundo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 266c3bd3-2ffc-4471-94b7-3675443be1ac
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# Errores de autenticaci&#243;n y validaci&#243;n de la seguridad por segundo
Nombre del contador: Errores de validación de seguridad y de autenticación por segundo  
  
## Descripción  
 Este contador se incrementa siempre que se rechaza un mensaje debido a un problema de seguridad que no abarca el contador "Llamadas de seguridad no autorizadas".Entre estos problemas se incluyen:  
  
-   No pudo leerse el token del cliente en el mensaje.  
  
-   El token del cliente ha producido un error en la autenticación \(por ejemplo, contraseña incorrecta\).  
  
-   Error en la comprobación de la firma \(por ejemplo, el mensaje ha sido alterado\).  
  
-   El mensaje es un duplicado de uno anterior, que pudo producirse durante un ataque de reproducción.  
  
-   Error de descifrado.  
  
-   Faltan algunos elementos necesarios \(por ejemplo, la marca de tiempo o el bloque de datos cifrados\) en el mensaje.  
  
-   Errores durante el protocolo de enlace TLSNEGO\/SPNEGO.  
  
 Éste es un tipo de contador de rendimiento [PERF\_COUNTER\_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), cuyo valor se calcula mediante la fórmula siguiente:  
  
 \(N1\-N0\)\/\(\(D1\-D0\)\/F\)