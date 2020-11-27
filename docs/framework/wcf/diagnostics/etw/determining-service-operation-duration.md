---
title: Determinar la duración de la operación de servicio
ms.date: 03/30/2017
ms.assetid: e8a93a2c-2c20-48b3-8986-57e90e9aa908
ms.openlocfilehash: 2607efe0d469f1235ee3d43d62f5e9781681668d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254836"
---
# <a name="determining-service-operation-duration"></a>Determinar la duración de la operación de servicio

Si la traza analítica está habilitada en una aplicación Windows Communication Foundation (WCF), la duración de la ejecución de una operación de servicio se puede determinar fácilmente mediante el examen del registro de eventos.  En este tema se muestra cómo determinar la cantidad de tiempo que una operación de servicio tarda en completarse.  
  
### <a name="determining-service-operation-execution-duration"></a>Determinar la duración de la ejecución de la operación de servicio  
  
1. Para abrir Visor de eventos, haga clic en **Inicio**, **Ejecutar** y escriba `eventvwr.exe` .  
  
2. Si no ha habilitado el seguimiento analítico, expanda **registros de aplicaciones y servicios**, **Microsoft**, **Windows**, **servidor de aplicaciones-aplicaciones**. Seleccione **Ver**, **Mostrar registros analíticos y de depuración**. Haga clic con el botón secundario en **analítico** y seleccione **Habilitar registro**. Deje abierto el Visor de eventos para que los seguimientos se puedan ver cuando se ejecute la operación de servicio.  
  
3. A continuación, abra una aplicación WCF que incluya un proyecto de servicio y un proyecto de cliente que interactúe con ese servicio.  Puede crear este tipo de aplicación siguiendo el [tutorial de introducción](../../getting-started-tutorial.md).  Si tiene instalados los ejemplos de WCF, puede abrir el [Introducción](../../samples/getting-started-sample.md), que contiene el proyecto completado creado en el tutorial.  
  
4. Ejecute la aplicación de servidor presionando **F5**. Ejecute la aplicación cliente haciendo clic con el botón derecho en el proyecto de **cliente** y seleccionando **depurar**, **Iniciar nueva instancia**.  
  
5. En el Visor de eventos, actualice el registro analítico y ordene los eventos por identificador.  Busque eventos con el ID. [de evento 214-OperationCompleted](214-operationcompleted.md).  Estos eventos mostrarán qué operaciones se han completado y cuál fue su duración.  El siguiente evento muestra la duración de una operación de agregar.  
  
    ```output  
    An OperationInvoker completed the call to the 'Add' method.  The method call duration was '3' ms.  
    ```
