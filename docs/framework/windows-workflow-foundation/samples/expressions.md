---
title: "Expresiones | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 43a85905-77b5-4893-bb38-1cb9b293d69d
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Expresiones
En este ejemplo se muestra cómo utilizar expresiones básicas en un flujo de trabajo.Consta de un flujo de trabajo que calcula estadísticas de sueldo básicas para dos empleados de una compañía ficticia.Dos clases, `Employee` y `SalaryStats`, se definen en Employee.cs y SalaryStats.cs.Estas clases se utilizan en un flujo de trabajo que muestra cómo realizar operaciones de aritmética y cadena sencillas en las propiedades de variables de tipos complejos.  
  
 El flujo de trabajo de cálculo de sueldo se define en XAML y en C\# para mostrar los dos estilos de creación.La versión de XAML está incluida en SalaryCalculation.xaml y se puede ver y editar en el diseñador de flujo de trabajo.La versión de C\# se encuentra en Program.cs.Las expresiones utilizadas en XAML cumplen la sintaxis de Visual Basic y utilizan las actividades de expresión <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> y <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601> para ejecutarse.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] las expresiones de Visual Basic, vea [Expresiones de Visual Basic](http://go.microsoft.com/fwlink/?LinkId=165912).Por otro lado, las expresiones de C\# se escriben como expresiones lambda y utilizan las actividades de expresión <xref:System.Activities.Expressions.LambdaValue%601> y <xref:System.Activities.Expressions.LambdaReference%601>.Al escribir las expresiones como expresiones lambda, el compilador de C\# puede proporcionar resaltado de sintaxis y comprobación estática.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] las expresiones lambda en C\#, vea [Expresiones lambda \(Guía de programación de C\#\)](http://go.microsoft.com/fwlink/?LinkId=182082).Si un flujo de trabajo se crea en código usando Visual Basic, se usan expresiones lambda de Visual Basic.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] las expresiones lambda en Visual Basic, vea [Lambda \(expresiones\) \(Visual Basic\)](http://go.microsoft.com/fwlink/?LinkId=152437).[!INCLUDE[crabout](../../../../includes/crabout-md.md)] cómo crear flujos de trabajo mediante código, vea [Crear flujos de trabajo, actividades y expresiones mediante código imperativo](../../../../docs/framework/windows-workflow-foundation//authoring-workflows-activities-and-expressions-using-imperative-code.md).  
  
#### Para ejecutar el ejemplo  
  
1.  Abra la solución Expressions.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Para compilar la solución, presione CTRL\+MAYÚS\+B o seleccione **Compilar solución** en el menú **Compilar**.  
  
    > [!NOTE]
    >  Para abrir SalaryCalculation.xaml en el diseñador de Visual Studio, debe compilar en primer lugar el proyecto para asegurarse de que las clases `Employee` y `SalaryStats` están disponibles para el diseñador.  
  
3.  Cuando la compilación finalice correctamente, presione F5 o seleccione **Iniciar depuración** en el menú **Depurar**.También puede presionar CTRL\+F5 o seleccionar **Iniciar sin depurar** en el menú **Depurar** para realizar la ejecución sin depuración.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Basic\Expressions`  
  
## Vea también