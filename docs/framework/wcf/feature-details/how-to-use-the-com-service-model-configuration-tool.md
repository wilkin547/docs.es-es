---
title: Procedimiento para usar la herramienta configuración de modelos de servicio COM+
ms.date: 03/30/2017
helpviewer_keywords:
- COM+ [WCF], using service model configuration tool
ms.assetid: 7e68cd8d-5fda-4641-b92f-290db874376e
ms.openlocfilehash: f9e761bafd84726b51a2010a932c68c67c37f899
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595289"
---
# <a name="how-to-use-the-com-service-model-configuration-tool"></a>Procedimiento para usar la herramienta configuración de modelos de servicio COM+
Cuando ha seleccionado un modo de hospedaje adecuado, utilice la herramienta de línea de comandos de configuración de modelos de servicio COM+ (ComSvcConfig.exe) para configurar las interfaces de aplicaciones que se expondrán como servicios web.  
  
> [!NOTE]
> Debe ser un administrador en el equipo para realizar cualquiera de las tareas siguientes.  
  
 Al usar ComSvcConfig.exe en un equipo con Windows 7 para configurar un servicio web con la finalidad de usar la última versión de modelo de servicio (actualmente, la versión 4.5), lleve a cabo los siguientes pasos:  
  
1. Establezca la clave del registro `[HKEY_LOCAL_COMPUTER\SOFTWARE\Microsoft\.NETFramework]\OnlyUseLatestCLR` en un valor DWORD de 0x00000001  
  
2. Ejecute comsvcconfig.exe  
  
3. Revierta la clave del Registro agregada en el paso 1 a su valor original, o elimínela si no existía.  
  
> [!IMPORTANT]
> Es importante revertir esta clave del Registro. Se trata de una clave de compatibilidad. Si no se revierte este cambio, se pueden producir problemas con otras aplicaciones .NET activas en el equipo.  
  
> [!WARNING]
> Al usar ComSvcConfig. exe/Install en un equipo con Windows 8, se muestra un cuadro de diálogo que indica "una aplicación de su equipo necesita la siguiente característica de Windows: .NET Framework 3,5 (incluye .NET 2,0 y .NET 3,0" si .NET Framework 3,5 no está instalado. Se puede omitir este cuadro de diálogo. También puede establecer la clave del Registro OnlyUseLatestCLR a un valor DWORD de 0x00000001  
  
## <a name="to-add-an-interface-to-the-set-of-interfaces-exposed-as-web-services-using-the-com-hosting-mode"></a>Para agregar una interfaz al conjunto de interfaces que se exponen como servicios Web, utilizando el modo de hospedaje de COM+  
  
- Ejecute ComSvcConfig utilizando `/install` y las opciones `/hosting:complus`, como se muestra en el ejemplo siguiente.  
  
    ```console  
    ComSvcConfig.exe /install /application:OnlineStore /contract:ItemOrders.Financial,IFinances /hosting:complus /verbose  
    ```  
  
     El comando agrega la interfaz `IFinances` del componente (de la aplicación OnlineStore COM+) `ItemOrders.IFinancial` al conjunto de interfaces que se expondrán como servicios web. El servicio utiliza el modo de hospedaje de COM+ y por consiguiente requiere la activación explícita de la aplicación.  
  
     Aunque el carácter comodín ( \* ) se puede usar para el componente y la interfaz, evite usarlo porque es posible que desee exponer solo la funcionalidad seleccionada como servicio Web. Si se ejecuta con una versión futura de este componente, al utilizar el carácter comodín se pueden exponer involuntariamente interfaces que pueden no haber estado presentes cuando se determinó la sintaxis de configuración.  
  
     La opción /verbose indica a la herramienta que muestre las advertencias además de cualquier error.  
  
     El contrato para el servicio expuesto contendrá todos los métodos de la interfaz `IFinances`.  
  
## <a name="to-add-only-specific-methods-from-an-interface-to-the-set-of-interfaces-exposed-as-web-services-using-the-com-hosting-mode"></a>Para agregar únicamente métodos específicos de una interfaz al conjunto de interfaces que se exponen como servicios Web, utilizando el modo de hospedaje de COM+  
  
