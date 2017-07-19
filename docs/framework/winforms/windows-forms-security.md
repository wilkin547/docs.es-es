---
title: "Windows Forms Security | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "designer access security"
  - "permissions, Windows Forms"
  - "Windows Forms, security"
  - "security [Windows Forms]"
  - "access control, Windows Forms"
  - "security policy, Windows Forms"
ms.assetid: 932d438a-5285-46d8-a958-8c93d0ad6cae
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Windows Forms Security
Windows Forms presenta un modelo de seguridad basado en código \(los niveles de seguridad se establecen para el código, independientemente del usuario que lo ejecute\).  Se trata de un modelo de seguridad aparte de los esquemas de seguridad que pudiera incorporar el sistema informático.  Éstos pueden incluir los del explorador \(como la seguridad basada en zonas disponible en Internet Explorer\) o los del sistema operativo \(como la seguridad basada en credenciales de Windows NT\).  
  
## En esta sección  
 [Security in Windows Forms Overview](../../../docs/framework/winforms/security-in-windows-forms-overview.md)  
 Explica brevemente el modelo de seguridad de .NET Framework y los pasos básicos necesarios para garantizar que los formularios Windows Forms de la aplicación sean seguros.  
  
 [More Secure File and Data Access in Windows Forms](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)  
 Explica cómo tener acceso a archivos y datos en un entorno parcialmente confiable.  
  
 [More Secure Printing in Windows Forms](../../../docs/framework/winforms/more-secure-printing-in-windows-forms.md)  
 Explica cómo tener acceso a características de impresión en un entorno parcialmente confiable.  
  
 [Additional Security Considerations in Windows Forms](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)  
 Explica cómo manipular ventanas, utilizar el Portapapeles y realizar llamadas a código no administrado en un entorno parcialmente confiable.  
  
## Secciones relacionadas  
 [NIB: Default Security Policy](http://msdn.microsoft.com/es-es/2c086873-0894-4f4d-8f7e-47427c1a3b55)  
 Enumera los permisos predeterminados que conceden los conjuntos de permisos Plena confianza, Intranet local e Internet.  
  
 [NIB: General Security Policy Administration](http://msdn.microsoft.com/es-es/5121fe35-f0e3-402c-94ab-4f35b0a87b4b)  
 Ofrece información sobre la administración de la directiva de seguridad de .NET Framework y la concesión de permisos.  
  
 [Dangerous Permissions and Policy Administration](../../../docs/framework/misc/dangerous-permissions-and-policy-administration.md)  
 Trata algunos de los permisos de .NET Framework que pueden poner en peligro la seguridad del sistema.  
  
 [Secure Coding Guidelines](../../../docs/standard/security/secure-coding-guidelines.md)  
 Contiene vínculos a temas que explican las prácticas recomendadas para escribir código seguro para .NET Framework.  
  
 [NIB: Requesting Permissions](http://msdn.microsoft.com/es-es/0447c49d-8cba-45e4-862c-ff0b59bebdc2)  
 Trata el uso de atributos para permitir que se sepan en tiempo de ejecución los permisos que debe ejecutar el código.  
  
 [Key Security Concepts](../../../docs/standard/security/key-security-concepts.md)  
 Contiene vínculos a temas que tratan los aspectos básicos de la seguridad del código.  
  
 [Code Access Security Basics](../../../docs/framework/misc/code-access-security-basics.md)  
 Trata los aspectos básicos del trabajo con la directiva de seguridad en tiempo de ejecución de .NET Framework.  
  
 [NIB: Determining When to Modify Security Policy](http://msdn.microsoft.com/es-es/af749b17-e461-409d-84b9-a3d44789db16)  
 Explica cómo determinar cuándo las aplicaciones deben discrepar con la directiva de seguridad predeterminada.  
  
 [NIB: Deploying Security Policy](http://msdn.microsoft.com/es-es/f936c1e5-033b-4bd9-a3bd-a39ba733a681)  
 Trata el mejor modo de implementar cambios en la directiva de seguridad.