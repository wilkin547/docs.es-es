---
title: "Extremo: Errores en la autenticaci&#243;n y validaci&#243;n de la seguridad | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5bad60aa-6084-4c7b-aefd-9b581f04382e
caps.latest.revision: 6
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 6
---
# Extremo: Errores en la autenticaci&#243;n y validaci&#243;n de la seguridad
Nombre del contador: errores en la autenticación y validación de la seguridad  
  
## Descripción  
 Este contador se incrementa siempre que se rechaza un mensaje debido a un problema de seguridad no cubierto en el contador "Llamadas de seguridad no autorizadas".Entre estos problemas se incluyen:  
  
-   No se puede leer el token de cliente del mensaje.  
  
-   Error al autenticar el token del cliente \(contraseña errónea\).  
  
-   Error en la comprobación de la signatura \(por ejemplo, mensaje manipulado\).  
  
-   El mensaje es un duplicado de uno anterior, que puede producirse durante un ataque de reproducción.  
  
-   Error de descifrado.  
  
-   Faltan algunos elementos necesarios \(la marca de tiempo o el bloque de datos cifrados\) en el mensaje.  
  
-   Errores durante el protocolo de enlace TLSNEGO\/SPNEGO.