- Ejecute ComSvcConfig utilizando `/install` y las opciones `/hosting:complus` con denominación explícita de los métodos necesarios, como se muestra en el ejemplo siguiente.  
  
    ```console  
    ComSvcConfig.exe /install /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{Credit,Debit} /hosting:complus /verbose  
    ```  
  
     El comando agrega solo los métodos `Credit` y `Debit` de la interfaz `IFinances` como operaciones al contrato de servicios expuesto. Todos los otros métodos en la interfaz se omitirán del contrato y no podrán ser llamados por los clientes de servicios web.  
  
## <a name="to-add-an-interface-to-the-set-of-interfaces-exposed-as-web-services-using-the-web-hosting-mode"></a>Para agregar una interfaz al conjunto de interfaces que se exponen como servicios Web, utilizando el modo de hospedaje Web  
  
- Ejecute ComSvcConfig utilizando la opción `/install` y la opción `/hosting:was`, como se muestra en el ejemplo siguiente.  
  
    ```console  
    ComSvcConfig.exe /install /application:OnlineWarehouse /contract:ItemInventory.Warehouse,IStockLevels /hosting:was /webDirectory:root/OnlineWarehouse /mex /verbose  
    ```  
  
     El comando agrega la interfaz `IStockLevels` en el componente `ItemInventory.Warehouse` (de la aplicación OnlineWarehouse COM+) al conjunto de interfaces que se expondrán como servicios web. El servicio está hospedado en Web en el directorio virtual de OnlineWarehouse de IIS en lugar de en COM+ y así la aplicación se activa automáticamente como se requiere.  
  
     Para utilizar la configuración en proceso hospedada en Web, la aplicación COM+ se debe configurar para ejecutarse como una aplicación de biblioteca en lugar de una aplicación de servidor utilizando la consola de administración de Servicios de componentes. Las aplicaciones configuradas como aplicaciones de servidor utilizan el modo hospedado por Web estándar e incurren un salto de proceso para procesar cada solicitud.  
  
     La opción `/mex` agrega un extremo de servicio adicional de Intercambio de metadatos (MEX) que utiliza el mismo transporte que el extremo de servicio de la aplicación para admitir clientes que desean recuperar una definición del contrato del servicio.  
  
## <a name="to-remove-a-web-service-for-a-specified-interface"></a>Para quitar un servicio Web para una interfaz especificada  
  
- Ejecute ComSvcConfig utilizando la opción `/uninstall`, como se muestra en el ejemplo siguiente.  
  
    ```console  
    ComSvcConfig.exe /uninstall /application:OnlineStore /contract:ItemOrders.Financial,IFinances /hosting:complus  
    ```  
  
     El comando quita la interfaz `IFinances` del componente (de la aplicación OnlineStore COM+) `ItemOrders.Financial`.  
  
## <a name="to-list-currently-exposed-interfaces"></a>Para hacer una lista de las interfaces actualmente expuestas  
  
- Ejecute ComSvcConfig utilizando la opción `/list`, como se muestra en el ejemplo siguiente.  
  
    ```console  
    ComSvcConfig.exe /list  
    ```  
  
     El comando hace una lista de las interfaces actualmente expuestas, junto con la dirección correspondiente y los detalles del enlace, y se pone a disposición del equipo local.  
  
## <a name="to-list-specific-currently-exposed-interfaces"></a>Para hacer una lista de interfaces específicas actualmente expuestas  
  
- Ejecute ComSvcConfig utilizando la opción `/list`, como se muestra en el ejemplo siguiente.  
  
    ```console  
    ComSvcConfig.exe /list /application:OnlineStore /hosting:complus  
    ```  
  
     El comando hace una lista de las interfaces hospedadas por COM+ actualmente expuestas, junto con la dirección correspondiente y los detalles del enlace, para la aplicación OnlineStore COM+ en el equipo local.  
  
## <a name="to-display-help-on-the-options-that-can-be-used-with-the-utility"></a>Para mostrar la ayuda en las opciones que se pueden utilizar con la utilidad  
  
- Ejecutar ComSvcConfig utilizando la opción /? , como se muestra en el ejemplo siguiente.  
  
    ```console  
    ComSvcConfig.exe /?  
    ```  
  
## <a name="see-also"></a>Vea también

- [Información general de la integración con aplicaciones COM+](integrating-with-com-plus-applications-overview.md)
