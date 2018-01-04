---
title: InvokeMethod
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 04988eb3-65f8-456d-b1bd-509f5d05a57c
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b90ebec929b310442cde2be8d96386e016a9bbb4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="invokemethod"></a>InvokeMethod
En este ejemplo se muestran las maneras diferentes de utilizar la actividad <xref:System.Activities.Statements.InvokeMethod> para invocar métodos de una clase.  
  
 Un método pertenece a una clase y representa un conjunto contenido de operaciones. La actividad <xref:System.Activities.Statements.InvokeMethod> proporciona la capacidad de llamar a los métodos en objetos o tipos, pasar parámetros y obtener el valor devuelto. Los métodos se pueden invocar sincrónica o asincrónicamente.  
  
## <a name="sample-details"></a>Detalles del ejemplo  
 En este ejemplo se utiliza la actividad <xref:System.Activities.Statements.InvokeMethod> para realizar los siguientes escenarios:  
  
1.  Invoque un método de instancia sin parámetros.  
  
2.  Invocar un método de instancia con dos parámetros (<xref:System.String> y <xref:System.Int32>).  
  
3.  Invocar un método de instancia con dos parámetros (<xref:System.String> y <xref:System.Int32>) y una matriz de parámetros de tipo <xref:System.String>[].  
  
4.  Invocar un método de instancia con dos parámetros de tipo <xref:System.Int32> y un resultado de tipo <xref:System.Int32>. En este escenario, el valor de resultado se enlaza a una variable y se utiliza en otra actividad. Se muestra en la consola utilizando la actividad <xref:System.Activities.Statements.WriteLine>.  
  
5.  Invocar un método estático con dos parámetros de tipo <xref:System.String> y <xref:System.Int32>.  
  
6.  Invocar un método de instancia con un parámetro genérico de tipo <xref:System.String>.  
  
7.  Invocar un método estático con dos parámetros genéricos de tipo <xref:System.String> y <xref:System.Int32>.  
  
8.  Invocar un método de instancia que tiene un parámetro pasado por referencia de tipo <xref:System.String>. En este escenario, el parámetro de referencia se enlaza a una variable (`outParam`) y se utiliza en otra actividad. Se muestra en la consola utilizando la actividad <xref:System.Activities.Statements.WriteLine>.  
  
9. Invoque un método de instancia asincrónico.  
  
10. Invocar dos métodos diferentes en la misma instancia de un objeto utilizando dos actividades <xref:System.Activities.Statements.InvokeMethod>.  
  
11. Almacenar un valor en una instancia de un objeto.  
  
12. Recuperar un valor de una instancia de un objeto.  
  
## <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
 Este ejemplo se proporciona en dos versiones. La primera versión de este ejemplo muestra el uso de <xref:System.Activities.Statements.InvokeMethod> mediante código de C# utilizando el modelo de programación de [!INCLUDE[wf](../../../../includes/wf-md.md)] y se puede encontrar en la carpeta CodedWorkflow\CS. La segunda versión muestra el uso de <xref:System.Activities.Statements.InvokeMethod> utilizando XAML y se puede encontrar en la carpeta DesignerWorkflow\CS.  
  
#### <a name="to-run-the-coded-workflow-sample"></a>Para ejecutar el ejemplo de flujo de trabajo codificado  
  
1.  Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución InvokeMethodUsage.sln en la carpeta CodedWorkflow\CS.  
  
2.  Para compilar la solución, presione Ctrl+MAYÚS+B.  
  
3.  Para ejecutar la solución, presione CTRL+F5.  
  
#### <a name="to-run-the-designer-workflow-sample"></a>Para ejecutar el ejemplo de flujo de trabajo de diseñador  
  
1.  Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución InvokeMethodUsage.sln en la carpeta DesignerWorkflow\CS.  
  
2.  Para compilar la solución, presione Ctrl+MAYÚS+B.  
  
3.  Para ejecutar la solución, presione CTRL+F5.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InvokeMethod`