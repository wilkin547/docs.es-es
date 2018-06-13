---
title: Directiva avanzada
ms.date: 03/30/2017
ms.assetid: 75a22c88-5e54-4ae8-84cb-fbb22a612f0a
ms.openlocfilehash: 81cf2fb428833d4ca8cccf197011b69f2ccf3108
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515560"
---
# <a name="advanced-policy"></a>Directiva avanzada
Este ejemplo amplía el ejemplo de directiva simple. Además de las reglas de descuento residencial y descuento comercial del ejemplo de directiva simple, se han agregado varias nuevas reglas.  
  
 Se agrega una regla de valor alto, que proporciona un descuento mayor para los pedidos de valor alto. Se le proporciona un valor de prioridad menor que el de las dos reglas anteriores, para que sobrescriba el campo de descuento y tenga prioridad sobre la regla de descuento residencial o la de descuento comercial.  
  
 También se agrega una regla de cálculo del total, que calcula el total en función del nivel de descuento. Muestra cómo hacer referencia a un método definido en la actividad de flujo de trabajo, y cómo utilizar las acciones Else. Esta regla también muestra el comportamiento del encadenamiento, puesto que se evaluará siempre que cambie el campo de descuento. Además, se muestra la atribución de método con RuleWriteAttribute en el método CalculateTotal. Esto hace que las reglas afectadas (ErrorTotalRule) se vuelvan a evaluar siempre que se ejecuta el método.  
  
 La última regla agregada es la que detecta errores (en este caso, Total menor que 0). Si ocurre esto, se detiene la ejecución de la directiva.  
  
 Finalmente, se agregan llamadas a `Console.Writeline` como acciones a cada regla para proporcionar más visibilidad de la ejecución de las reglas, a la vez que se muestra que es posible tener acceso a los métodos estáticos en tipos a los que se hace referencia. También puede usar el seguimiento para obtener visibilidad en las reglas que se ejecutan.  
  
 Este ejemplo hace uso de las clases siguientes.  
  
 **ResidentialDiscountRule:**  
  
 IF OrderValue > 500 AND CustomerType = Residential  
  
 THEN Discount = 5%  
  
 **BusinessDiscountRule:**  
  
 IF OrderValue > 10000 AND CustomerType = Business  
  
 THEN Discount = 10%  
  
 **HighValueDiscountRule:**  
  
 IF OrderValue > 20000  
  
 THEN Discount = 15%  
  
 **TotalRule:**  
  
 IF Discount > 0  
  
 THEN CalculateTotal(OrderValue, Discount)  
  
 ELSE Total = OrderValue  
  
 **ErrorTotalRule:**  
  
 IF Total \< 0  
  
 THEN Error = "Fired ErrorTotalRule"; Halt  
  
 La evaluación y ejecución de las reglas también se puede ver mediante el seguimiento y el seguimiento.  
  
### <a name="to-build-the-sample"></a>Para compilar el ejemplo  
  
1.  Abra la solución en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Compile la solución presionando CTRL+MAYÚS+B.  
  
3.  Ejecute la solución sin depuración presionando CTRL+F5.  
  
### <a name="to-run-the-sample"></a>Para ejecutar el ejemplo  
  
-   En la ventana del símbolo del sistema del SDK, ejecute el archivo .exe de la carpeta AdvancedPolicy\bin\debug (o la carpeta AdvancedPolicy\bin para la versión de Visual Basic del ejemplo), que se encuentra debajo de la carpeta principal del ejemplo.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar:  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio:  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\AdvancedPolicy`  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Workflow.Activities.Rules.RuleSet>  
 <xref:System.Workflow.Activities.PolicyActivity>  
 [Directiva simple](../../../../docs/framework/windows-workflow-foundation/samples/simple-policy.md)
