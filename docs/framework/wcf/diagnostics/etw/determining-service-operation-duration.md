---
title: "Determinar la duraci&#243;n de la operaci&#243;n de servicio | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e8a93a2c-2c20-48b3-8986-57e90e9aa908
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Determinar la duraci&#243;n de la operaci&#243;n de servicio
Si la traza analítica está habilitada en una aplicación de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], la duración de la ejecución de una operación del servicio se puede determinar con facilidad examinando el registro de eventos.  En este tema se muestra cómo determinar la cantidad de tiempo que una operación de servicio tarda en completarse.  
  
### Determinar la duración de la ejecución de la operación de servicio  
  
1.  Abra el Visor de eventos; para ello, haga clic en **Inicio** y en **Ejecutar**, y escriba `eventvwr.exe`.  
  
2.  Si no ha habilitado la traza analítica, expanda **Registros de aplicaciones y servicios**, **Microsoft**, **Windows** y **Servidor de aplicaciones\-Aplicaciones** Seleccione **Ver**, **Mostrar registros analíticos y de depuración**.  Haga clic con el botón secundario en **Analítico** y seleccione **Habilitar registro**.  Deje abierto el Visor de eventos para que los seguimientos se puedan ver cuando se ejecute la operación de servicio.  
  
3.  Luego, abra una aplicación de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] que incluya un proyecto de servicio y un proyecto de cliente que interactúe con ese servicio.  Puede crear este tipo de aplicación si sigue el [Tutorial de introducción](../../../../../docs/framework/wcf/getting-started-tutorial.md).  Si tiene instalados los ejemplos de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)], puede abrir [Introducción:](../../../../../docs/framework/wcf/samples/getting-started-sample.md), que contiene el proyecto completado creado en el tutorial.  
  
4.  Ejecute la aplicación de servidor presionando **F5**.  Ejecute la aplicación cliente haciendo clic con el botón secundario en el proyecto **Cliente** y seleccionando **Depuración** e **Iniciar nueva instancia**.  
  
5.  En el Visor de eventos, actualice el registro analítico y ordene los eventos por identificador.  Busque los eventos con el identificador [214 \- OperationCompleted](../../../../../docs/framework/wcf/diagnostics/etw/214-operationcompleted.md).  Estos eventos mostrarán qué operaciones se han completado y cuál fue su duración.  El siguiente evento muestra la duración de una operación de agregar.  
  
    ```Output  
  
    Un OperationInvoker completó la llamada al método 'Add'.  La duración de la llamada al método fue de '3' ms.    
    ```