---
title: "Determinar la duración de la operación de servicio"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8a93a2c-2c20-48b3-8986-57e90e9aa908
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 63a8c92713ee452da2439475ac526229d1e5741c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="determining-service-operation-duration"></a>Determinar la duración de la operación de servicio
Si la traza analítica está habilitada en una aplicación de [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], la duración de la ejecución de una operación del servicio se puede determinar con facilidad examinando el registro de eventos.  En este tema se muestra cómo determinar la cantidad de tiempo que una operación de servicio tarda en completarse.  
  
### <a name="determining-service-operation-execution-duration"></a>Determinar la duración de la ejecución de la operación de servicio  
  
1.  Abra el Visor de eventos, haga clic en **iniciar**, **ejecutar**y escriba `eventvwr.exe`.  
  
2.  Si no ha habilitado la traza analítica, expanda **registros de aplicaciones y servicios**, **Microsoft**, **Windows**, **servidor de aplicaciones** . Seleccione **vista**, **mostrar analíticos y de depuración registros**. Haga clic en **analítico** y seleccione **Habilitar registro**. Deje abierto el Visor de eventos para que los seguimientos se puedan ver cuando se ejecute la operación de servicio.  
  
3.  Luego, abra una aplicación de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] que incluya un proyecto de servicio y un proyecto de cliente que interactúe con ese servicio.  Puede crear este tipo de aplicación siguiendo la [Tutorial de introducción](../../../../../docs/framework/wcf/getting-started-tutorial.md).  Si tiene la [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] ejemplos instalados, puede abrir el [Introducción](../../../../../docs/framework/wcf/samples/getting-started-sample.md), que contiene el proyecto completado creado en el tutorial.  
  
4.  Ejecute la aplicación de servidor presionando **F5**. Ejecutar la aplicación cliente con el botón secundario en el **cliente** proyecto y seleccione **depurar**, **Iniciar nueva instancia**.  
  
5.  En el Visor de eventos, actualice el registro analítico y ordene los eventos por identificador.  Busque eventos con Id. de evento [214 - OperationCompleted](../../../../../docs/framework/wcf/diagnostics/etw/214-operationcompleted.md).  Estos eventos mostrarán qué operaciones se han completado y cuál fue su duración.  El siguiente evento muestra la duración de una operación de agregar.  
  
    ```Output  
    An OperationInvoker completed the call to the 'Add' method.  The method call duration was '3' ms.  
    ```
