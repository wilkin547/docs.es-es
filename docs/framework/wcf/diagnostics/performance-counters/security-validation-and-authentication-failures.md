---
title: "Errores de autenticaci&#243;n y validaci&#243;n de la seguridad | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0d4e3666-dfc6-421c-baf8-9479c22f7050
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# Errores de autenticaci&#243;n y validaci&#243;n de la seguridad
Nombre del contador: errores en la autenticación y validación de la seguridad  
  
## Descripción  
 Este contador se incrementa siempre que se rechaza un mensaje debido a un problema de seguridad no cubierto en el contador "Llamadas de seguridad no autorizadas".Entre estos problemas se incluyen:  
  
-   No pudo leerse el token del cliente en el mensaje.  
  
-   El token del cliente ha producido un error en la autenticación \(por ejemplo, contraseña incorrecta\).  
  
-   Error en la comprobación de la firma \(por ejemplo, el mensaje ha sido alterado\).  
  
-   El mensaje es un duplicado de uno anterior, que pudo producirse durante un ataque de reproducción.  
  
-   Error de descifrado.  
  
-   Faltan algunos elementos necesarios \(por ejemplo, la marca de tiempo o el bloque de datos cifrados\) en el mensaje.  
  
-   Errores durante el protocolo de enlace TLSNEGO\/SPNEGO.