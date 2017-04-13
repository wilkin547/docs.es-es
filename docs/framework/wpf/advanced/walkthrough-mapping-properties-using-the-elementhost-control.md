---
title: "Tutorial: Asignar propiedades mediante el uso del control ElementHost | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ElementHost (control), asignar propiedades"
  - "asignar propiedades"
ms.assetid: bccd6e0d-2272-4924-9107-ff8ed58b88aa
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Tutorial: Asignar propiedades mediante el uso del control ElementHost
En este tutorial se muestra cómo utilizar la propiedad <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> para asignar propiedades de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] a sus propiedades correspondientes en un elemento de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hospedado.  
  
 Las tareas ilustradas en este tutorial incluyen:  
  
-   Crear el proyecto.  
  
-   Definir una nueva asignación de propiedad.  
  
-   Quitar una asignación de propiedad predeterminada.  
  
-   Extender una asignación de propiedad predeterminada.  
  
 Para ver una lista de código completa de las tareas ilustradas en este tutorial, vea [Mapping Properties Using the ElementHost Control Sample](http://go.microsoft.com/fwlink/?LinkID=160018).  
  
 Cuando haya terminado, podrá asignar propiedades de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] a sus propiedades correspondientes de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en un elemento hospedado.  
  
## Requisitos previos  
 Necesita los componentes siguientes para completar este tutorial:  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  
  
## Crear el proyecto  
  
#### Para crear el proyecto  
  
1.  Cree un proyecto de aplicación de [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] denominado `PropertyMappingWithElementHost`.  Para obtener más información, consulte [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  En el Explorador de soluciones, agregue referencias a los ensamblados de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] siguientes.  
  
    -   PresentationCore  
  
    -   PresentationFramework  
  
    -   WindowsBase  
  
    -   WindowsFormsIntegration  
  
3.  Copie el código siguiente en la parte superior del archivo de código `Form1`.  
  
     [!code-csharp[PropertyMappingWithElementHost#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#10)]
     [!code-vb[PropertyMappingWithElementHost#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#10)]  
  
4.  Abra `Form1` en el Diseñador de Windows Forms.  Haga doble clic en el formulario para agregar un controlador para el evento <xref:System.Windows.Forms.Form.Load>.  
  
5.  Vuelva al Diseñador de Windows Forms y agregue un controlador para el evento <xref:System.Windows.Forms.Control.Resize> del formulario.  Para obtener más información, consulte [How to: Create Event Handlers Using the Designer](http://msdn.microsoft.com/es-es/8461e9b8-14e8-406f-936e-3726732b23d2).  
  
6.  Declare un campo <xref:System.Windows.Forms.Integration.ElementHost> en la clase `Form1`.  
  
     [!code-csharp[PropertyMappingWithElementHost#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#16)]
     [!code-vb[PropertyMappingWithElementHost#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#16)]  
  
## Definir nuevas asignaciones de propiedad  
 El control <xref:System.Windows.Forms.Integration.ElementHost> proporciona varias asignaciones de propiedad predeterminadas.  Para agregar una nueva asignación de propiedad, se llama al método <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> de la propiedad <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> del control <xref:System.Windows.Forms.Integration.ElementHost>.  
  
#### Para definir las nuevas asignaciones de propiedad  
  
1.  Copie el código siguiente en la definición de la clase `Form1`.  
  
     [!code-csharp[PropertyMappingWithElementHost#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#12)]
     [!code-vb[PropertyMappingWithElementHost#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#12)]  
  
     El método `AddMarginMapping` agrega una nueva asignación para la propiedad <xref:System.Windows.Forms.Control.Margin%2A>.  
  
     El método `OnMarginChange` convierte la propiedad <xref:System.Windows.Forms.Control.Margin%2A> en la propiedad <xref:System.Windows.FrameworkElement.Margin%2A> de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]  
  
2.  Copie el código siguiente en la definición de la clase `Form1`.  
  
     [!code-csharp[PropertyMappingWithElementHost#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#14)]
     [!code-vb[PropertyMappingWithElementHost#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#14)]  
  
     El método `AddRegionMapping` agrega una nueva asignación para la propiedad <xref:System.Windows.Forms.Control.Region%2A>.  
  
     El método `OnRegionChange` convierte la propiedad <xref:System.Windows.Forms.Control.Region%2A> en la propiedad <xref:System.Windows.UIElement.Clip%2A> de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]  
  
     El método `Form1_Resize` controla el evento <xref:System.Windows.Forms.Control.Resize> del formulario y cambia el tamaño de la zona de recorte para ajustar el elemento hospedado.  
  
## Quitar una asignación de propiedad predeterminada  
 Para quitar una asignación de propiedad predeterminada, llame al método <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> de la propiedad <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> del control <xref:System.Windows.Forms.Integration.ElementHost>.  
  
#### Para quitar una asignación de propiedad predeterminada  
  
-   Copie el código siguiente en la definición de la clase `Form1`.  
  
     [!code-csharp[PropertyMappingWithElementHost#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#13)]
     [!code-vb[PropertyMappingWithElementHost#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#13)]  
  
     El método `RemoveCursorMapping` elimina la asignación predeterminada para la propiedad <xref:System.Windows.Forms.Control.Cursor%2A>.  
  
## Extender una asignación de propiedad predeterminada  
 Puede utilizar una asignación de propiedad predeterminada y también extenderla con su propia asignación.  
  
#### Para extender una asignación de propiedad predeterminada  
  
-   Copie el código siguiente en la definición de la clase `Form1`.  
  
     [!code-csharp[PropertyMappingWithElementHost#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#15)]
     [!code-vb[PropertyMappingWithElementHost#15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#15)]  
  
     El método `ExtendBackColorMapping` agrega un convertidor de propiedades personalizado a la asignación existente de la propiedad <xref:System.Windows.Forms.Control.BackColor%2A>.  
  
     El método `OnBackColorChange` asigna una imagen concreta a la propiedad <xref:System.Windows.Controls.Control.Background%2A> de control hospedado.  Se llama al método `OnBackColorChange` una vez aplicada la asignación de propiedad predeterminada.  
  
## Inicializar las asignaciones de propiedad  
  
#### Para inicializar las asignaciones de propiedad  
  
1.  Copie el código siguiente en la definición de la clase `Form1`.  
  
     [!code-csharp[PropertyMappingWithElementHost#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#11)]
     [!code-vb[PropertyMappingWithElementHost#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#11)]  
  
     El método `Form1_Load` controla el evento <xref:System.Windows.Forms.Form.Load> y realiza la inicialización siguiente.  
  
    -   Crea un elemento <xref:System.Windows.Controls.Button> de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
    -   Llama a los métodos que definió anteriormente en el tutorial para configurar las asignaciones de propiedad.  
  
    -   Asigna los valores iniciales a las propiedades asignadas.  
  
2.  Presione F5 para compilar y ejecutar la aplicación.  
  
## Vea también  
 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Asignación de propiedades en formularios Windows Forms y WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)   
 [WPF Designer](http://msdn.microsoft.com/es-es/c6c65214-8411-4e16-b254-163ed4099c26)   
 [Tutorial: Hospedar un control compuesto de WPF en formularios Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)