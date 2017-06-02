---
title: "Canal del mismo nivel | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e06a2efb-8e70-4299-8b0f-bfb37efb074b
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Canal del mismo nivel
En este tema se enumeran todas las excepciones que genera Peer Channel [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].  
  
## Lista de excepciones  
  
|Código de recurso|Cadena de recurso|  
|-----------------------|-----------------------|  
|InsufficientCredentials|Las credenciales especificadas no son suficientes para llevar a cabo la operación solicitada.  Especificar un valor válido para la operación especificada|  
|InvalidResolverMode|El valor PeerResolverMode especificado no es válido.  Especifique PeerResolveMode.Auto, predeterminado o PNRP.|  
|PeerNodeAborted|No se puede abrir PeerNode porque se ha finalizado.|  
|PeerNullRegistrationInfo|La información de registro no puede ser nula.  Asegúrese de que la operación de registro se invoca con un objeto RegistrationInfo válido.|  
|PeerNullResolveInfo|La información de resolución no puede ser `null`.  Asegúrese de que la operación de resolución se invoca con un objeto ResolveInfo válido.|