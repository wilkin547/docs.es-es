---
title: "C&#243;mo: Enlazar un control de Windows Forms a un objeto Factory | Microsoft Docs"
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
  - "BindingSource (componente) [Windows Forms], enlazar a un generador de objetos"
  - "BindingSource (componente) [Windows Forms], ejemplos"
  - "controles [Windows Forms], enlace"
  - "generador de objetos, enlazar"
ms.assetid: 7d59af89-ff82-41d8-a48a-f1fbae788b0d
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Enlazar un control de Windows Forms a un objeto Factory
Al crear controles que interactúan con datos, a veces considerará necesario enlazar un control a un objeto o un método que genere otros objetos.  Este tipo de objetos o métodos se denomina generador.  El origen de datos podría ser, por ejemplo, el valor devuelto de una llamada al método, en lugar de un objeto en la memoria o un tipo.  Puede enlazar un control a este tipo de origen de datos mientras el origen devuelve una colección.  
  
 Puede enlazar fácilmente un control a un objeto de generador utilizando el control <xref:System.Windows.Forms.BindingSource>.  
  
## Ejemplo  
 El ejemplo siguiente muestra cómo enlazar un control <xref:System.Windows.Forms.DataGridView> a un método de generador mediante el uso de un control <xref:System.Windows.Forms.BindingSource>.  El método de generador se denomina `GetOrdersByCustomerId` y devuelve todos los pedidos de un cliente determinado en la base de datos Northwind.  
  
 [!code-cpp[System.Windows.Forms.DataConnector.BindToFactory#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.BindToFactory#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.BindToFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/VB/form1.vb#1)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System, System.Data, System.Drawing y System.Windows.Forms.  
  
 Para obtener información acerca de cómo generar este ejemplo desde la línea de comandos para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Compilar desde la línea de comandos](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) o [Compilar la línea de comandos con csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.  Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Vea también  
 <xref:System.Windows.Forms.BindingNavigator>   
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.BindingSource>   
 [BindingSource \(Componente\)](../../../../docs/framework/winforms/controls/bindingsource-component.md)   
 [Cómo: Enlazar un control de Windows Forms a un tipo](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)