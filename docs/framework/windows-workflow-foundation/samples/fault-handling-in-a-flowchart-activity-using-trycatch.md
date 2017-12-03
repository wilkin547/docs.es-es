---
title: Control de errores en una actividad de diagrama de flujo utilizando TryCatch
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50922964-bfe0-4ba8-9422-0e7220d514fd
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0d8bccc1b9505f685fd4e358216e76c22ec751e9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="fault-handling-in-a-flowchart-activity-using-trycatch"></a>Control de errores en una actividad de diagrama de flujo utilizando TryCatch
En este ejemplo se muestra cómo se puede usar la actividad <xref:System.Activities.Statements.TryCatch> dentro de una actividad de flujo de control compleja.  
  
 En este ejemplo, se pasan un código de la promoción y el número de hijos como variables a una actividad <xref:System.Activities.Statements.Flowchart> que calcula un descuento en función de fórmulas que corresponden al código de promoción. En el ejemplo se incluyen las versiones de código imperativo y de diseñador de flujo de trabajo del ejemplo.  
  
 En la siguiente tabla se detallan las variables de la actividad `CreateFlowchartWithFaults`.  
  
|Parámetros|Descripción|  
|----------------|-----------------|  
|promoCode|El código de la promoción. Tipo: string<br /><br /> Los posibles valores con descripción en paréntesis:<br /><br /> -Único (simple)<br />-MNK (casado / a sin hijos).<br />-MWK (casado / con hijos).|  
|numKids|El número de hijos. Tipo: int|  
  
 La actividad `CreateFlowchartWithFaults` utiliza una actividad <xref:System.Activities.Statements.FlowSwitch%601> que activa el argumento `promoCode` y calcula el descuento mediante la siguiente fórmula.  
  
|Valor de `promoCode`|Descuento (%)|  
|--------------------------|--------------------|  
|Single|10|  
|MNK|15|  
|MWK|15 + (1 – 1 /`numberOfKids`)\*10 **Nota:** potencialmente, puede producir este cálculo un <xref:System.DivideByZeroException>. Por tanto, el cálculo del descuento se incluye en una actividad <xref:System.Activities.Statements.TryCatch> que detecta la excepción <xref:System.DivideByZeroException> y establece el descuento en cero.|  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución FlowchartWithFaultHandling.sln.  
  
2.  Para compilar la solución, presione Ctrl+MAYÚS+B.  
  
3.  Presione F5 para ejecutar la solución.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\FlowChartWithFaultHandling`  
  
## <a name="see-also"></a>Vea también  
 [Flujos de trabajo del diagrama de flujo](../../../../docs/framework/windows-workflow-foundation/flowchart-workflows.md)  
 [Excepciones](../../../../docs/framework/windows-workflow-foundation/exceptions.md)
