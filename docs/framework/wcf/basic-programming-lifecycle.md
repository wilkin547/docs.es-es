---
title: "Ciclo de vida de programaci&#243;n b&#225;sica | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "creación del servicio [WCF]"
ms.assetid: 7cf21bfe-23bd-46aa-8033-609f851dbf76
caps.latest.revision: 36
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 36
---
# Ciclo de vida de programaci&#243;n b&#225;sica
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] permite a las aplicaciones comunicar si están en el mismo equipo, en Internet o en diferentes plataformas de aplicación.En este tema se describen las tareas necesarias para crear una aplicación de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].Para obtener una aplicación de ejemplo de trabajo, vea [Tutorial de introducción](../../../docs/framework/wcf/getting-started-tutorial.md).  
  
## Las tareas básicas  
 Las tareas básicas que se van a realizar son, en orden:  
  
1.  Definir el contrato de servicio.Un contrato de servicio especifica la firma de un servicio, los datos que intercambia y el resto de los datos necesarios contractualmente.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Diseño de contratos de servicios](../../../docs/framework/wcf/designing-service-contracts.md).  
  
2.  Implementar el contrato.Para implementar un contrato de servicio, cree una clase que implemente el contrato y especifique comportamientos personalizados que deba tener el tiempo de ejecución.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Implementación de contratos de servicio](../../../docs/framework/wcf/implementing-service-contracts.md).  
  
3.  Configurar el servicio especificando los extremos y el resto de la información de comportamiento.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Configuración de servicios](../../../docs/framework/wcf/configuring-services.md).  
  
4.  Hospedar el servicio.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Servicios de hospedaje](../../../docs/framework/wcf/hosting-services.md).  
  
5.  Compilar una aplicación cliente.[!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Creación de clientes](../../../docs/framework/wcf/building-clients.md).  
  
 Aunque los temas de esta sección sigan este orden, algunos escenarios no se inician al principio.Por ejemplo, si desea crear un cliente para un servicio existente, ha de comenzar en el paso 5.O si está creando un servicio que usarán otros, puede omitir el paso 5.  
  
 Cuando esté familiarizado con el desarrollo de contratos de servicio, también puede leer [Introducción a la extensibilidad](../../../docs/framework/wcf/introduction-to-extensibility.md).Si tiene problemas con su servicio, compruebe [Inicio rápido de solución de problemas de WCF](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md) para ver si otros tienen los mismos problemas o problemas similares.  
  
## Vea también  
 [Implementación de contratos de servicio](../../../docs/framework/wcf/implementing-service-contracts.md)