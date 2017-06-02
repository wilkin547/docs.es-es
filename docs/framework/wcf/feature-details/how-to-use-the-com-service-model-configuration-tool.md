---
title: "C&#243;mo: Utilizar la herramienta configuraci&#243;n de modelos de servicio COM+ | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "COM+ [WCF], utilizar la herramienta de configuración del modelo de servicio"
ms.assetid: 7e68cd8d-5fda-4641-b92f-290db874376e
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# C&#243;mo: Utilizar la herramienta configuraci&#243;n de modelos de servicio COM+
Cuando ha seleccionado un modo de hospedaje adecuado, utilice la herramienta de línea de comandos de configuración de modelos de servicio COM\+ \(ComSvcConfig.exe\) para configurar las interfaces de aplicaciones que se expondrán como servicios web.  
  
> [!NOTE]
>  Debe ser un administrador en el equipo para realizar cualquiera de las tareas siguientes.  
  
 Al usar ComSvcConfig.exe en un equipo con Windows 7 para configurar un servicio web con la finalidad de usar la última versión de modelo de servicio \(actualmente, la versión 4.5\), lleve a cabo los siguientes pasos:  
  
1.  Establezca la clave del Registro `[HKEY_LOCAL_COMPUTER\SOFTWARE\Microsoft\.NETFramework]\OnlyUseLatestCLR` a un valor DWORD de 0x00000001  
  
2.  Ejecute comsvcconfig.exe  
  
3.  Revierta la clave del Registro agregada en el paso 1 a su valor original, o elimínela si no existía.  
  
> [!IMPORTANT]
>  Es importante revertir esta clave del Registro.Se trata de una clave de compatibilidad.Si no se revierte este cambio, se pueden producir problemas con otras aplicaciones .NET activas en el equipo.  
  
> [!WARNING]
>  Al usar ComSvcConfig.exe \/install en un equipo con Windows 8, se muestra un cuadro de diálogo que indica "Una aplicación de su equipo requiere la siguiente característica de Windows: .NET Framework 3.5 \(incluye .NET 2.0 y .NET 3.0\)" si no se ha instalado .NET Framework 3.5.Se puede omitir este cuadro de diálogo.También puede establecer la clave del Registro OnlyUseLatestCLR a un valor DWORD de 0x00000001  
  
### Para agregar una interfaz al conjunto de interfaces que se expondrán como servicios web, utilizando el modo de hospedaje de COM\+  
  
-   Ejecute ComSvcConfig utilizando `/install` y las opciones `/hosting:complus`, como se muestra en el ejemplo siguiente.  
  
    ```  
    ComSvcConfig.exe /install /application:OnlineStore /contract:ItemOrders.Financial,IFinances /hosting:complus /verbose  
    ```  
  
     El comando agrega la interfaz `IFinances` del componente \(de la aplicación OnlineStore COM\+\) `ItemOrders.IFinancial` al conjunto de interfaces que se expondrán como servicios web.El servicio utiliza el modo de hospedaje de COM\+ y por consiguiente requiere la activación explícita de la aplicación.  
  
     Aunque el carácter comodín de asterisco \(\*\) se puede utilizar para el componente y la interfaz, evite utilizarlo porque podría desear exponer solo la funcionalidad seleccionada como un servicio web.Si se ejecuta con una versión futura de este componente, al utilizar el carácter comodín se pueden exponer involuntariamente interfaces que pueden no haber estado presentes cuando se determinó la sintaxis de configuración.  
  
     La opción \/verbose indica a la herramienta que muestre las advertencias además de cualquier error.  
  
     El contrato para el servicio expuesto contendrá todos los métodos de la interfaz `IFinances`.  
  
### Para agregar solo métodos específicos de una interfaz al conjunto de interfaces que se expondrán como servicios web, utilizando el modo del alojamiento de COM\+  
  
