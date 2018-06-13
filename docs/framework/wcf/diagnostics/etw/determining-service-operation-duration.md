---
title: Determinar la duración de la operación de servicio
ms.date: 03/30/2017
ms.assetid: e8a93a2c-2c20-48b3-8986-57e90e9aa908
ms.openlocfilehash: 8c86ccc09979071e0678be792f4937d526e23fa7
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
ms.locfileid: "33804968"
---
# <a name="determining-service-operation-duration"></a>Determinar la duración de la operación de servicio
Si está habilitada la traza analítica en una aplicación de Windows Communication Foundation (WCF), la duración de ejecución de una operación de servicio fácilmente se puede determinar examinando el registro de eventos.  En este tema se muestra cómo determinar la cantidad de tiempo que una operación de servicio tarda en completarse.  
  
### <a name="determining-service-operation-execution-duration"></a>Determinar la duración de la ejecución de la operación de servicio  
  
1.  Abra el Visor de eventos, haga clic en **iniciar**, **ejecutar**y escriba `eventvwr.exe`.  
  
2.  Si no ha habilitado la traza analítica, expanda **registros de aplicaciones y servicios**, **Microsoft**, **Windows**, **servidor de aplicaciones** . Seleccione **vista**, **mostrar analíticos y de depuración registros**. Haga clic en **analítico** y seleccione **Habilitar registro**. Deje abierto el Visor de eventos para que los seguimientos se puedan ver cuando se ejecute la operación de servicio.  
  
3.  A continuación, abra una aplicación de WCF que incluye un proyecto de servicio y un proyecto de cliente que interactúa con ese servicio.  Puede crear este tipo de aplicación siguiendo la [Tutorial de introducción](../../../../../docs/framework/wcf/getting-started-tutorial.md).  Si tiene instalados los ejemplos de WCF, puede abrir el [Introducción](../../../../../docs/framework/wcf/samples/getting-started-sample.md), que contiene el proyecto completado creado en el tutorial.  
  
4.  Ejecute la aplicación de servidor presionando **F5**. Ejecutar la aplicación cliente con el botón secundario en el **cliente** proyecto y seleccione **depurar**, **Iniciar nueva instancia**.  
  
5.  En el Visor de eventos, actualice el registro analítico y ordene los eventos por identificador.  Busque eventos con Id. de evento [214 - OperationCompleted](../../../../../docs/framework/wcf/diagnostics/etw/214-operationcompleted.md).  Estos eventos mostrarán qué operaciones se han completado y cuál fue su duración.  El siguiente evento muestra la duración de una operación de agregar.  
  
    ```Output  
    An OperationInvoker completed the call to the 'Add' method.  The method call duration was '3' ms.  
    ```
