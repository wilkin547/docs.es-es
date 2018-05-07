---
title: Determinar la duración de la operación de servicio
ms.date: 03/30/2017
ms.assetid: e8a93a2c-2c20-48b3-8986-57e90e9aa908
ms.openlocfilehash: a7615a4574210ad6e9b5eee2e5d5855365768854
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="determining-service-operation-duration"></a>Determinar la duración de la operación de servicio
Si está habilitada la traza analítica en una aplicación de Windows Communication Foundation (WCF), la duración de ejecución de una operación de servicio fácilmente se puede determinar examinando el registro de eventos.  En este tema se muestra cómo determinar la cantidad de tiempo que una operación de servicio tarda en completarse.  
  
### <a name="determining-service-operation-execution-duration"></a>Determinar la duración de la ejecución de la operación de servicio  
  
1.  Abra el Visor de eventos, haga clic en **iniciar**, **ejecutar**y escriba `eventvwr.exe`.  
  
2.  Si no ha habilitado la traza analítica, expanda **registros de aplicaciones y servicios**, **Microsoft**, **Windows**, **servidor de aplicaciones** . Seleccione **vista**, **mostrar analíticos y de depuración registros**. Haga clic en **analítico** y seleccione **Habilitar registro**. Deje abierto el Visor de eventos para que los seguimientos se puedan ver cuando se ejecute la operación de servicio.  
  
3.  Luego, abra una aplicación de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] que incluya un proyecto de servicio y un proyecto de cliente que interactúe con ese servicio.  Puede crear este tipo de aplicación siguiendo la [Tutorial de introducción](../../../../../docs/framework/wcf/getting-started-tutorial.md).  Si tiene la [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] ejemplos instalados, puede abrir el [Introducción](../../../../../docs/framework/wcf/samples/getting-started-sample.md), que contiene el proyecto completado creado en el tutorial.  
  
4.  Ejecute la aplicación de servidor presionando **F5**. Ejecutar la aplicación cliente con el botón secundario en el **cliente** proyecto y seleccione **depurar**, **Iniciar nueva instancia**.  
  
5.  En el Visor de eventos, actualice el registro analítico y ordene los eventos por identificador.  Busque eventos con Id. de evento [214 - OperationCompleted](../../../../../docs/framework/wcf/diagnostics/etw/214-operationcompleted.md).  Estos eventos mostrarán qué operaciones se han completado y cuál fue su duración.  El siguiente evento muestra la duración de una operación de agregar.  
  
    ```Output  
    An OperationInvoker completed the call to the 'Add' method.  The method call duration was '3' ms.  
    ```
