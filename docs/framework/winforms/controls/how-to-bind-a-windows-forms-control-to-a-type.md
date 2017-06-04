---
title: "C&#243;mo: Enlazar un control de Windows Forms a un tipo | Microsoft Docs"
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
  - "BindingSource (componente) [Windows Forms], enlazar a un tipo"
  - "controles [Windows Forms], enlazar a un tipo"
  - "tipos [formularios Windows Forms], enlazar controles"
ms.assetid: 94faeebb-d2bc-45d6-86d7-96a42661b43d
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# C&#243;mo: Enlazar un control de Windows Forms a un tipo
Al crear controles que interactúan con datos, a veces necesitará enlazar un control a un tipo en lugar de a un objeto.  Estas situaciones se producen especialmente en tiempo de diseño, cuando puede que los datos no estén disponibles pero los controles enlazados a datos necesitan mostrar la información de una interfaz pública del tipo.  Por ejemplo, puede enlazar un control <xref:System.Windows.Forms.DataGridView> a un objeto expuesto por un servicio Web y quiere que el control <xref:System.Windows.Forms.DataGridView> etiquete sus columnas en tiempo de diseño con los nombres de miembro de un tipo personalizado.  
  
 Puede enlazar fácilmente un control a un tipo con el componente <xref:System.Windows.Forms.BindingSource>.  
  
## Ejemplo  
 En el ejemplo de código siguiente se muestra cómo enlazar un control <xref:System.Windows.Forms.DataGridView> a un tipo personalizado mediante un componente <xref:System.Windows.Forms.BindingSource>.  Al ejecutar el ejemplo, observará que <xref:System.Windows.Forms.DataGridView> ha etiquetado las columnas que reflejan las propiedades de un objeto `Customer` antes de que el control se rellene con datos.  El ejemplo tiene un botón Add Customer para agregar datos al control <xref:System.Windows.Forms.DataGridView>.  Al hacer clic en el botón, se agrega un nuevo objeto `Customer` al <xref:System.Windows.Forms.BindingSource>.  En un escenario real, los datos se pueden obtener mediante una llamada a un servicio Web o a otro origen de datos.  
  
 [!code-csharp[System.Windows.Forms.DataConnector.BindingToType#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindingToType/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.BindingToType#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindingToType/VB/form1.vb#1)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System y System.Windows.Forms.  
  
 Para obtener información acerca de cómo compilar este ejemplo desde la línea de comandos para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Compilar desde la línea de comandos](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) o [Compilar la línea de comandos con csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.  Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228%20\(v=vs.110\)).  
  
## Vea también  
 <xref:System.Windows.Forms.BindingNavigator>   
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.BindingSource>   
 [BindingSource \(Componente\)](../../../../docs/framework/winforms/controls/bindingsource-component.md)