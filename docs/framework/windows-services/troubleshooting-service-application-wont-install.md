---
title: "Troubleshooting: Service Application Won&#39;t Install | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "troubleshooting service applications"
  - "services, troubleshooting"
  - "services, debugging"
  - "Windows NT services, troubleshooting"
  - "troubleshooting NT services"
  - "Windows Service applications, troubleshooting"
ms.assetid: 45c48e2e-b97d-44bc-8896-14f328e0ce33
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
caps.handback.revision: 8
---
# Troubleshooting: Service Application Won&#39;t Install
Si la aplicación de servicio no se instala correctamente, compruebe que la propiedad <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> de la clase del servicio está establecida en el mismo valor que se muestra en el instalador del servicio.  Para que el servicio se instale correctamente, el valor debe ser el mismo en ambas instancias.  
  
> [!NOTE]
>  Además, puede consultar los registros de instalación para obtener información acerca del proceso de instalación.  
  
 Asimismo, es recomendable comprobar si ya se encuentra instalado otro servicio con el mismo nombre.  Para que la instalación sea correcta, los nombres de los servicios deben ser únicos.  
  
## Vea también  
 [Introduction to Windows Service Applications](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)