---
title: "Ejemplo de tabla UriTemplate | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5dd1d38f-1989-4c64-820d-821f5a02216a
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Ejemplo de tabla UriTemplate
La clase <xref:System.UriTemplateTable> proporciona una estructura de tabla asociativa similar a un diccionario para trabajar con un conjunto de instancias de `UriTemplate`.Se puede hacer coincidir los identificadores uniformes de recursos \(URI\) concretos de manera eficaz con todas las plantillas de la tabla y se pueden recuperar los datos asociados con la plantilla con la que coincide.  
  
 Este ejemplo muestra los conceptos clave siguientes relacionados con la clase `UriTemplateTable`:  
  
-   Sintaxis para crear instancias de un `UriTemplateTable`.  
  
-   Rellenar un `UriTemplateTable` con un conjunto de pares clave\/valor.  
  
-   Hacer coincidir un URI de candidato con la tabla usando <xref:System.UriTemplateTable.MatchSingle%2A>.  
  
### Para configurar, compilar y ejecutar el ejemplo  
  
1.  Para compilar el código de la edición .NET de C\# o Visual Basic de la solución, siga las instrucciones de [Compilación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2.  Para ejecutar el ejemplo en una configuración con un único equipo o con varios, siga las instrucciones de [Ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplateTable`  
  
## Vea también  
 [Distribuidor de tabla de UriTemplate](../../../../docs/framework/wcf/samples/uritemplate-table-dispatcher-sample.md)   
 [UriTemplate](../../../../docs/framework/wcf/samples/uritemplate-sample.md)