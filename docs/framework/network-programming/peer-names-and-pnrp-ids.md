---
title: "Nombres de mismo nivel e identificadores PNRP | Microsoft Docs"
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
ms.assetid: afa538e8-948f-4a98-aa9f-305134004115
caps.latest.revision: 5
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 5
---
# Nombres de mismo nivel e identificadores PNRP
Peer Name representa un extremo para la comunicación, que puede ser un equipo, usuario, grupo, un servicio, o nada asociado a un par que pueda resolver una dirección IPv6.  Peer Name Resolution Protocol \(PNRP\) toma el Peer Name estadístico único para la creación de un id. de PNRP, que se utiliza para identificar los miembros en la nube.  
  
## Peer Names  
 Los nombres de par se puede registrar como no seguro o protegerse.  Los nombres no seguro simplemente son cadenas de texto situadas bajo suplantación, como cualquiera puede registrar un nombre no seguro duplicado.  Los nombres no seguro es mejor utilizaban en private o protected de otra manera redes.  Los nombres delimitados están protegidos con un certificado y una firma digital.  Sólo el editor original podrá probar la propiedad de un nombre delimitar.  
  
 La combinación de nube y de ámbito proporciona un entorno razonablemente seguro para los pares que participan en la actividad de PNRP.  Sin embargo, con un nombre del mismo nivel asegúrese de no garantiza la seguridad de la aplicación de la conexión de red.  La seguridad de la aplicación depende de la implementación.  
  
 Los nombres del mismo nivel delimitados se registran sólo por su propietario y protegidos con la criptografía de clave pública.  Un nombre del mismo nivel asegúrese de se considera que pertenece a la entidad del mismo nivel que tiene la clave privada correspondiente.  La propiedad se puede probar mediante la dirección del mismo nivel certificada \(CPA\), que se firma utilizando la clave privada.  Un usuario malintencionado no puede forjar la propiedad de un nombre del mismo nivel sin la clave privada correspondiente.  
  
## Id. de PNRP  
 ![Id. PNRP](../../../docs/framework/network-programming/media/fdc9e8a0-4a1c-488d-a019-bc3a1973220c.png "fdc9e8a0\-4a1c\-488d\-a019\-bc3a1973220c")  
  
 Los id. de PNRP constan de los siguientes:  
  
-   Los 128 bits de orden superior, conocidos como el id. de par\-a\- par \(P2P\), son un hash de un nombre del mismo nivel asignado al extremo.  El nombre del mismo nivel tiene el siguiente formato: *Authority.Classifier*.  Para los nombres delimitados, *la autoridad* es el hash del algoritmo hash seguro 1 \(SHA1\) de clave pública del nombre del mismo nivel en caracteres hexadecimales.  Para los nombres sin garantía, *la autoridad* es el carácter “0 ".  *el clasificador* es una cadena que identifica la aplicación.  Ningún clasificador del mismo nivel de nombre puede ser superior a 149 caracteres, incluido el terminador de `null` .  
  
-   Los 128 bits de orden inferior se utilizan para la ubicación del servicio, que es un número generado que identifica distintas instancias del mismo id. de PROYECTOS en la misma nube.  
  
 Esta combinación de id. de PROYECTOS y de la ubicación del servicio permite que los id. varias de PNRP están registrados de un solo equipo.  
  
## Vea también  
 <xref:System.Net.PeerToPeer.PeerName>   
 <xref:System.Net.PeerToPeer>