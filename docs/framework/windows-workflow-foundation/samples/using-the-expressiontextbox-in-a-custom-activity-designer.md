---
title: Uso de la ExpressionTextBox en un diseñador de actividad personalizado
ms.date: 03/30/2017
ms.assetid: f82e73e7-a256-4a4d-82b7-c0d62f4ab5e7
ms.openlocfilehash: dfb53096be59abd9924a024880d4125ca774d4b8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96267504"
---
# <a name="using-the-expressiontextbox-in-a-custom-activity-designer"></a>Uso de la ExpressionTextBox en un diseñador de actividad personalizado

En este ejemplo se muestra cómo utilizar el objeto <xref:System.Activities.Presentation.View.ExpressionTextBox> en un diseñador de actividad personalizado. La actividad personalizada, `MultiAssign`, asigna dos valores de cadena a dos variables de cadena. Algunos controles de <xref:System.Activities.Presentation.View.ExpressionTextBox> se enlazan a argumentos <xref:System.Activities.InArgument> y otros a argumentos <xref:System.Activities.OutArgument>.

## <a name="sample-details"></a>Detalles del ejemplo

 `ArgumentToExpressionConverter` es el convertidor de tipos utilizado cuando se enlazan expresiones a argumentos. `ConverterParameter` debe establecerse en `In` o en `Out`, según corresponda. No se admite `InOut`.

 El `UseLocationExpression` atributo se usa en `OutArgument` s para especificar que la expresión debe ser una expresión de valor L ("valor izquierdo" o "valor de ubicación"). En la mayoría de los casos, una expresión de valor L es un identificador de Visual Basic válido que se usa para indicar que el argumento `OutArgument` que se devuelve es una variable o nombre de argumento.

 El atributo `MaxLines` se establece en uno en este ejemplo y `MinLines` no se establece. Esto indica que <xref:System.Activities.Presentation.View.ExpressionTextBox> representa el tamaño fijo de una línea, independientemente de la cantidad de texto que escriba el usuario. Para permitir que <xref:System.Activities.Presentation.View.ExpressionTextBox> aumente de tamaño para ajustarse a los datos proporcionados por el usuario, establezca el valor de `MaxLines` como mayor que `MinLines`.

 ExpressionTextBox solo se puede enlazar a argumentos y no a propiedades CLR.

#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo

1. Con Visual Studio 2010, abra el archivo ExpressionTextBoxSample. sln.

2. Para compilar la solución, presione Ctrl+MAYÚS+B.

#### <a name="to-run-this-sample"></a>Para ejecutar el ejemplo

1. Agregue a la solución una aplicación de consola de flujos de trabajo.

2. Agregue una referencia al proyecto **ExpressionTextBoxSample** desde el nuevo proyecto de aplicación de consola de flujos de trabajo.

3. Compile la solución.

4. Arrastre la actividad de **asignación Multiasignada** desde el cuadro de herramientas y colóquela en el flujo de trabajo.

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\ExpressionTextBox`  
  
## <a name="see-also"></a>Vea también

- <xref:System.Activities.Presentation.View.ExpressionTextBox>
- [Desarrollar aplicaciones con el Diseñador de flujo de trabajo](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