-   Ejecute ComSvcConfig utilizando `/install` y las opciones `/hosting:complus` con denominación explícita de los métodos necesarios, como se muestra en el ejemplo siguiente.  
  
    ```  
    ComSvcConfig.exe /install /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{Credit,Debit} /hosting:complus /verbose  
    ```  
  
     El comando agrega solo los métodos `Credit` y `Debit` de la interfaz `IFinances` como operaciones al contrato de servicios expuesto.Todos los otros métodos en la interfaz se omitirán del contrato y no podrán ser llamados por los clientes de servicios web.  
  
### Para agregar una interfaz al conjunto de interfaces que serán expuestas como servicios web, utilizando el modo de hospedaje web  
  
-   Ejecute ComSvcConfig utilizando la opción `/install` y la opción `/hosting:was`, como se muestra en el ejemplo siguiente.  
  
    ```  
    ComSvcConfig.exe /install /application:OnlineWarehouse /contract:ItemInventory.Warehouse,IStockLevels /hosting:was /webDirectory:root/OnlineWarehouse /mex /verbose  
    ```  
  
     El comando agrega la interfaz `IStockLevels` en el componente `ItemInventory.Warehouse` \(de la aplicación OnlineWarehouse COM\+\) al conjunto de interfaces que se expondrán como servicios web.El servicio está hospedado en Web en el directorio virtual de OnlineWarehouse de IIS en lugar de en COM\+ y así la aplicación se activa automáticamente como se requiere.  
  
     Para utilizar la configuración en proceso hospedada en Web, la aplicación COM\+ se debe configurar para ejecutarse como una aplicación de biblioteca en lugar de una aplicación de servidor utilizando la consola de administración de Servicios de componentes.Las aplicaciones configuradas como aplicaciones de servidor utilizan el modo hospedado por Web estándar e incurren un salto de proceso para procesar cada solicitud.  
  
     La opción `/mex` agrega un extremo de servicio adicional de Intercambio de metadatos \(MEX\) que utiliza el mismo transporte que el extremo de servicio de la aplicación para admitir clientes que desean recuperar una definición del contrato del servicio.  
  
### Para quitar un servicio Web para una interfaz especificada  
  
-   Ejecute ComSvcConfig utilizando la opción `/uninstall`, como se muestra en el ejemplo siguiente.  
  
    ```  
    ComSvcConfig.exe /uninstall /application:OnlineStore /contract:ItemOrders.Financial,IFinances /hosting:complus  
    ```  
  
     El comando quita la interfaz `IFinances` del componente \(de la aplicación OnlineStore COM\+\) `ItemOrders.Financial`.  
  
### Para hacer una lista de las interfaces actualmente expuestas  
  
-   Ejecute ComSvcConfig utilizando la opción `/list`, como se muestra en el ejemplo siguiente.  
  
    ```  
    ComSvcConfig.exe /list  
    ```  
  
     El comando hace una lista de las interfaces actualmente expuestas, junto con la dirección correspondiente y los detalles del enlace, y se pone a disposición del equipo local.  
  
### Para hacer una lista de interfaces específicas actualmente expuestas  
  
-   Ejecute ComSvcConfig utilizando la opción `/list`, como se muestra en el ejemplo siguiente.  
  
    ```  
    ComSvcConfig.exe /list /application:OnlineStore /hosting:complus  
    ```  
  
     El comando hace una lista de las interfaces hospedadas por COM\+ actualmente expuestas, junto con la dirección correspondiente y los detalles del enlace, para la aplicación OnlineStore COM\+ en el equipo local.  
  
### Para mostrar la ayuda en las opciones que se pueden utilizar con la utilidad  
  
-   Ejecutar ComSvcConfig utilizando la opción \/?, como se muestra en el ejemplo siguiente.  
  
    ```  
    ComSvcConfig.exe /?  
  
    ```  
  
## Vea también  
 [Integración en la información general de las aplicaciones COM\+](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications-overview.md)