---
title: "Servicio: errores en la validaci&#243;n de la seguridad y la autenticaci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 55c98268-b1ad-459d-851b-25ef52248187
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# Servicio: errores en la validaci&#243;n de la seguridad y la autenticaci&#243;n
Nombre del contador: errores en la autenticación y validación de la seguridad  
  
## Descripción  
 Este contador se incrementa siempre que se rechaza un mensaje debido a un problema de seguridad no cubierto en el contador "Llamadas de seguridad no autorizadas".Entre estos problemas se incluyen:  
  
-   No se puede leer el token de cliente en el mensaje.  
  
-   Error de autenticación en el token de cliente \(por ejemplo, contraseña incorrecta\).  
  
-   Error de comprobación de la firma \(por ejemplo, el mensaje ha sido alterado\).  
  
-   El mensaje es un duplicado de uno anterior, que puede producirse durante un ataque de reproducción.  
  
-   Error de descifrado.  
  
-   Faltan algunos elementos obligatorios \(por ejemplo, la marca de tiempo o el bloque de datos cifrados\) en el mensaje.  
  
-   Errores durante el protocolo de enlace TLSNEGO\/SPNEGO.