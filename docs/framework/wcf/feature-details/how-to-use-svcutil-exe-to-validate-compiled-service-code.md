---
title: "C&#243;mo: Utilizar Svcutil.exe para validar el c&#243;digo del servicio compilado | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d0d820fb-41c2-45b8-8f22-0fa5aeebbbaa
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# C&#243;mo: Utilizar Svcutil.exe para validar el c&#243;digo del servicio compilado
Puede utilizar [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para detectar los errores en las implementaciones del servicio y configuraciones sin hospedar el servicio.  
  
### Validar un servicio  
  
1.  Compile su servicio en un archivo ejecutable y uno o más ensamblados dependientes.  
  
2.  Abra un símbolo del sistema de SDK.  
  
3.  En el símbolo del sistema, inicie la herramienta Svcutil.exe mediante el formato siguiente.  Para obtener más información sobre los distintos parámetros, vea la sección Validación del servicio en el tema [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
    ```  
    svcutil.exe /validate /serviceName:<serviceConfigName>  <assemblyPath>*  
    ```  
  
     Debe utilizar la opción `/serviceName` para indicar el nombre de configuración del servicio que quiere validar.  
  
     El argumento `assemblyPath` especifica la ruta de acceso al archivo ejecutable para el servicio y uno o más ensamblados que contienen los tipos de servicio que se validarán.  El ensamblado ejecutable debe tener un archivo de configuración asociado para proporcionar la configuración de servicio.  Puede utilizar los caracteres comodín de la línea de comandos estándar para proporcionar varios ensamblados.  
  
## Ejemplo  
 Lo siguiente controla el servicio myServiceName implementados en el archivo ejecutable myServiceHost.exe.  Se carga el archivo de configuración para el servicio \(myServiceHost.exe.config\) automáticamente.  
  
```  
svcutil /validate /serviceName:myServiceName myServiceHost.exe  
```  
  
## Vea también  
 [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)