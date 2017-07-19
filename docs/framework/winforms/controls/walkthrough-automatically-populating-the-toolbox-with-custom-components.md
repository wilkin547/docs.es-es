---
title: "Tutorial: Rellenar autom&#225;ticamente el cuadro de herramientas con componentes personalizados | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "componentes personalizados, agregar al cuadro de herramientas"
  - "IToolboxService (interfaz)"
  - "Cuadro de herramientas [formularios Windows Forms], llenar"
ms.assetid: 2fa1e3e8-6b9f-42b2-97c0-2be57444dba4
caps.latest.revision: 22
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 22
---
# Tutorial: Rellenar autom&#225;ticamente el cuadro de herramientas con componentes personalizados
Si los componentes están definidos por un proyecto en la solución abierta actual, aparecerán automáticamente en el **Cuadro de herramientas**, sin que se requiera ninguna acción por parte del usuario.  También puede rellenar manualmente el **Cuadro de herramientas** con componentes personalizados mediante [Choose Toolbox Items Dialog Box \(Visual Studio\)](http://msdn.microsoft.com/es-es/bd07835f-18a8-433e-bccc-7141f65263bb), pero el **Cuadro de herramientas** tiene en cuenta los elementos en los resultados de la compilación de la solución, con todas las características siguientes:  
  
-   Implementa <xref:System.ComponentModel.IComponent>:  
  
-   No tiene <xref:System.ComponentModel.ToolboxItemAttribute> establecido en `false`;  
  
-   No tiene <xref:System.ComponentModel.DesignTimeVisibleAttribute> establecido en `false`.  
  
> [!NOTE]
>  El **Cuadro de herramientas** no sigue las cadenas de referencia, por lo que no mostrará en la solución elementos que no estén creados por un proyecto.  
  
 Este tutorial muestra cómo un componente personalizado aparece automáticamente en el **Cuadro de herramientas** cuando se ha compilado el componente.  Las tareas ilustradas en este tutorial incluyen:  
  
-   Crear un proyecto de formularios Windows Forms.  
  
-   Crear un componente personalizado.  
  
-   Crear una instancia de un componente personalizado.  
  
-   Descargar y volver a cargar un componente personalizado.  
  
 Cuando finalice, verá que el **Cuadro de herramientas** se rellena con un componente que ha creado.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Crear el proyecto  
 El primer paso es crear el proyecto y configurar el formulario.  
  
#### Para crear el proyecto  
  
1.  Cree un proyecto de aplicación basada en Windows denominado `ToolboxExample`.  
  
     Para obtener más información, vea [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Agregue un nuevo componente al proyecto.  Denomínelo `DemoComponent`.  
  
     Para obtener más información, vea [NIB:How to: Add New Project Items](http://msdn.microsoft.com/es-es/63d3e16b-de6e-4bb5-a0e3-ecec762201ce).  
  
3.  Compile el proyecto.  
  
4.  En el menú **Herramientas**, haga clic en el elemento **Opciones**.  Haga clic en **General** en el elemento **Diseñador de Windows Forms** y asegúrese de que la opción **AutoToolboxPopulate** está establecida en **True**.  
  
## Crear una instancia de un componente personalizado  
 El paso siguiente es crear una instancia del componente personalizado en el formulario.  Dado que el **Cuadro de herramientas** tiene en cuenta automáticamente el nuevo componente, este procedimiento es tan sencillo como crear cualquier otro componente o control.  
  
#### Para crear una instancia de un componente personalizado  
  
1.  Abra el formulario del proyecto en el **Diseñador de formularios**.  
  
2.  En el **Cuadro de herramientas**, haga clic en la nueva ficha denominada **Componentes de ToolboxExample**.  
  
     Cuando hace clic en la ficha, verá **DemoComponent**.  
  
    > [!NOTE]
    >  Por razones de rendimiento, los componentes del área rellenada automáticamente del **Cuadro de herramientas** no muestran mapas de bits personalizados y no se admite <xref:System.Drawing.ToolboxBitmapAttribute>.  Para mostrar un icono para un componente personalizado en el **Cuadro de herramientas**, use el cuadro de diálogo **Elegir elementos del cuadro de herramientas** para cargar ese componente.  
  
3.  Arrastre el componente al formulario.  
  
     Se crea una instancia del componente y se agrega a la **Bandeja de componentes**.  
  
## Descargar y volver a cargar un componente personalizado  
 El **Cuadro de herramientas** tiene en cuenta los componentes de cada proyecto cargado y, cuando se descarga un proyecto, quita las referencias a los componentes del proyecto.  
  
#### Para experimentar con el efecto de descargar y volver a cargar los componentes en el Cuadro de herramientas  
  
1.  Descargue el proyecto desde la solución.  
  
     Para obtener más información sobre la descarga de proyectos, vea [NIB:How to: Unload and Reload Projects](http://msdn.microsoft.com/es-es/abc0155b-8fcb-4ffc-95b6-698518a7100b).  Si se le indica que lo guarde, elija **Sí**.  
  
2.  Agregue un nuevo proyecto de **Aplicación para Windows** a la solución.  Abra el formulario en el **Diseñador**.  
  
     Ya no está la ficha **Componentes ToolboxExample** del proyecto anterior.  
  
3.  Vuelva a cargar el proyecto `ToolboxExample`.  
  
     La ficha **Componentes ToolboxExample** reaparece.  
  
## Pasos siguientes  
 Este tutorial muestra que el **Cuadro de herramientas** tiene en cuenta los componentes de un proyecto, pero el **Cuadro de herramientas** también tiene en cuenta los controles.  Experimente con sus propios controles personalizados agregando y quitando proyectos de control de la solución.  
  
## Vea también  
 [General, Windows Forms Designer, Options Dialog Box](http://msdn.microsoft.com/es-es/8dd170af-72f0-4212-b04b-034ceee92834)   
 [How to: Manipulate Toolbox Tabs](http://msdn.microsoft.com/es-es/21285050-cadd-455a-b1f5-a2289a89c4db)   
 [Choose Toolbox Items Dialog Box \(Visual Studio\)](http://msdn.microsoft.com/es-es/bd07835f-18a8-433e-bccc-7141f65263bb)   
 [Insertar controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)