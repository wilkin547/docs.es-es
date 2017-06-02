---
title: "Aislamiento de red para aplicaciones de la Tienda Windows | Microsoft Docs"
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
ms.assetid: b064497c-d956-46b8-838d-7a0223c7e200
caps.latest.revision: 7
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# Aislamiento de red para aplicaciones de la Tienda Windows
Las clases de <xref:System.Net>, <xref:System.Net.Http>, y los espacios de nombres de <xref:System.Net.Http.Headers> se pueden utilizar para desarrollar aplicaciones de almacén de Windows o aplicaciones de escritorio.  Cuando se utiliza en Windows almacene la aplicación, clases de estos espacios de nombres afectados por el aislamiento de red, parte del modelo de seguridad de la aplicación utilizado por [!INCLUDE[win8](../../../includes/win8-md.md)].  Las funciones adecuadas de red deben estar habilitadas en el manifiesto de aplicación para una implementación del almacén de Windows para que el sistema permite acceso de red.  
  
## Lista de comprobación de aislamiento De red  
 Utilice esta lista de comprobación para asegurarse de que el aislamiento de red está configurado para la aplicación del almacén de Windows.  
  
1.  Determine la dirección de las solicitudes de acceso de red necesarias por la aplicación.  Puede ser o solicitudes cliente\- iniciadas de salida o las solicitudes no solicitadas de entrada o podrían ser una combinación de ambos tipos de solicitud de la red.  
  
2.  Determinar el tipo de recursos de red que esa aplicación comunicar.  Una aplicación puede necesitar comunicarse con los recursos de confianza en una red de inicio o trabajo.  Una aplicación puede necesitar comunicarse con recursos en internet.  Una aplicación puede tener acceso a ambos tipos de recursos de la red.  
  
3.  Configure las funciones mínimo\- necesarias de aislamiento de red en el manifiesto de la aplicación.  
  
4.  Implemente y ejecute la aplicación para probarla mediante las herramientas de aislamiento de red proporcionadas para solucionar problemas.  
  
 Para obtener información más detallada sobre cómo configurar las herramientas de funciones y de aislamiento de red utilizadas para solucionar el aislamiento de red, vea [Cómo configurar funciones de aislamiento de red](http://go.microsoft.com/fwlink/?LinkID=228265) en la documentación del desarrollador de [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] .  
  
## Vea también  
 [Conectarse a un servicio web](http://go.microsoft.com/fwlink/?LinkID=245696)   
 [Instrucciones y lista de comprobación de aislamiento de red](http://go.microsoft.com/fwlink/?LinkID=228265)   
 [QuickStart: Conexión mediante HttpClient](http://go.microsoft.com/fwlink/?LinkId=245697)   
 [Cómo utilizar controladores de HttpClient](http://go.microsoft.com/fwlink/?LinkId=245699)   
 [Cómo proteger las conexiones de HttpClient](http://go.microsoft.com/fwlink/?LinkId=245698)   
 [ejemplo de HttpClient](http://go.microsoft.com/fwlink/?LinkId=242550)