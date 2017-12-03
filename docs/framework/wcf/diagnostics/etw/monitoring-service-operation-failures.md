---
title: "Supervisar los errores de operación de servicio"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59472ba3-8ebf-4479-bd7b-f440d5e636cb
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c6030b1ad1dc3953137d3b068be1bceb99975a5f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="monitoring-service-operation-failures"></a>Supervisar los errores de operación de servicio
Si la traza analítica está habilitada para una aplicación, los errores del servicio se pueden supervisar con facilidad en el visor de eventos.  Este tema muestra cómo determinar cuándo se produce un error en una operación del servicio y cómo determinar lo que produjo el error.  
  
### <a name="determining-service-operation-failure-information"></a>Determinar la información de error de la operación del servicio  
  
1.  Abra el Visor de eventos, haga clic en **iniciar**, **ejecutar**y escriba `eventvwr.exe`.  
  
2.  Si no ha habilitado la traza analítica, expanda **registros de aplicaciones y servicios**, **Microsoft**, **Windows**, **servidor de aplicaciones** . Seleccione **vista**, **mostrar analíticos y de depuración registros**. Haga clic en **analítico** y seleccione **Habilitar registro**. Deje abierto el Visor de eventos para que los seguimientos se puedan ver cuando se produzca el error en la operación de servicio.  
  
3.  A continuación, abra el ejemplo creado en el [Tutorial de introducción](../../../../../docs/framework/wcf/getting-started-tutorial.md) en [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] tenga en cuenta que debe ejecutar [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] como administrador para que se puede crear el servicio. Si tiene la [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] ejemplos instalados, puede abrir el [Introducción](../../../../../docs/framework/wcf/samples/getting-started-sample.md), que contiene el proyecto completado creado en el tutorial.  
  
4.  En el archivo Program.cs del proyecto Servidor, agregue la siguiente línea de código al principio del método `Divide` en la clase `CalculatorService`:  
  
    ```  
    if (n2 == 0) throw new DivideByZeroException();  
    ```  
  
5.  En el archivo Program.cs del proyecto Cliente, cambie por cero el valor asignado a value2:  
  
    ```  
    //Call the Divide service operation  
    value1 = 22.00D;  
    value2 = 0.00D;  
    result = client.Divide(value1, value2);  
    Console.WriteLine("Divide({0}, {1}) = {2}", value1, value2, result);  
    ```  
  
6.  Ejecute la aplicación de servidor sin depurar presionando **CTRL+F5**.  
  
7.  Abra un símbolo del sistema de Visual Studio 2010.  Desplácese hasta el directorio de cliente y ejecute el cliente desde la línea de comandos.  
  
8.  En el Visor de eventos, deshabilite el registro analítico y actualícelo, y ordene los eventos por identificador de evento.  Busque un evento con el Id. de evento [ServiceException 219 -](../../../../../docs/framework/wcf/diagnostics/etw/219-serviceexception.md), que describe el error del servicio.  
  
    ```Output  
    There was an unhandled exception of type 'System.DivideByZeroException' during message processing.  Full Exception ToString: System.DivideByZeroException: Attempted to divide by zero.  
    ```  
  
    > [!NOTE]
    >  Los eventos se almacenan en búfer al enviarse al visor de eventos; el evento erróneo puede no aparecer enseguida.
