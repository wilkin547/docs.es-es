---
title: "Implementaci&#243;n de aplicaciones WCF con ClickOnce | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1a11feee-2a47-4d3e-a28a-ad69d5ff93e0
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Implementaci&#243;n de aplicaciones WCF con ClickOnce
Las aplicaciones cliente que usen [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] se pueden implementar utilizando la tecnología de ClickOnce.Esta tecnología les permite sacar partido de las protecciones de seguridad en tiempo de ejecución proporcionadas por seguridad de acceso del código \(CAS\), siempre que estén firmadas digitalmente con un certificado de confianza.El certificado utilizado para firmar la aplicación ClickOnce debe residir en el almacén del Editor de confianza y la directiva de seguridad local en el equipo cliente se debe configurar para conceder los permisos de plena confianza a las aplicaciones firmadas con el certificado del editor.  
  
 Para obtener información sobre cómo configurar las aplicaciones ClickOnce y los editores de confianza, vea [Configuring ClickOnce Trusted Publishers](http://go.microsoft.com/fwlink/?LinkId=94774).  
  
## Vea también  
 [Trusted Application Deployment Overview](http://go.microsoft.com/fwlink/?LinkId=94775)   
 [ClickOnce Deployment for Windows Forms Applications](http://go.microsoft.com/fwlink/?LinkId=94776)