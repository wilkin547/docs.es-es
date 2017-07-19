---
title: "C&#243;mo: Habilitar la vista en mosaico en un control ListView de formularios Windows Forms mediante el Dise&#241;ador | Microsoft Docs"
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
  - "ListView (control) [Windows Forms], vista en mosaico"
  - "características de vista en mosaico"
  - "disponer en mosaico, Windows Forms, controles"
ms.assetid: 12f0816a-52b8-41ee-a6d9-ded3a8a5817a
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# C&#243;mo: Habilitar la vista en mosaico en un control ListView de formularios Windows Forms mediante el Dise&#241;ador
La característica de vista en mosaico del control <xref:System.Windows.Forms.ListView> permite proporcionar un equilibrio visual entre la información gráfica y la información textual.  La información textual mostrada de un elemento en la vista en mosaico es igual que la información de columna definida para la vista de detalles.  La vista en mosaico funciona en combinación con las características de agrupación o de marca de inserción en el control <xref:System.Windows.Forms.ListView>.  
  
 La vista en mosaico utiliza un icono de 32 x 32 y varias líneas de texto, como se muestra en la imagen siguiente.  
  
 ![Vista en mosaico de un control ListView](../../../../docs/framework/winforms/controls/media/listviewtile.gif "ListViewTile")  
  
 Las propiedades y los métodos de la vista en mosaico permiten especificar los campos de columna que deben mostrarse para cada elemento, y controlar colectivamente el tamaño y el aspecto de todos los elementos dentro de una ventana de vista en mosaico.  Para mayor claridad, la primera línea de texto de un mosaico es siempre el nombre del elemento y no se puede cambiar.  
  
 El procedimiento siguiente requiere un proyecto de **Aplicación para Windows** con un formulario que contiene un control <xref:System.Windows.Forms.ListView>.  Para obtener información sobre cómo configurar tal proyecto, vea [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: Agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  La vista en mosaico sólo está disponible en [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] cuando la aplicación llama al método <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=fullName>.  En sistemas operativos anteriores, cualquier código relacionado con la vista en mosaico no tiene ningún efecto y se muestra el control <xref:System.Windows.Forms.ListView> en la vista de iconos grandes.  Para obtener más información, vea <xref:System.Windows.Forms.ListView.View%2A?displayProperty=fullName>.  
>   
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para establecer la vista en mosaico en el diseñador  
  
1.  Seleccione el control <xref:System.Windows.Forms.ListView> del formulario.  
  
2.  En la ventana **Propiedades**, seleccione la propiedad <xref:System.Windows.Forms.ListView.View%2A> y elija **Mosaico**.  
  
## Vea también  
 <xref:System.Windows.Forms.ListView.TileSize%2A>   
 [Características de Windows XP y controles de formularios Windows Forms](http://msdn.microsoft.com/es-es/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)   
 [Información general del control ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)