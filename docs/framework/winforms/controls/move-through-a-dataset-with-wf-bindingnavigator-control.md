---
title: "C&#243;mo: Desplazarse por un conjunto de datos con el control BindingNavigator de formularios Windows Forms | Microsoft Docs"
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
  - "BindingNavigator (control) [Windows Forms], mover a través de conjuntos de datos"
  - "conjuntos de datos [Windows Forms], mover"
  - "ejemplos [Windows Forms], BindingNavigator (control)"
ms.assetid: 146d97be-3d97-400e-accb-860bbf47729d
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Desplazarse por un conjunto de datos con el control BindingNavigator de formularios Windows Forms
Al crear aplicaciones controladas por datos, a menudo necesitará mostrar colecciones de datos a los usuarios.  El control <xref:System.Windows.Forms.BindingNavigator>, junto con el componente <xref:System.Windows.Forms.BindingSource>, proporciona una solución cómoda y extensible para desplazarse por una colección y mostrar sus elementos secuencialmente.  
  
## Ejemplo  
 En el ejemplo de código siguiente, se muestra cómo usar el control <xref:System.Windows.Forms.BindingNavigator> para desplazarse por los datos.  El conjunto está contenido en un <xref:System.Data.DataView>, que enlaza a un control <xref:System.Windows.Forms.TextBox> con un componente <xref:System.Windows.Forms.BindingSource>.  
  
> [!NOTE]
>  Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación.  El uso de la autenticación de Windows \(también conocida como seguridad integrada\) es un modo más seguro de controlar el acceso a una base de datos.  Para obtener más información, consulte [Proteger la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
 [!code-csharp[System.Windows.Forms.DataNavigator#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataNavigator#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/VB/form1.vb#1)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System, System.Data, System.Drawing, System.Windows.Forms y System.Xml.  
  
 Para obtener información acerca de cómo generar este ejemplo desde la línea de comandos para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Compilar desde la línea de comandos](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) o [Compilar la línea de comandos con csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.  Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228%20\(v=vs.110\)).  
  
## Vea también  
 <xref:System.Windows.Forms.BindingSource>   
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.BindingSource>   
 [BindingNavigator \(Control\)](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)   
 [BindingSource \(Componente\)](../../../../docs/framework/winforms/controls/bindingsource-component.md)   
 [Cómo: Enlazar un control de Windows Forms a un tipo](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)