---
title: "C&#243;mo: Enlazar controles de Windows Forms con el componente BindingSource mediante el Dise&#241;ador | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "BindingSource (componente) [Windows Forms], enlazar controles"
  - "controles [Windows Forms], enlace"
  - "enlace de datos, BindingSource (componente)"
ms.assetid: 391ae170-de5c-40f8-8233-91cb2ee4683a
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# C&#243;mo: Enlazar controles de Windows Forms con el componente BindingSource mediante el Dise&#241;ador
Después de agregar los controles al formulario y determinar la interfaz de usuario para su aplicación, puede enlazar los controles a un origen de datos para que los usuarios puedan modificar y guardar datos relacionados con la aplicación en tiempo de ejecución.  
  
 Es más sencillo enlazar un control o una serie de controles de formularios Windows Forms utilizando el control <xref:System.Windows.Forms.BindingSource> como un puente entre los controles del formulario y el origen de datos.  
  
 Se pueden enlazar a datos uno o más controles de un formulario; en el siguiente procedimiento, un control <xref:System.Windows.Forms.TextBox> se enlaza a un origen de datos.  
  
 Para finalizar el procedimiento, se supone que lo enlazará a un origen de datos derivado de una base de datos.  Para obtener más información sobre cómo crear orígenes de datos a partir de otros almacenes de datos, vea [Información general sobre orígenes de datos](../Topic/Add%20new%20data%20sources.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para enlazar un control en tiempo de diseño  
  
1.  Arrastre un control <xref:System.Windows.Forms.TextBox> al formulario.  
  
2.  En la ventana **Propiedades**:  
  
    1.  Expanda el nodo **\(DataBindings\)**.  
  
    2.  Haga clic en la flecha que se encuentra junto a la propiedad <xref:System.Windows.Forms.TextBox.Text%2A>.  
  
         Se abre el editor de tipos de la interfaz de usuario de **DataSource**.  
  
         Si un origen de datos se ha configurado previamente para el proyecto o un formulario, éste aparecerá.  
  
3.  Haga clic en **Agregar origen de datos del proyecto** para conectar a los datos y crear un origen de datos.  
  
4.  En la página de bienvenida del **Asistente para la configuración de orígenes de datos**, haga clic en **Siguiente**.  
  
5.  En la página **Elegir un tipo de origen de datos**, seleccione **Base de datos**.  
  
6.  Seleccione una conexión de datos de la lista de conexiones disponible en la página **Elegir la conexión de datos**.  Si la conexión de datos deseada no está disponible, seleccione **Nueva conexión** para crear una nueva conexión de datos.  
  
7.  Elija **Sí, guardar la conexión** para almacenar la cadena de conexión en el archivo de configuración de la aplicación.  
  
8.  Seleccione los objetos de la base de datos que se van a colocar en la aplicación.  En este caso, seleccione un campo en una tabla que desea que <xref:System.Windows.Forms.TextBox> muestre.  
  
9. Si lo desea, reemplace el nombre predeterminado del conjunto de datos  
  
10. Haga clic en **Finalizar**.  
  
11. En la ventana **Propiedades**, haga clic en la flecha que se encuentra junto a la propiedad <xref:System.Windows.Forms.TextBox.Text%2A>.  En el editor de tipos de la interfaz de usuario de **DataSource**, seleccione el nombre del campo al que se va a enlazar <xref:System.Windows.Forms.TextBox>.  
  
     El editor de tipos de la interfaz de usuario de **DataSource** se cierra y se agregan el conjunto de datos, <xref:System.Windows.Forms.BindingSource> y el adaptador de tabla específico al formulario.  
  
## Vea también  
 <xref:System.Windows.Forms.BindingSource>   
 <xref:System.Windows.Forms.BindingNavigator>   
 [Información general sobre orígenes de datos](../Topic/Add%20new%20data%20sources.md)   
 [Orígenes de datos \(ventana\)](../Topic/Data%20Sources%20Window.md)