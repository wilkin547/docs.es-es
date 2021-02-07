---
description: 'Más información acerca de cómo: usar la herramienta de configuración del modelo de servicio COM+'
title: Procedimiento para usar la herramienta configuración de modelos de servicio COM+
ms.date: 03/30/2017
helpviewer_keywords:
- COM+ [WCF], using service model configuration tool
ms.assetid: 7e68cd8d-5fda-4641-b92f-290db874376e
ms.openlocfilehash: 2047604f327cd871629bbdac403e9acd816bbdb1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99734092"
---
# <a name="how-to-use-the-com-service-model-configuration-tool"></a>Procedimiento para usar la herramienta configuración de modelos de servicio COM+

Cuando ha seleccionado un modo de hospedaje adecuado, utilice la herramienta de línea de comandos de configuración de modelos de servicio COM+ (ComSvcConfig.exe) para configurar las interfaces de aplicaciones que se expondrán como servicios web.

> [!NOTE]
> Debe ser un administrador en el equipo para realizar cualquiera de las tareas siguientes.

 Al usar ComSvcConfig.exe en un equipo con Windows 7 para configurar un servicio web con la finalidad de usar la última versión de modelo de servicio (actualmente, la versión 4.5), lleve a cabo los siguientes pasos:

1. Establezca la clave del registro  `[HKEY_LOCAL_COMPUTER\SOFTWARE\Microsoft\.NETFramework]\OnlyUseLatestCLR` en un valor DWORD de 0x00000001

2. Ejecute comsvcconfig.exe

3. Revierta la clave del Registro agregada en el paso 1 a su valor original, o elimínela si no existía.

> [!IMPORTANT]
> Es importante revertir esta clave del Registro. Se trata de una clave de compatibilidad. Si no se revierte este cambio, se pueden producir problemas con otras aplicaciones .NET activas en el equipo.

> [!WARNING]
> Cuando se usa ComSvcConfig.exe/install en un equipo con Windows 8, se muestra un cuadro de diálogo que indica "una aplicación de su equipo necesita la siguiente característica de Windows: .NET Framework 3,5 (incluye .NET 2,0 y .NET 3,0" si .NET Framework 3,5 no está instalado. Se puede omitir este cuadro de diálogo. También puede establecer la clave del Registro OnlyUseLatestCLR a un valor DWORD de 0x00000001

## <a name="add-an-interface-using-the-com-hosting-mode"></a>Agregar una interfaz mediante el modo de hospedaje de COM+

- Ejecute ComSvcConfig utilizando `/install` y las opciones `/hosting:complus`, como se muestra en el ejemplo siguiente.

    ```console
    ComSvcConfig.exe /install /application:OnlineStore /contract:ItemOrders.Financial,IFinances /hosting:complus /verbose
    ```

     El comando agrega la interfaz `IFinances` del componente (de la aplicación OnlineStore COM+) `ItemOrders.IFinancial` al conjunto de interfaces que se expondrán como servicios web. El servicio utiliza el modo de hospedaje de COM+ y por consiguiente requiere la activación explícita de la aplicación.

     Aunque el carácter comodín ( \* ) se puede usar para el componente y la interfaz, evite usarlo porque es posible que desee exponer solo la funcionalidad seleccionada como servicio Web. Si se ejecuta con una versión futura de este componente, al utilizar el carácter comodín se pueden exponer involuntariamente interfaces que pueden no haber estado presentes cuando se determinó la sintaxis de configuración.

     La opción /verbose indica a la herramienta que muestre las advertencias además de cualquier error.

     El contrato para el servicio expuesto contendrá todos los métodos de la interfaz `IFinances`.

## <a name="add-specific-methods-from-an-interface-using-the-com-hosting-mode"></a>Agregar métodos específicos desde una interfaz mediante el modo de hospedaje de COM+

- Ejecute ComSvcConfig utilizando `/install` y las opciones `/hosting:complus` con denominación explícita de los métodos necesarios, como se muestra en el ejemplo siguiente.

    ```console
    ComSvcConfig.exe /install /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{Credit,Debit} /hosting:complus /verbose
    ```

     El comando agrega solo los métodos `Credit` y `Debit` de la interfaz `IFinances` como operaciones al contrato de servicios expuesto. Todos los otros métodos en la interfaz se omitirán del contrato y no podrán ser llamados por los clientes de servicios web.

## <a name="add-an-interface-using-the-web-hosting-mode"></a>Agregar una interfaz mediante el modo de hospedaje Web

- Ejecute ComSvcConfig utilizando la opción `/install` y la opción `/hosting:was`, como se muestra en el ejemplo siguiente.

    ```console
    ComSvcConfig.exe /install /application:OnlineWarehouse /contract:ItemInventory.Warehouse,IStockLevels /hosting:was /webDirectory:root/OnlineWarehouse /mex /verbose
    ```

     El comando agrega la interfaz `IStockLevels` en el componente `ItemInventory.Warehouse` (de la aplicación OnlineWarehouse COM+) al conjunto de interfaces que se expondrán como servicios web. El servicio está hospedado en Web en el directorio virtual de OnlineWarehouse de IIS en lugar de en COM+ y así la aplicación se activa automáticamente como se requiere.

     Para utilizar la configuración en proceso hospedada en Web, la aplicación COM+ se debe configurar para ejecutarse como una aplicación de biblioteca en lugar de una aplicación de servidor utilizando la consola de administración de Servicios de componentes. Las aplicaciones configuradas como aplicaciones de servidor utilizan el modo hospedado por Web estándar e incurren un salto de proceso para procesar cada solicitud.

     La opción `/mex` agrega un extremo de servicio adicional de Intercambio de metadatos (MEX) que utiliza el mismo transporte que el extremo de servicio de la aplicación para admitir clientes que desean recuperar una definición del contrato del servicio.

## <a name="remove-a-web-service-for-a-specified-interface"></a>Quitar un servicio web para una interfaz especificada

- Ejecute ComSvcConfig utilizando la opción `/uninstall`, como se muestra en el ejemplo siguiente.

    ```console
    ComSvcConfig.exe /uninstall /application:OnlineStore /contract:ItemOrders.Financial,IFinances /hosting:complus
    ```

     El comando quita la interfaz `IFinances` del componente (de la aplicación OnlineStore COM+) `ItemOrders.Financial`.

## <a name="list-currently-exposed-interfaces"></a>Enumerar las interfaces actualmente expuestas

- Ejecute ComSvcConfig utilizando la opción `/list`, como se muestra en el ejemplo siguiente.

    ```console
    ComSvcConfig.exe /list
    ```

     El comando hace una lista de las interfaces actualmente expuestas, junto con la dirección correspondiente y los detalles del enlace, y se pone a disposición del equipo local.

## <a name="list-specific-currently-exposed-interfaces"></a>Enumerar interfaces específicas actualmente expuestas

- Ejecute ComSvcConfig utilizando la opción `/list`, como se muestra en el ejemplo siguiente.

    ```console
    ComSvcConfig.exe /list /application:OnlineStore /hosting:complus
    ```

     El comando hace una lista de las interfaces hospedadas por COM+ actualmente expuestas, junto con la dirección correspondiente y los detalles del enlace, para la aplicación OnlineStore COM+ en el equipo local.

## <a name="display-help-for-options"></a>Mostrar ayuda para opciones

- Ejecutar ComSvcConfig utilizando la opción /? , como se muestra en el ejemplo siguiente.

    ```console
    ComSvcConfig.exe /?
    ```

## <a name="see-also"></a>Vea también

- [Información general de la integración con aplicaciones COM+](integrating-with-com-plus-applications-overview.md)
