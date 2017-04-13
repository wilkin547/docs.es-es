---
title: "Capacidad de programaci&#243;n del almac&#233;n de metadatos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5b613661-f3f9-4e07-8e88-28c9ea2fd8f8
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Capacidad de programaci&#243;n del almac&#233;n de metadatos
El almacén de metadatos es una característica de [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] que permite la asociación de metadatos arbitrarios, en forma de atributos de CLR, con tipos en tiempo de ejecución.Esto permite un acoplamiento separado entre los componentes de tiempo de ejecución y sus homólogos en tiempo de diseño, así como la capacidad de cambiar los componentes en tiempo de diseño sin afectar al tiempo de ejecución.En este ejemplo se muestra cómo realizar una programación en el almacén de metadatos aplicando atributos a un tipo en tiempo de ejecución, sobre cuyo origen no tenemos control alguno.La terminología normalmente utilizada es que una aplicación de hospedaje registra los metadatos para un conjunto de tipos.  
  
 Dentro del resultado, puede observar un atributo adicional inesperado, <xref:System.Runtime.InteropServices.GUIDAttribute>.Este atributo se agrega al utilizar la API de metadatos y no tiene ningún impacto en la ejecución del ejemplo.  
  
 En este ejemplo se explica cómo:  
  
## Demostraciones  
  
-   Inyección de atributos utilizando la API del almacén de metadatos.  
  
-   Uso de un mecanismo de devolución de llamada para diferir el registro de metadatos.  
  
#### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución ProgrammingMetadataStore.sln.  
  
2.  Para compilar la solución, presione Ctrl\+MAYÚS\+B.  
  
3.  Presione F5 para ejecutar la solución.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\MetadataStore`  
  
## Vea también