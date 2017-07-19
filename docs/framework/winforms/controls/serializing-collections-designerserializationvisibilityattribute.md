---
title: "Tutorial: Serializar colecciones de tipos est&#225;ndar con DesignerSerializationVisibilityAttribute | Microsoft Docs"
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
  - "colecciones, serializar"
  - "colecciones, tipos estándar"
  - "DesiginerSerializationVisibilityAttribute (clase)"
  - "serialización, colecciones"
  - "tipos estándar, colecciones"
ms.assetid: 020c9df4-fdc5-4dae-815a-963ecae5668c
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Tutorial: Serializar colecciones de tipos est&#225;ndar con DesignerSerializationVisibilityAttribute
Los controles personalizados exponen en algunas ocasiones una colección como una propiedad.  Este tutorial muestra cómo se utiliza la clase <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> para controlar cómo se serializa una colección en tiempo de diseño.  La aplicación del valor <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> a la propiedad de colección garantiza la serialización de la propiedad.  
  
 Para copiar el código de este tema como un listado sencillo, vea [How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](../Topic/How%20to:%20Serialize%20Collections%20of%20Standard%20Types%20with%20the%20DesignerSerializationVisibilityAttribute.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## Requisitos previos  
 Para poder completar este tutorial, necesitará:  
  
-   Permisos suficientes para poder crear y ejecutar proyectos de aplicación de Windows Forms en el equipo donde esté instalado Visual Studio.  
  
## Crear un control que tenga una colección serializable  
 El primer paso es crear un control que tenga una colección serializable como propiedad.  Puede modificar el contenido de esta colección utilizando el **Editor de la colección**, al que puede obtener acceso desde la ventana **Propiedades**.  
  
#### Para crear un control con una colección serializable  
  
1.  Cree un proyecto de Biblioteca de controles de Windows denominado `SerializationDemoControlLib`.  Para obtener más información, vea [Windows Control Library Template](http://msdn.microsoft.com/es-es/722f4e2d-1310-4ed5-8f33-593337ab66b4).  
  
2.  Cambie el nombre de `UserControl1` a `SerializationDemoControl`.  Para obtener más información, vea [How to: Rename Identifiers](http://msdn.microsoft.com/es-es/2430f732-2b70-4516-8cf6-a7bb71cc9724).  
  
3.  En la ventana **Propiedades**, establezca el valor de la propiedad <xref:System.Windows.Forms.Padding.All%2A?displayProperty=fullName> en `10`.  
  
4.  Coloque un control <xref:System.Windows.Forms.TextBox> en `SerializationDemoControl`.  
  
5.  Seleccione el control <xref:System.Windows.Forms.TextBox>.  En la ventana **Propiedades**, defina las propiedades siguientes:  
  
    |Propiedad.|Cambie a|  
    |----------------|--------------|  
    |**Multiline**|`true`|  
    |**Dock**|<xref:System.Windows.Forms.DockStyle>|  
    |**ScrollBars**|<xref:System.Windows.Forms.ScrollBars>|  
    |**ReadOnly**|`true`|  
  
6.  En el **Editor de código**, declare un campo de matriz de cadenas denominado `stringsValue` en `SerializationDemoControl`.  
  
     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]  
  
7.  Defina la propiedad `Strings` en `SerializationDemoControl`.  
  
> [!NOTE]
>  El valor <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> se utiliza para habilitar la serialización de la colección.  
  
 [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
 [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
 [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]  
  
1.  Presione F5 para compilar el proyecto y ejecutar el control en el **UserControl Test Container**.  
  
2.  Busque la propiedad `Strings` en <xref:System.Windows.Forms.PropertyGrid> de **UserControl Test Container**.  Haga clic en la propiedad `Strings` y, a continuación, haga clic en el botón de puntos suspensivos \(![Captura de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) para abrir el **Editor de colección de cadenas**.  
  
3.  Escriba varias cadenas en el **Editor de colección de cadenas**.  Sepárelas presionando la tecla INTRO al final de cada cadena.  Haga clic en **Aceptar** cuando termine de escribir las cadenas.  
  
> [!NOTE]
>  Las cadenas que escriba aparecerán en el control <xref:System.Windows.Forms.TextBox> de `SerializationDemoControl`.  
  
## Serializar una propiedad de colección  
 Para probar el comportamiento de serialización del control, colóquelo en un formulario y cambie el contenido de la colección con el **Editor de la colección**.  Puede ver el estado de la colección serializada mirando un archivo de diseñador especial, en el que el **Diseñador de Windows Forms** emite código.  
  
#### Para serializar una colección  
  
1.  Agregue un proyecto de aplicación para Windows a la solución.  Asigne al proyecto el nombre `SerializationDemoControlTest`.  
  
2.  En el **Cuadro de herramientas**, busque la ficha denominada **Componentes SerializationDemoControlLib**.  En esta ficha, encontrará el `SerializationDemoControl`.  Para obtener más información, vea [Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md).  
  
3.  Coloque un `SerializationDemoControl` en el formulario.  
  
4.  Busque la propiedad `Strings` en la ventana **Propiedades**.  Haga clic en la propiedad `Strings` y, a continuación, haga clic en el botón de puntos suspensivos \(![Captura de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) para abrir el **Editor de colección de cadenas**.  
  
5.  Escriba varias cadenas en el **Editor de colección de cadenas**.  Sepárelas presionando la tecla INTRO al final de cada cadena.  Haga clic en **Aceptar** cuando termine de escribir las cadenas.  
  
> [!NOTE]
>  Las cadenas que escriba aparecerán en el control <xref:System.Windows.Forms.TextBox> de `SerializationDemoControl`.  
  
1.  En el **Explorador de soluciones**, haga clic en el botón **Mostrar todos los archivos**.  
  
2.  Abra el nodo **Form1**.  Debajo habrá un archivo denominado **Form1.Designer.cs** o **Form1.Designer.vb**.  Éste es el archivo en el que el **Diseñador de Windows Forms** emite código, que representa el estado en tiempo de diseño del formulario y sus controles secundarios.  Abra este archivo en el **Editor de código**.  
  
3.  Abra la región denominada **Código generado por el Diseñador de Windows Forms** y busque la sección con la etiqueta **serializationDemoControl1**.  Debajo de esta etiqueta está el código que representa el estado serializado del control.  Las cadenas que escribió en el paso 5 aparecerán en una asignación a la propiedad `Strings`.  En el ejemplo de código siguiente se muestra código similar al que verá si ha escrito las cadenas "red", "orange" y "yellow".  
  
4.  \[Visual Basic\]  
  
    ```  
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}  
    ```  
  
5.  \[C\#\]  
  
    ```  
    this.serializationDemoControl1.Strings = new string[] {  
            "red",  
            "orange",  
            "yellow"};  
    ```  
  
6.  En el **Editor de código**, cambie el valor de <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> en la propiedad `Strings` a <xref:System.ComponentModel.DesignerSerializationVisibility>.  
  
7.  \[Visual Basic\]  
  
    ```  
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _  
    ```  
  
8.  \[C\#\]  
  
    ```  
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]  
    ```  
  
9. Recompile la solución y repita los pasos 4 a 8.  
  
> [!NOTE]
>  En este caso, el **Diseñador de Windows Forms** no emite una asignación a la propiedad `Strings`.  
  
## Pasos siguientes  
 Una vez que ya sabe serializar una colección de tipos estándar, puede aprender a perfeccionar la forma de integrar los controles personalizados en tiempo de diseño.  En los temas siguientes se describe cómo se puede mejorar la integración en tiempo de diseño de los controles personalizados.  
  
-   [Design\-Time Architecture](../Topic/Design-Time%20Architecture.md)  
  
-   [Atributos en controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
  
-   [Designer Serialization Overview](../Topic/Designer%20Serialization%20Overview.md)  
  
-   [Tutorial: Crear un control de formularios Windows Forms que aproveche las características en tiempo de diseño de Visual Studio](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
  
## Vea también  
 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>   
 [Designer Serialization Overview](../Topic/Designer%20Serialization%20Overview.md)   
 [How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](../Topic/How%20to:%20Serialize%20Collections%20of%20Standard%20Types%20with%20the%20DesignerSerializationVisibilityAttribute.md)   
 [Tutorial: Rellenar automáticamente el cuadro de herramientas con componentes personalizados](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)