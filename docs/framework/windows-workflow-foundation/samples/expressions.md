---
title: Expressions2
ms.date: 03/30/2017
ms.assetid: 43a85905-77b5-4893-bb38-1cb9b293d69d
ms.openlocfilehash: e852b62e6d0b6b4b3ddc19b197902de5325310a1
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44275098"
---
# <a name="expressions"></a>Expresiones
En este ejemplo se muestra cómo utilizar expresiones básicas en un flujo de trabajo. Consta de un flujo de trabajo que calcula estadísticas de sueldo básicas para dos empleados de una compañía ficticia. Dos clases, `Employee` y `SalaryStats`, se definen en Employee.cs y SalaryStats.cs. Estas clases se utilizan en un flujo de trabajo que muestra cómo realizar operaciones de aritmética y cadena sencillas en las propiedades de variables de tipos complejos.  
  
 El flujo de trabajo de cálculo de sueldo se define en XAML y en C# para mostrar los dos estilos de creación. La versión de XAML está incluida en SalaryCalculation.xaml y se puede ver y editar en el diseñador de flujo de trabajo. La versión de C# se encuentra en Program.cs. Las expresiones utilizadas en XAML cumplen la sintaxis de Visual Basic y utilizan las actividades de expresión <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> y <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601> para ejecutarse. Para obtener más información acerca de Visual Basic, vea expresiones [expresiones de Visual Basic](https://go.microsoft.com/fwlink/?LinkId=165912). Por otro lado, las expresiones de C# se escriben como expresiones lambda y utilizan las actividades de expresión <xref:System.Activities.Expressions.LambdaValue%601> y <xref:System.Activities.Expressions.LambdaReference%601>. Al escribir las expresiones como expresiones lambda, el compilador de C# puede proporcionar resaltado de sintaxis y comprobación estática. Para obtener más información sobre las expresiones lambda en C#, vea [expresiones Lambda (Guía de programación de C#)](https://go.microsoft.com/fwlink/?LinkId=182082). Si un flujo de trabajo se crea en código usando Visual Basic, se usan expresiones lambda de Visual Basic. Para obtener más información sobre las expresiones lambda en Visual Basic, vea [expresiones Lambda (Visual Basic)](https://go.microsoft.com/fwlink/?LinkId=152437). Para obtener más información acerca sobre la creación de flujos de trabajo mediante código, vea [creación de flujos de trabajo, actividades y expresiones mediante código imperativo](../../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md).  
  
#### <a name="to-run-the-sample"></a>Para ejecutar el ejemplo  
  
1.  Abra la solución Expressions.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Presione CTRL + MAYÚS + B para compilar la solución o seleccione **compilar solución** desde el **compilar** menú.  
  
    > [!NOTE]
    >  Para abrir SalaryCalculation.xaml en el diseñador de Visual Studio, debe compilar en primer lugar el proyecto para asegurarse de que las clases `Employee` y `SalaryStats` están disponibles para el diseñador.  
  
3.  Una vez que se ha realizado correctamente la compilación, presione F5 o seleccione **Iniciar depuración** desde el **depurar** menú. También puede presionar CTRL+F5 o seleccionar **iniciar sin depurar** desde el **depurar** menú ejecutar sin depuración.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Expressions`