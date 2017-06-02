---
title: "Supervisar los errores de operaci&#243;n de servicio | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 59472ba3-8ebf-4479-bd7b-f440d5e636cb
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Supervisar los errores de operaci&#243;n de servicio
Si la traza analítica está habilitada para una aplicación, los errores del servicio se pueden supervisar con facilidad en el visor de eventos.Este tema muestra cómo determinar cuándo se produce un error en una operación del servicio y cómo determinar lo que produjo el error.  
  
### Determinar la información de error de la operación del servicio  
  
1.  Abra el Visor de eventos; para ello, haga clic en **Inicio** y en **Ejecutar**, y escriba `eventvwr.exe`.  
  
2.  Si no ha habilitado la traza analítica, expanda **Registros de aplicaciones y servicios**, **Microsoft**, **Windows** y **Servidor de aplicaciones\-Aplicaciones**Seleccione **Ver**, **Mostrar registros analíticos y de depuración**.Haga clic con el botón secundario en **Analítico** y seleccione **Habilitar registro**.Deje abierto el Visor de eventos para que los seguimientos se puedan ver cuando se produzca el error en la operación de servicio.  
  
3.  Luego, abra el ejemplo creado en el [Tutorial de introducción](../../../../../docs/framework/wcf/getting-started-tutorial.md) en [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)]. Observe que debe ejecutar [!INCLUDE[vs_current_long](../../../../../includes/vs-current-long-md.md)] como administrador para que se pueda crear el servicio.Si tiene instalados los ejemplos de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)], puede abrir [Introducción:](../../../../../docs/framework/wcf/samples/getting-started-sample.md), que contiene el proyecto completado creado en el tutorial.  
  
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
  
6.  Ejecute la aplicación de servidor sin depurar presionando **Ctrl\+F5**.  
  
7.  Abra un símbolo del sistema de Visual Studio 2010.Desplácese hasta el directorio de cliente y ejecute el cliente desde la línea de comandos.  
  
8.  En el Visor de eventos, deshabilite el registro analítico y actualícelo, y ordene los eventos por identificador de evento.Busque un evento con el identificador de evento [219 \- ServiceException](../../../../../docs/framework/wcf/diagnostics/etw/219-serviceexception.md), que describe el error del servicio.  
  
    ```Output  
    Se produjo una excepción no controlada de tipo 'System.DivideByZeroException' durante el procesamiento del mensaje.Excepción completa ToString: System.DivideByZeroException: Se intentó dividir por cero.  
    ```  
  
    > [!NOTE]
    >  Los eventos se almacenan en búfer al enviarse al visor de eventos; el evento erróneo puede no aparecer enseguida.