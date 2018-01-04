---
title: Actividad CommentOut
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 340204c3-f827-45fb-870e-55e2ac457ca5
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 900f6647eadb04a783fe0a3a143a71d9c766a48c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="commentout-activity"></a>Actividad CommentOut
En este ejemplo se muestra cómo escribir una actividad personalizada que quita otras actividades de la ruta de acceso de ejecución, marcándolas como comentario.  
  
## <a name="the-commentout-activity"></a>Actividad CommentOut  
 Para lograr su objetivo, la actividad CommentOut deriva de la clase base <xref:System.Activities.CodeActivity> e implementa un método <xref:System.Activities.CodeActivity.Execute%2A> vacío.  
  
```  
protected override void Execute(CodeActivityContext context)  
{  
}  
```  
  
 La clase se declara tal como se muestra en el ejemplo siguiente.  
  
```  
[Designer(typeof(CommentOutDesigner))]  
[ContentProperty("Body")]  
public sealed class CommentOut : CodeActivity  
```  
  
 El atributo `Designer` especifica la clase que implementa la interfaz visual de la actividad en tiempo de diseño. El atributo `ContentProperty` declara que la propiedad `"Body"` se puede omitir en la representación de XAML de una instancia de esta actividad.  
  
```  
<Border x:Uid="Border_1" BorderThickness ="1">  
    <sad:WorkflowItemPresenter   
    x:Uid="sad:WorkflowItemPresenter_1" AutomationProperties.AutomationId="Body" Item="{Binding Path=ModelItem.Body, Mode=TwoWay}"  
    AllowedItemType="{x:Type sa:Activity}"  
    HintText="Drop activity here"   
    Margin="5,5,5,5" />  
</Border>  
```  
  
 En la clase de diseñador, XAML se usa para crear una representación visual personalizada de la actividad. <xref:System.Activities.Presentation.WorkflowItemPresenter> es una clase que proporciona el editor visual.  
  
 En la superficie de la actividad `CommentOut` solamente se puede colocar una única actividad. Si desea agregar varias actividades a esta superficie, arrastre una actividad de secuencia primero.  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Abra CommentOut.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Compile la solución presionando CTRL+SHIFT+B.  
  
3.  Inicie el ejemplo sin depuración presionando CTRL+F5.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\CommentOut`
