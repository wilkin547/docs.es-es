---
title: "Uso de la ExpressionTextBox en un dise&#241;ador de actividad personalizado | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f82e73e7-a256-4a4d-82b7-c0d62f4ab5e7
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Uso de la ExpressionTextBox en un dise&#241;ador de actividad personalizado
En este ejemplo se muestra cómo utilizar el objeto <xref:System.Activities.Presentation.View.ExpressionTextBox> en un diseñador de actividad personalizado.La actividad personalizada, `MultiAssign`, asigna dos valores de cadena a dos variables de cadena.Algunos controles de <xref:System.Activities.Presentation.View.ExpressionTextBox> se enlazan a argumentos <xref:System.Activities.InArgument> y otros a argumentos <xref:System.Activities.OutArgument>.  
  
## Detalles del ejemplo  
 `ArgumentToExpressionConverter` es el convertidor de tipos utilizado cuando se enlazan expresiones a argumentos.`ConverterParameter` debe establecerse en `In` o en `Out`, según corresponda.No se admite `InOut`.  
  
 El atributo `UseLocationExpression` se utiliza en argumentos `OutArgument` para especificar que la expresión debe ser de valor L \("valor izquierdo" o "valor de ubicación"\).En la mayoría de los casos, una expresión de valor L es un identificador de Visual Basic válido que se usa para indicar que el argumento `OutArgument` que se devuelve es una variable o nombre de argumento.  
  
 El atributo `MaxLines` se establece en uno en este ejemplo y `MinLines` no se establece.Esto indica que <xref:System.Activities.Presentation.View.ExpressionTextBox> representa el tamaño fijo de una línea, independientemente de la cantidad de texto que escriba el usuario.Para permitir que <xref:System.Activities.Presentation.View.ExpressionTextBox> aumente de tamaño para ajustarse a los datos proporcionados por el usuario, establezca el valor de `MaxLines` como mayor que `MinLines`.  
  
 ExpressionTextBox solo se puede enlazar a argumentos y no a propiedades CLR.  
  
#### Para utilizar este ejemplo  
  
1.  Abra el archivo ExpressionTextBoxSample.sln con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Para compilar la solución, presione Ctrl\+MAYÚS\+B.  
  
#### Para ejecutar este ejemplo  
  
1.  Agregue a la solución una aplicación de consola de flujos de trabajo.  
  
2.  Agregue una referencia al proyecto **ExpressionTextBoxSample** desde el nuevo proyecto de la aplicación de consola de flujos de trabajo.  
  
3.  Compile la solución.  
  
4.  Arrastre la actividad **MultiAssign** desde el cuadro de herramientas y colóquela en el flujo de trabajo.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(valor predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\ExpressionTextBox`  
  
## Vea también  
 <xref:System.Activities.Presentation.View.ExpressionTextBox>   
 [Desarrollar aplicaciones con el Diseñador de flujo de trabajo](../Topic/Developing%20Applications%20with%20the%20Workflow%20Designer.md)