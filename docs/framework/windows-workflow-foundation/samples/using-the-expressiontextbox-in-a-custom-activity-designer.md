---
title: Uso de la ExpressionTextBox en un diseñador de actividad personalizado
ms.date: 03/30/2017
ms.assetid: f82e73e7-a256-4a4d-82b7-c0d62f4ab5e7
ms.openlocfilehash: ad0c29e2661c82e663fd6b68fdcd74f542ef28b1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33516791"
---
# <a name="using-the-expressiontextbox-in-a-custom-activity-designer"></a>Uso de la ExpressionTextBox en un diseñador de actividad personalizado
En este ejemplo se muestra cómo utilizar el objeto <xref:System.Activities.Presentation.View.ExpressionTextBox> en un diseñador de actividad personalizado. La actividad personalizada, `MultiAssign`, asigna dos valores de cadena a dos variables de cadena. Algunos controles de <xref:System.Activities.Presentation.View.ExpressionTextBox> se enlazan a argumentos <xref:System.Activities.InArgument> y otros a argumentos <xref:System.Activities.OutArgument>.  
  
## <a name="sample-details"></a>Detalles del ejemplo  
 `ArgumentToExpressionConverter` es el convertidor de tipos utilizado cuando se enlazan expresiones a argumentos. `ConverterParameter` debe establecerse en `In` o en `Out`, según corresponda. No se admite `InOut`.  
  
 El `UseLocationExpression` atributo se usa en `OutArgument`s para especificar que la expresión debe ser una expresión de valor L ("valor izquierdo" o "valor de ubicación"). En la mayoría de los casos, una expresión de valor L es un identificador de Visual Basic válido que se usa para indicar que el argumento `OutArgument` que se devuelve es una variable o nombre de argumento.  
  
 El atributo `MaxLines` se establece en uno en este ejemplo y `MinLines` no se establece. Esto indica que <xref:System.Activities.Presentation.View.ExpressionTextBox> representa el tamaño fijo de una línea, independientemente de la cantidad de texto que escriba el usuario. Para permitir que <xref:System.Activities.Presentation.View.ExpressionTextBox> aumente de tamaño para ajustarse a los datos proporcionados por el usuario, establezca el valor de `MaxLines` como mayor que `MinLines`.  
  
 ExpressionTextBox solo se puede enlazar a argumentos y no a propiedades CLR.  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Abra el archivo ExpressionTextBoxSample.sln con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Para compilar la solución, presione Ctrl+MAYÚS+B.  
  
#### <a name="to-run-this-sample"></a>Para ejecutar este ejemplo  
  
1.  Agregue a la solución una aplicación de consola de flujos de trabajo.  
  
2.  Agregue una referencia a la **ExpressionTextBoxSample** proyecto desde el nuevo proyecto de aplicación de consola de flujos de trabajo.  
  
3.  Compile la solución.  
  
4.  Arrastre el **MultiAssign** actividad en el cuadro de herramientas y colóquelo en el flujo de trabajo.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\ExpressionTextBox`  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Activities.Presentation.View.ExpressionTextBox>  
 [Desarrollar aplicaciones con el Diseñador de flujo de trabajo](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
