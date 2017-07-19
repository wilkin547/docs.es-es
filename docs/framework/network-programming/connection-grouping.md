---
title: "Agrupaci&#243;n de conexiones | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Internet, conexiones"
  - "conexiones [.NET Framework], agrupar"
  - "clase WebRequest, agrupación de conexiones"
  - "recursos de red, conexiones"
  - "agrupación de conexiones"
ms.assetid: 2ec502e8-4ba0-4c22-9410-f28eaf4eee63
caps.latest.revision: 7
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# Agrupaci&#243;n de conexiones
La agrupación de conexión asociado solicitudes específicas en una sola aplicación a un grupo de conexiones definido.  Esto se puede requerir por una aplicación de nivel intermedio que se conecte a un servidor back\-end en nombre de un usuario y utiliza un protocolo de autenticación que admite a delegación, como Kerberos, o por una aplicación de nivel intermedio que proporcione sus propias credenciales, como en el ejemplo siguiente.  Por ejemplo, supongamos un usuario, Joe, llamadas un sitio web interno que envíe su información de nóminas.  Después de autenticar a Joe, el servidor de aplicaciones de nivel medio utiliza las credenciales de Joe para conectarse al servidor back\-end para recuperar la información de nóminas.  A continuación, Susan visita el sitio y solicite la información de nóminas.  Dado que la aplicación de nivel medio ha creado una conexión utilizando las credenciales de Joe, el servidor back\-end responde con información de Joe.  Sin embargo, si la aplicación asigna cada solicitud enviada al servidor back\-end a un grupo de conexión formado username, cada usuario pertenece a un grupo de conexiones independiente y no puede compartir accidentalmente la información de autenticación con otro usuario.  
  
 Para asignar una solicitud a un grupo concreto de la conexión, debe asignar un nombre a la propiedad de <xref:System.Net.WebRequest.ConnectionGroupName%2A> del <xref:System.Net.WebRequest> antes de crear la solicitud.  
  
## Vea también  
 [Administrar conexiones](../../../docs/framework/network-programming/managing-connections.md)   
 [Cómo: asignar la información de usuario para agrupar conexiones](../../../docs/framework/network-programming/how-to-assign-user-information-to-group-connections.md)