---
title: "C&#243;mo: Mostrar una marca de inserci&#243;n en un control ListView de formularios Windows Forms | Microsoft Docs"
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
  - "colocar y arrastrar, marcas de inserción"
  - "gráficos, marcas de inserción"
  - "marcas de inserción"
  - "ListView (control) [Windows Forms], operaciones de arrastre"
ms.assetid: 88d0a15b-25fd-4dc3-a685-297351311940
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# C&#243;mo: Mostrar una marca de inserci&#243;n en un control ListView de formularios Windows Forms
La marca de inserción del control <xref:System.Windows.Forms.ListView> muestra a los usuarios el punto en el que se insertarán los elementos arrastrados.  Cuando un usuario arrastra un elemento a un punto entre otros dos elementos, la marca de inserción muestra la nueva ubicación esperada del elemento.  
  
> [!NOTE]
>  La característica de marca de inserción solo está disponible en [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] cuando la aplicación llama al método <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=fullName>.  En sistemas operativos anteriores, cualquier código relacionado con la marca de inserción no tiene ningún efecto y la marca de inserción no aparecerá.  Para obtener más información, vea <xref:System.Windows.Forms.ListViewInsertionMark>.  
  
 La siguiente imagen muestra una marca de inserción:  
  
 ![Marca de inserción de ListView](../../../../docs/framework/winforms/controls/media/listviewinsertion.gif "ListViewInsertion")  
  
 El ejemplo de código siguiente muestra cómo utilizar esta característica.  
  
## Ejemplo  
 [!code-cpp[System.Windows.Forms.ListView.InsertionMark#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CPP/listviewinsertionmarkexample.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListView.InsertionMark#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CS/listviewinsertionmarkexample.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.InsertionMark#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/VB/listviewinsertionmarkexample.vb#1)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System y System.Windows.Forms.  
  
 Para obtener información acerca de cómo generar este ejemplo desde la línea de comandos para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Compilar desde la línea de comandos](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) o [Compilar la línea de comandos con csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.  Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Vea también  
 <xref:System.Windows.Forms.ListView>   
 <xref:System.Windows.Forms.ListView.InsertionMark%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.ListViewInsertionMark>   
 [ListView \(Control\)](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)   
 [Información general del control ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)   
 [Características de Windows XP y controles de formularios Windows Forms](http://msdn.microsoft.com/es-es/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)   
 [Walkthrough: Performing a Drag\-and\-Drop Operation in Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)