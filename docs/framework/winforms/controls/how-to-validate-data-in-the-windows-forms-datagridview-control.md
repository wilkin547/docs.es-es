---
title: "C&#243;mo: Validar datos en el control DataGridView de formularios Windows Forms | Microsoft Docs"
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
  - "datos [Windows Forms], validación"
  - "cuadrículas de datos, validar datos"
  - "validación de datos, Windows Forms"
  - "DataGridView (control) [Windows Forms], validación de datos"
ms.assetid: d10aef35-701e-4a3c-a684-2a2ed1aeaca6
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# C&#243;mo: Validar datos en el control DataGridView de formularios Windows Forms
El ejemplo de código siguiente muestra cómo validar datos introducidos por un usuario en un control <xref:System.Windows.Forms.DataGridView>.  En este ejemplo, <xref:System.Windows.Forms.DataGridView> se rellena con filas de la tabla `Customers` de la base de datos de ejemplo Northwind.  Cuando el usuario edita una celda en la columna `CompanyName`, se comprueba la validez de su valor verificando que no está vacío.  Si el controlador de eventos del evento <xref:System.Windows.Forms.DataGridView.CellValidating> detecta que el valor es una cadena vacía, <xref:System.Windows.Forms.DataGridView> impide que el usuario salga de la celda hasta que se especifique una cadena que no esté vacía.  
  
 Para una explicación más completa de este ejemplo de código, consulte [Tutorial: Validar datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).  
  
## Ejemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewDataValidation#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#00)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System, System.Data, System.Windows.Forms y System.XML.  
  
 Para obtener información acerca de cómo generar este ejemplo desde la línea de comandos para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Compilar desde la línea de comandos](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) o [Compilar la línea de comandos con csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.  Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Seguridad de .NET Framework  
 Almacenar información confidencial, como una contraseña, en la cadena de conexión puede afectar a la seguridad de la aplicación.  El uso de la autenticación de Windows \(también conocida como seguridad integrada\) es un modo más seguro de controlar el acceso a una base de datos.  Para obtener más información, consulte [Proteger la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.BindingSource>   
 [Tutorial: Validar datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)   
 [Entrada de datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)   
 [Tutorial: Controlar los errores que se producen durante la entrada de datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md)   
 [Proteger la información de conexión](../../../../docs/framework/data/adonet/protecting-connection-information.md)